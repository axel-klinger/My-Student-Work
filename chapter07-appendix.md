# Anhang

## Messergebnisse

### Vorversuche

*Abbildung 25: Natriumhochdrucklampe*

*Abbildung 26: Siccatherm - Rot*

Fehler! Keine gültige Verknüpfung.

*Abbildung 27: Siccatherm - Weiß*

*Abbildung 28: TerrathermDeluxe*

### Hauptversuch

*Abbildung 29: 15° Neigung des Prototyps gegen die Horizontale*

*Abbildung 30: 62° Neigung des Prototyps gegen die Horizontale*

## VBA Funktionen

Da in Excel die Funktionen des Sinus und Cosinus mit dem Radmaß arbeiten, während für den Normalanwender das Gradmaß weitaus einfacher zu handhaben ist, bedeutet im Folgenden DtoR eine Winkelumwandlung von Dezimalgrad ins Bogenmaß und umgekehrt.

Da es nicht Jedermanns Sache ist Quelltext zu lesen, soll hier die eigentliche Formel zur Berechnung der durch direkte Strahlung auf eine Fläche treffenden Sonnenenergie zuerst beschrieben werden. Die Winkel werden dabei in Dezimalgrad eingegeben, die Fläche in m² und Datum und Zeit im entsprechenden Excel-Format.

```
‘Energie auf Fläche
Function EaufA(dBreitengrad, dLängengrad, dDatum, dZeit, nDiffGMT, _
			dFläche, dDelta, dEpsilon, dAbsorptionsgrad)
    Dim S As Vektor		‘Vektor der Sonnenstrahlen
    Dim W As Vektor		‘Normalenvektor der Wand

    Delta = DtoR(dDelta)
    Epsilon = dEpsilon
    HUHS = HöheSonne(dBreitengrad, dLängengrad, dDatum, dZeit, nDiffGMT)
    AZS = DtoR(AzimutSonne(dBreitengrad, dLängengrad, _
		dDatum, dZeit, nDiffGMT))

    S.x = -Cos(DtoR(HUHS)) * Cos(AZS)
    S.y = Cos(DtoR(HUHS)) * Sin(AZS)
    S.z = -Sin(DtoR(HUHS))

    W.x = Cos(DtoR(90) - Delta) * Sin(DtoR(Epsilon + 90))
    W.y = -Cos(DtoR(90) - Delta) * Cos(DtoR(Epsilon + 90))
    W.z = Sin(DtoR(90) - Delta)

    EaufA = IIf(WVV(W, S) > DtoR(90), dAbsorptionsgrad * dFläche _
		* Globalstrahlung(HUHS, dDatum) * -Cos(WVV(W, S)), 0)
End Function
```

Bei allen weiteren Funktionen handelt es sich um die Ermittlung astronomischer Koordinaten zur Angabe des Sonnenstandes.

```
'Horizontalkoordinaten: WinkelHorizontSonne
Function HöheSonne(dBreitengrad, dLängengrad, dDatum, dZeit, dDiffGMT)
	Dim LAST, DEK, REK, STW, GB				
	LAST = Sternzeit(dDatum, dZeit, dDiffGMT, dLängengrad)
	DEK = DtoR(DeklinationSonne(dDatum, dZeit))
	REK = RektaszensionSonne(dDatum, dZeit)              	
	STW = REST(LAST - REK / 360 * 24 + 24, 24)  
	GB = DtoR(dBreitengrad)
	HöheSonne = RtoD(Asin(Cos(GB) * Cos(STW / 24 * 2 * PI) * Cos(DEK) _
+ Sin(GB) * Sin(DEK)))
End Function
```

```
'Horizontalkoordinaten: AzimutSonne
Function AzimutSonne(dBreitengrad, dLängengrad, dDatum, dZeit, dDiffGMT)       
	Dim LAST, DEK, REK, STW, GB, ZIR, NNR, az
    	LAST = Sternzeit(dDatum, dZeit, dDiffGMT, dLängengrad)
	DEK = DtoR(DeklinationSonne(dDatum, dZeit))
	REK = RektaszensionSonne(dDatum, dZeit)
    	STW = REST(LAST - REK / 360 * 24 + 24, 24)
    	GB = DtoR(dBreitengrad)
    	ZIR = Sin(STW / 24 * 2 * PI)
    	NNR = (Cos(STW / 24 * 2 * PI) * Sin(GB) - Tan(DEK) * Cos(GB))
    	az = Atn(ZIR / NNR)
    	If NNR < 0 And ZIR <> 0 Then
        		AzimutSonne = RtoD(az) + 180
    	ElseIf NNR > 0 And ZIR > 0 Then
        		AzimutSonne = RtoD(az)
    	ElseIf NNR > 0 And ZIR < 0 Then
        		AzimutSonne = 360 + RtoD(az)
    	End If
End Function
```

In dieser Studienarbeit gehen wir vereinfachend davon aus, dass sich die Erde auf einer Kreisbahn um die Sonne bewegt. Die Deklination gibt den Winkel zwischen Sonne und Äquator an und verläuft zwischen -23,45° und 23,45°. Die Rektaszension wird vom Frühlingspunkt in östlicher Richtung von 0° bis 360° gezählt.

```
'Äquatorialkoordinaten: WinkelAchseSonne
Function DeklinationSonne(dDatum, dZeit)                 	 
	Dim FP
	FP = DateSerial(Year(dDatum), 3, 21) - DateSerial(Year(dDatum), 1, 0)
	DeklinationSonne = AN * Sin((TagImJahr(dDatum, dZeit) - FP - 0.5) _
/ TageImJahr(dDatum) * 2 * PI)
End Function

'Äquatorialkoordinaten: WinkelFrühlingsPunktSonne
Function RektaszensionSonne(dDatum, dZeit)                   	
	Dim FP, R					
	FP = DateSerial(Year(dDatum), 3, 21) - DateSerial(Year(dDatum), 1, 0)
	R = RtoD((TagImJahr(dDatum, dZeit) - FP + 0.5) _
/ TageImJahr(dDatum) * 2 * PI)
	RektaszensionSonne = IIf(R >= 0, R, R + 360)
End Function
```

Für astronomische berechnungen ist es oft von Vorteil eine durchgehende Tageszählung zur Verfügung zu haben. Dies erreicht das julianische Datum. Nullpunkt ist der 01.01.4713 v. Chr. 12 Uhr Weltzeit (Greenwich).

```
Function JulianischesDatum(dDatum)
	Dim j, b, m, JD
    	Dim p  			'Format JJJJ,MMTT
    	Dim CAL			'Calendar: 1 = Julianisch, 2 = Gregorianisch
	Dim JDNull              'Julianisches Datum für 0 Uhr UT

    	p = Year(dDatum) + Month(dDatum) / 100 + Day(dDatum) / 10000
    	CAL = IIf(p >= 1582.1015, 2, 1)
    	j = IIf(Month(dDatum) > 2, Year(dDatum), Year(dDatum) - 1)
    	m = IIf(Month(dDatum) > 2, Month(dDatum), Month(dDatum) + 12)
    	JD = Fix(365.25 * j) + Fix(30.6001 * (m + 1)) + Day(dDatum) + 1720994.5
    	b = 2 - Fix(j / 100) + Fix(Fix(j / 100) / 4)
    	JDNull = IIf(CAL < 2, JD, JD + b)
    	JulianischesDatum = JDNull
End Function
```

```
Function Sternzeit(dDatum, dZeit, dDiffGMT, dLängengrad)          	
	Dim JD, TN, TE, Omega, l, Lst, Dpsi, Deps, eps0, eps, Dpce
	Dim  UT	'Universial Time
	Dim dz      'Dezimale Zeit
	Dim GMST0	'mittlere Greenwicher Sternzeit um 0 Uhr UT
	Dim GMST    'mittlere Greenwicher Sternzeit um UT Uhr UT
	Dim LMST  	'mittlere Lokale Stz um UT Uhr bei der Länge dLängengrad
 	Dim GAST    'Greenwich Apparent Siderial Time (wahre Sternzeit)
	Dim LAST    'Local Apparent Siderial Time

    	JD = JulianischesDatum(dDatum)
    	TN = (JD - 2451545) / 36525
    	GMST0 = 24110.54841 + 8640184.812866 * TN _
+ 0.093104 * TN * TN - 0.0000062 * TN * TN * TN
    	GMST0 = GMST0 / 3600 - Fix((GMST0 / 3600) / 24) * 24
    	GMST0 = IIf(GMST0 < 0, GMST0 + 24, GMST0)
    	UT = IIf((dZeit - dDiffGMT / 24) < 0, _
(dZeit - dDiffGMT / 24 + 1), (dZeit - dDiffGMT / 24))
    	dz = Hour(UT) + Minute(UT) / 60 + Second(UT) / 3600
    	GMST = REST(GMST0 + 1.00273790935 * dz, 24)
    	LMST = REST(GMST + dLängengrad / 15 + 24, 24)

    	TE = (JD + dz / 24 - 2451545) / 36525
    	Omega = DtoR(125.04452 - 1934.136261 * TE _
+ 0.0020708 * TE * TE + TE * TE * TE / 450000)
    	l = DtoR(280.4665 + 36000.7698 * TE)
    	Lst = DtoR(218.3165 + 481267.8813 * TE)
    	Dpsi = -17.2 * Sin(Omega) - 1.32 * Sin(2 * l) _
- 0.23 * Sin(2 * Lst) + 0.21 * Sin(2 * Omega)
    	Deps = 9.2 * Cos(Omega) + 0.57 * Cos(2 * l) _
+ 0.1 * Cos(2 * Lst) - 0.09 * Cos(2 * Omega)
    	eps0 = 23.43929111 + (-46.815 * TE _
- 0.00059 * TE * TE + 0.001813 * TE * TE * TE) / 3600
    	eps = DtoR(eps0 + Deps / 3600)
    	Dpce = Dpsi * Cos(eps)
    	GAST = GMST + Dpce / 3600 / 15 '/ (3600 * 15)
    	LAST = LMST + Dpce / 3600 / 15

    	Sternzeit = LAST
End Function
```

Für die Globalstrahlung gehen wir bei folgender Rechnung von monatlichen Durchschnittswerten für die Trübungsfaktoren nach Linke [...]

Const Inull = 1370	‘Intensität der Sonne außerhalb der Atmosphäre

```
Function Globalstrahlung(HöhenWinkel, DAT)
	Dim TL As Variant
	TL = Array(2.7, 3.1, 3.3, 3.5, 3.7, 4.3, 4.3, 4.1, 3.9, 3#, 2.9, 2.7)
	If HöhenWinkel >= 0 Then
        	Globalstrahlung = INull * Sin(DtoR(HöhenWinkel)) * 0.84 _
		* exp ^ (-TL(Month(DAT) - 1) * 0.027 / Sin(DtoR(HöhenWinkel)))
    	Else
        	Globalstrahlung = 0
    	End If
End Function
```

Die Funktion E_In liefert die Werte für von der kombinierten Fassade aufgenommene Energie in Watt

```
Function E_In(dBreitengrad, dLängengrad, dDatum, dZeit, nDiffGMT, _
Dicke, Anzahl, Laenge, alp, bet, del, eps, ab1, ab2)
    Dim FR, FA, FA_, FB, FB_, FB__, a, b, l, tmpa, tmpb, tmpb_
    Dim tmp As Vektor
    Dim S As Vektor
    Dim S_ As Vektor
    Dim Sa_ As Vektor
    Dim tmpSa_ As Vektor
    Dim tmpSb_ As Vektor
    Dim Sa__ As Vektor
    Dim Sar_ As Vektor
    Dim Sb_ As Vektor
    Dim Sb__ As Vektor
    Dim W As Vektor
    Dim NSch As Vektor
    Dim NSch_ As Vektor
    Dim tmpN_ As Vektor
    Dim NSp As Vektor
    Dim SummeQA, SummeQB

    Alpha = DtoR(alp)
    Beta = DtoR(bet)
    a = Dicke / Sin(Beta)
    b = Dicke / Sin(Alpha)
    l = Laenge
    Gamma = DtoR(180) - Alpha - Beta
    Delta = DtoR(del)
    Epsilon = eps
    HUHS = HöheSonne(dBreitengrad, dLängengrad, dDatum, dZeit, nDiffGMT)
    AZS = DtoR(AzimutSonne(dBreitengrad, dLängengrad, _
dDatum, dZeit, nDiffGMT))

    x0s = 600: y0s = 450: sc2 = 10
    x1s = sc2 * c * Cos(Delta): y1s = sc2 * c * Sin(Delta)
    x2s = sc2 * b * Cos(DtoR(180) - Delta - Alpha)
    y2s = sc2 * b * Sin(DtoR(180) - Delta - Alpha)
    x3s = sc2 * a * Cos(Delta - Beta): y3s = sc2 * a * Sin(Delta - Beta)

    S.x = -Cos(DtoR(HUHS)) * Cos(AZS)
    S.y = Cos(DtoR(HUHS)) * Sin(AZS)
    S.z = -Sin(DtoR(HUHS))

    W.x = Cos(DtoR(90) - Delta) * Sin(DtoR(Epsilon + 90))
    W.y = -Cos(DtoR(90) - Delta) * Cos(DtoR(Epsilon + 90))
    W.z = Sin(DtoR(90) - Delta)

    NSch.x = Cos(DtoR(90) - Delta - Alpha) * Sin(DtoR(-Epsilon + 90))
    NSch.y = Cos(DtoR(90) - Delta - Alpha) * Cos(DtoR(-Epsilon + 90))
    NSch.z = Sin(DtoR(90) - Delta - Alpha)

    NSp.x = Cos(DtoR(90) - Delta + Beta) * Sin(DtoR(-Epsilon + 90))
    NSp.y = Cos(DtoR(90) - Delta + Beta) * Cos(DtoR(-Epsilon + 90))
    NSp.z = Sin(DtoR(90) - Delta + Beta)

    S_ = VTrans(S, 0, Epsilon)             'Bildschirmkoordinaten im Schnitt
    Sa_ = VTrans(S, RtoD(Delta - Beta), Epsilon)
    Sb_ = VTrans(S, RtoD(Delta + Alpha), Epsilon)

    Sar_.x = Sa_.x: Sar_.y = Sa_.y: Sar_.z = -Sa_.z
    NSch_.x = Sin(Alpha + Beta): NSch_.y = 0: NSch_.z = Cos(Alpha + Beta)

    If HUHS > 0 Then               		'Wenn die Sonne überm Horizont steht
        If WVV(W, S) > DtoR(90) Then   	'Wenn die Wand von vorne angeschienen            If WVV(NSp, S) > DtoR(90) Then   'Spiegel wird direkt angeschienen
                'b_ für oberen Spiegelpunkt ermitteln
                tmpSa_.x = Sa_.x: tmpSa_.y = 0: tmpSa_.z = -Sa_.z
                tmpN_.x = 0: tmpN_.y = 0: tmpN_.z = 1
                ah_ = DtoR(90) - WVV(tmpN_, tmpSa_) 'Atn(-Sa_.z / Sa_.x)
                tmpb_ = a / Sin(DtoR(180) - Gamma - ah_) * Sin(ah_)
                tmpb_ = IIf(tmpb_ < 0, 0, tmpb_)
                tmpb_ = IIf(tmpb_ > b, b, tmpb_)

                If WVV(NSch, S) > DtoR(90) Then 'Schwarz direkt angeschienen
                    a_ = 0
                    tmpb = b
                    tmpa = a
                Else                            'Schwarz wirft Schatten
                    'a_ für Schatten ermitteln
                    tmpSb_.x = Sb_.x: tmpSb_.y = 0: tmpSb_.z = Sb_.z
                    tmpN_.x = 0: tmpN_.y = 0: tmpN_.z = 1
                    bh_ = DtoR(90) - WVV(tmpN_, tmpSb_)
                    a_ = b / Sin(DtoR(180) - Gamma - bh_) * Sin(bh_)
                    a_ = IIf(a_ < 0, 0, a_)
                    a_ = IIf(a_ > a, a, a_)
                    tmpb = 0
                    tmpa = a
                End If

                If a_ > 0 Then            'Wenn unterer Spiegelpunkt existiert
                    'b__ ermitteln
                    b__ = a_ * Sin(ah_) / Sin(DtoR(180) - Gamma - ah_)
                    b__ = IIf(b__ < 0, 0, b__)
                    b__ = IIf(b__ > b, b, b__)
                Else
                    b__ = 0
                End If
            Else                                'Spiegel wirft Schatten
                'b_ für Schatten ermitteln
                tmpSa_.x = Sa_.x: tmpSa_.y = 0: tmpSa_.z = Sa_.z
                tmpN_.x = 0: tmpN_.y = 0: tmpN_.z = 1
                ah_ = DtoR(90) - WVV(tmpN_, tmpSa_)
                b_ = a / Sin(DtoR(180) - Gamma - ah_) * Sin(ah_)
                b_ = IIf(b_ < 0, 0, b_)
                b_ = IIf(b_ > b, b, b_)
                a_ = 0
                tmpb = b
                tmpa = 0
            End If
            FA = (tmpa - a_) * l * Anzahl / 100
            FB = (tmpb - b_) * l * Anzahl / 100
            FR = (tmpb_ - b__) * l * Anzahl / 100

SummeQA = ab2 * FA * Globalstrahlung(HUHS, dDatum) * -Cos(WVV(NSp, S))
SummeQB = ab1 * FB * Globalstrahlung(HUHS, dDatum) * -Cos(WVV(NSch, S)) _
+ ab1*(1 - ab2)*FR*Globalstrahlung(HUHS, dDatum)*-Cos(WVV(NSch_, Sar_))
            E_In = SummeQA + SummeQB
        Else                                    'Wand von hinten angeschienen
            E_In = 0
        End If
    Else                                    'Sonne steht unter dem Horizont
        E_In = 0
    End If
    On Error GoTo 0
End Function
```
