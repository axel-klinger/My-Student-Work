## Abstract

Im Sommer heizen sich Gebäude auf und müssen mit Energieaufwand gekühlt werden, während sie im Winter auskühlen und mit Energieaufwand beheizt werden müssen. Wenn die Fassade des Gebäudes die Strahlung der Sonne im Sommer weniger absorbiert und im Winter weniger reflektiert, kann Kühl- und Heizenergie gespart werden. Wenn sich die Fassade des Gebäudes im Winter verdunkelt und im Sommer erhellt, können über die Absorption der Strahlung die Energieaufwände gesenkt werden. Hier wird ein Ansatz, experimentell und simuliert vorgestellt, wie sich die Absorption der Strahlung in Abhängigkeit des Winkles der Einstrahlung auf die Fassade variieren lässt.

## Grundgedanke

In der vorliegenden Arbeit wird die von der Sonne auf die nicht transparente (opake) Gebäudehülle wirkende Energie untersucht.
Das Ziel des Optimierungsansatzes ist es, einen möglichst großen Teil dieser Energie in der Heizperiode zu nutzen und im Sommer abzuführen. Durch die Verschiebung der Oberflächentemperatur einer Fassade in Richtung Innenraumtemperatur ergibt sich ein geringeres Energiegefälle in der Wand, was zu einer geringeren Ausgleichsleistung durch Klimaanlage bzw. Heizung führt.

Mit den von uns im Rahmen dieser Studienarbeit ausgeführten Versuchen soll  der Berechnungsalgorithmus für die sonneneinstrahlungswinkelabhängige Energieaufnahme  unser geometrischen Struktur verifiziert werden. Als Ansatz müssen dafür Angaben für das Verhältnis der Absorptionsgrade der von uns verwendeten Oberflächen durch Vorversuche gewonnen werden.  

In wie weit sich die Transmissionsverluste, bzw. die äußeren Kühllasten durch opake Außenbauteile zugunsten der Gesamtenergiebilanz eines Hochbaus durch eine zur Sonne optimierte Fassade, reduzieren lassen, soll prognostiziert werden.

### Winterliche Nutzung

Die Anforderungen an den Wärmeschutz von Gebäuden sind in [1] und [3] festgelegt. Die solaren Wärmegewinne infolge Strahlungsabsorption auf opake Bauteile werden erstmalig in [2] als eine der energetischen Einflussgrößen für die Heizwärmebedarfsberechnung erwähnt. Abhängig sind diese unter anderem vom mittleren Strahlungsabsorptionsgrad des Außenbauteils. Sie dürfen im Monatsbilanzverfahren unter Vernachlässigung des Minderungsfaktors durch Verschattung oder Sonnenschutz, eines etwaigen Rahmenanteils und dem langwelligen Abstrahlungseffekt nach der Formel:

$$
\Phi_{S,o_M} = \sum_j I_{S,M,j} * (\sum_n a_{o,n} * k_n * R_a * A_n)
$$

berücksichtigt werden.

Dabei sind:

* $\Phi$	[W]	= Wärmegewinne
* I [W/m²]	= Sonneneinstrahlungsintensität
* k [W/(m²K)]	= Wärmedurchgangskoeffizient
* a [-]	= Absorptionsgrad für Sonneneinstrahlung
* R [m²K/W]	= Wärmedurchlass
* A	[m²]	= Außenbauteiloberfläche

Indizes:

* S	= solar		
* a	= außen
* M	= monatlich		
* j	= Himmelsrichtung
* o	= opak		
* n	= Bauteil

Unser Ansatz besteht darin diese, wenn auch im Vergleich zu denen durch  transparente Bauteile geringen, Gewinne zu maximieren, indem wir die geometrische Struktur unserer Fassade so ausbilden, dass bei den geringen Sonnenstandshöhenwinkeln im Winterhalbjahr die Sonnenstrahlen zum Teil direkt und zum Teil reflektiert auf schwarze Flächen fallen.

Eine pauschalere Ansatzmöglichkeit besteht darin, die Transmissionswärmeverluste abzumindern. Die Wärmestromdichte durch ein opakes Außenbauteil von innen nach außen bei Sonneneinstrahlung kann dann vereinfachend (stationäre Bedingungen) über die Gleichung:

$$
q = k * (\theta_{Li} - \theta_{La} - \frac{a_s * I} {\alpha_a})
$$

beschrieben werden.

Dabei sind:

* q [W/m²]	= Wärmestromdichte
* k [W/(m²K)]	= Wärmedurchgangskoeffizient
* $\theta_{Li}$ [°C]	= Raumlufttemperatur
* $\theta_{La}$ [°C]	= Außenlufttemperatur
* $\alpha_a$ [W/(m²K)]	= äußerer Wärmeübergangskoeffizient

Der Term $\theta_{La} + a_s * \frac{I}{\alpha_a}$ wird auch als modifizierte Sonnenlufttemperatur $\Theta$ bezeichnet, so dass gilt:

$$
q = k * (\theta_{Li} - \Theta)
$$

Diese Gleichung zeigt, dass für $\Theta > \theta_{Li}$ eine Umkehr des Wärmestroms erfolgt.

### Sommerlicher Wärmeschutz

In den Sommermonaten gilt es im Gegensatz zum Winter, die einfallende Wärmeenergie möglichst gering zu halten. Die Grundlagen und Berechnungsverfahren für den sommerlichen Wärmeschutz sind unter anderem in [1] und [4] zu finden. Nach [4] unterteilt man bei der Berechnung der anfallenden Kühllast, zur Dimensionierung etwaiger Klimaanlagen beispielsweise, die innere und äußere. Letztere umfasst die über die Gebäudeumschließungsfläche eintretende Energie, die für die Untersuchung von besonderem Interesse ist. Die Strahlungsbeeinflussung der Außenoberfläche im Sommerhalbjahr gering zu halten und die dadurch anfallenden (wenn auch vergleichsweise geringen) zusätzlichen Kühllasten zu minimieren ist Ziel dieser Untersuchung.

Nach dem Kurzverfahren der [4] werden Bauartklassen (Dämpfungsfaktoren und Zeitverschiebungen charakterisieren diese), so wie Flächenorientierungs- und tageszeitabhängig äquivalente Temperaturdifferenzen verwendet, um den Wärmestrom durch die Außenwände zu bestimmen. In die äquivalente Temperaturdifferenz ist dabei nach einem Verfahren von G. Nehrling die Lösung des instationären Wärmedurchgangs durch äußere Raumumschließungsflächen eingearbeitet. Sie berücksichtigt des weiteren metrologische Einflussfaktoren wie die Ausstrahlung der Fläche gegen die Atmosphäre und die atmosphärische Gegenstrahlung.

Für diese Betrachtungen soll aber der,  die Speicherfähigkeit der Baustoffes vernachlässigende,  Wärmestrom unter stationären Bedingungen eine ausreichende Basis darstellen.

### Randbedingungen der Untersuchung
Zur Untersuchung der Energieaufnahme einer Fassade sind diverse Einflussfaktoren von Bedeutung. Da im Rahmen dieser Studienarbeit nicht alle Größen berücksichtigt werden können, werden folgende Parameter konstant gesetzt:

* Klarer Himmel
* Kein Wind und kein Niederschlag
* Auswirkungen von Luftfeuchtigkeit und Luftdruck auf die Intensität bleiben unberücksichtigt
* Ausschließlich Energiestrom in das Fassadenelement
* Vernachlässigung der thermischen Längenänderungen und daraus entstehende erhöhte Temperaturspannungen
* Kein diffuser Strahlungsanteil
* Stationär
* Sonnenäquivalenz im Rahmen des im Vorversuch angewandten Materials (s. 3.1)

## Analytischer Weg

Zur Praktischen Anwendung der in diesem Kapitel beschriebenen Größen können anhand des unter Visual Basic entwickelten Excel-Programms die einzelnen Schritte nachvollzogen werden. Die Inhalte der wichtigsten Funktionen sind als Listings im Anhang zu finden. Hier klicken:

Um eine möglichst allgemeine Aussage über die Jahres- und Tageszeitlich schwankenden Intensitäten der Sonne machen zu können, ist es zunächst einmal erforderlich, den aktuellen, bzw. auf eine Uhrzeit und einen Ort bezogenen, Sonnenstand zu ermitteln.

Die Berechnung der Energie, die von der Sonne auf eine Fassade abgegeben wird, ist abhängig vom Winkel zwischen Strahlungsquelle und Oberfläche und der wirksamen Intensität des Strahlers. Der Winkel wird mit Hilfe der Vektorrechnung im Horizontkoordinatensystem zwischen dem Richtungsvektor der Sonne und dem Normalenvektor der Bauteiloberfläche gebildet. Der Richtungsvektor der Sonne wird beschrieben durch einen Winkel in der Ebene des Horizonts gegen Süden, dieser Winkel heißt das Azimut a, und einem Winkel zwischen Sonne und Horizont, der Höhe h.

Der Normalenvektor einer zu betrachtenden Fläche wird auf die gleiche Weise ermittelt, durch die Verdrehung gegen Süden und die Neigung gegen den Horizont.

Die Intensität der Sonne die auf ein Bauteil wirkt, errechnet sich aus einem konstanten Wert für die außerhalb der Atmosphäre wirkende Strahlungsintensität, abgemindert durch eine jahreszeitlich schwankende Trübung der Atmosphäre.


### Sonnenstand

Zur Ermittlung des Sonnenstandes gibt es Tabellenwerke für die Parameter Azimut und Höhe in Abhängigkeit von Ort und Zeit auf der Erde. Im Rahmen der Simulation unter Excel werden die beiden Winkel jedoch berechnet, um sie allgemeingültiger handhaben zu können. Für die Berechnung wird zunächst einmal ein weiteres Koordinatensystem benötigt, welches die jahreszeitliche Veränderung des Sonnenstandes beschreibt - das sogenannte Äquatorkoordinatensystem.

#### Deklination und Rektaszension der Sonne

![Deklination und Rektaszension](images/Ekliptik4.png)

*Abbildung 1: Deklination und Rektaszension*

Im Äquatorkoordinatensystem, welches die Positionen von Himmelskörpern beschreibt und seinen Ursprung im Mittelpunkt der Erde hat, wird die Richtung eines Sterns, in diesem Fall die der Sonne,  durch die beiden Winkel Rektaszension  und Deklination  beschrieben. Im Vergleich zu anderen Sternen ändern sich diese Größen für die Sonne im Laufe des Jahres, da sich die Erde um die Sonne bewegt. Die Größen sind nur abhängig von der Variablen ZEIT und für alle Orte auf der Erde gleich. Bei diesem Koordinatensystem liegt die Z-Achse in der Polachse und zeigt nach Norden. Die X-Achse zeigt auf den Frühlingspunkt. Der Frühlingspunkt liegt auf der Schnittgeraden der Äquatorebene,  welche mit der Ebene des Erdäquators übereinstimmt, und der Bahnebene, welche um 23,45° gegenüber der Äquatorebene geneigt ist.

Bei den Berechnungen ist an dieser Stelle auf astronomische Feinheiten wie Aberration, Nutation, Refraktion und Kepler [5] verzichtet worden, da diese nur eine sehr geringe Auswirkung auf die für diese Untersuchung relevanten Intensitäten haben.

Die beiden Größen  und  lassen sich nun mit Hilfe zweier Excel-Funktionen aus den Parametern Datum, Uhrzeit und Zeitverschiebung gegenüber Greenwich Mean Time (GMT) in Stunden berechnen.

$\alpha$ = RektaszensionSonne(Datum;Zeit;DiffGMT)

$\delta$ = DeklinationSonne(Datum;Zeit;DiffGMT)

| Wert | Abbr. | Beispiel |
| ---- | ----- | -------- |
| Datum: | DAT | 21. Juni 1999 |
| Zeit: | ZT | 12:27:00 |
| Abstand von GMT in Stunden: | DiffGMT | 1 |
| Rektaszension der Sonne | RektS | 90,76° |
| Deklination der Sonne | DeklS | 23,45° |

Der nächste Schritt ist es, diese globalen Koordinaten in ein lokales Koordinatensystem zu übertragen, welches seinen Ursprung auf der Erdoberfläche hat, so dass sich diese Koordinaten mit denen des Bauteiles vergleichen lassen. Das lokale Koordinatensystem ist das Horizontsystem.

#### Azimut und Höhe der Sonne

![Azimut und Höhe](images/HorSys.png)

*Abbildung 2: Azimut und Höhe*

Der  Ursprung des Horizontsystems auf der Erdoberfläche wird durch den Längen- und  Breitengrad beschrieben. Hierbei zeigt die X-Achse entlang des Längengrades nach Süden und die Z-Achse senkrecht nach oben zum Zenit. In diesem Koordinatensystem, welches auch bereits dem kartesischen Koordinatensystem des Bauteils entspricht, wird der Sonnenstand durch das Azimut a als Winkel von Süd über West, Nord, Ost und die Höhe der Sonne über dem Horizont als Winkel h beschrieben

Da sich nun durch die Drehung der Erde um ihre Achse auch das Horizontalsystem um die Z-Achse des Äquatorsystems dreht, benötig man eine weitere Größe, die diese Drehung beschreibt, den Stundenwinkel . Mit den drei Größen Rektaszension, Deklination und Stundenwinkel lassen sich nun unter Excel das Azimut und die Höhe berechnen. Um dem späteren Anwender diese Funktionen zu vereinfachen, werden an die Funktionen nur Ort und Zeit übergeben, wobei intern die drei anderen Größen, sowie die Sternzeit als einheitliche Zeitbasis berechnet werden.

A = AzimutSonne(Breitengrad;Längengrad;Datum;Uhrzeit;DiffGMT)

H = HöheSonne(Breitengrad;Längengrad;Datum;Uhrzeit;DiffGMT)

| Wert | Abbr. | Beispiel |
| ---- | ----- | -------- |
| Geografische Breite: | GB | 52,24° |
| Geografische Länge: | GL | 9,40° |
| Höhe ü. Horiz. d. Sonne | HUHS | 61,22° |
| Azimut der Sonne | AZS | 359,32° |

#### Orientierung der Fläche

Die Orientierung der Bauteiloberfläche wird durch die Drehung um die Z-Achse  von Süden nach Westen negativ, von Süden nach Osten positiv und die Neigung der Fläche gegen den Horizont  beschrieben.

### Berechnung der Fassade

#### Abmessungen und Eigenschaften des Bauteils

*Abbildung 3: Schnitt der Fassade*

*Abbildung 4: Draufsicht der Fassade*

| Wert | Abbr. | Beispiel |
| ---- | ----- | -------- |
| Höhe der Leisten | D | 1,05cm |
| Anzahl der Leisten | n | 22 |
| Bauteillänge | l | 0,49m |
| Schwarz-Wand Winkel | Alpha | 34,00° |
| Spiegel-Wand Winkel | Beta | 56,00° |
| Wand-Horizont Winkel | Delta | 90,00° |
| Wand-Süd Winkel | Epsilon | 0,00° |
| Absorptionsgrad Schwarz | abSch | 0,80 |
| Absorptionsgrad Spiegel | abSp | 0,21 |
| Spitze der Profile | Gamma | 90,00° |
| Breite der schwarzen Lamellen | b | 1,88cm |
| Breite der Spiegellamellen | a | 1,27cm |
| Breite der Profile auf der Wand | c | 2,26cm |
| Bauteilhöhe | h | 0,50m |
| Summe der schwarzen Flächen | B | 0,20m² |
| Summe der Spiegelflächen | A | 0,14m² |
| Wandfläche | W | 0,24m² |

#### Abmessungen und Eigenschaften der Referenzflächen

| Wert | Abbr. | Beispiel |
| ---- | ----- | -------- |
| Neigung wie Bauteil |  | 90,00° |
| Drehung wie Bauteil |  | 0,00° |
| Fläche wie Bauteil |  | 0,24m² |
| **Schwarz** |  |  |
| Absorptionsgrad Schwarz | abSch | 0,80 |
| **Spiegel** |  |  |
| Absorptionsgrad Spiegel | abSp | 0,21 |

### Intensitäten der Sonne

#### Globalstrahlung
Die Globalstrahlung ist die Strahlungsintensität, die abgemindert um die atmosphärische Trübung bei unbewölktem Himmel auf der Erdoberfläche auf eine senkrecht zur Strahlungsrichtung stehende Fläche fällt. Sie hängt neben der jahreszeitabhängigen atmosphärischen Trübung nach Linke, von der Länge des Weges durch die Atmosphäre ab. Letztere ist vom Höhenwinkel der Sonne und der Höhe über NN abhängig.

Analytisch wird diese Intensität nach der von Kasten in [5] angegebenen Parametrisierungsformel noch ohne die Höhenabhängigkeit ermittelt:

$$
G(0) = I_0 * \sin(\gamma) * 0,84 * e^{(\frac{-T_L*0,027}{\sin(\gamma)})}
$$

mit: 	

* G(0) = Globalstrahlung bei unbewölktem Himmel
*	$\gamma$ = Höhenwinkel der Sonne überm Horizont
* $I_0$ = Solarkonstante (1,37 kW/m2)
* TL = Linke Trübungsfaktor

Die wirksame Intensität der Sonne auf eine Fläche ($I_w$) hängt entscheidend von dem Winkel zwischen  der Flächennormalen sowie der Strahlungsstromrichtung ($\eta$) ab. Es gilt:

$$
I_w = G(0) * \cos(\eta)
$$

### Strahlungsgewinne

Das Produkt der wirksamen Intensitäten auf den jeweiligen Flächen und ihrer Absorptionsgrade ergibt  die durch den Strahlungsstrom erzeugte Wärmestromdichte an der Bauteiloberfläche. Um den dadurch erzeugten Wärmestrom in ein Bauteil zu einem bestimmten Zeitpunkt zu erhalten, wird die Wärmestromdichte mit der jeweiligen zu diesem Zeitpunkt beschienen Fläche multipliziert. Das Ergebnis dieser Berechnung (durch die Funktion $E_In$) ist eine dreidimensionale Darstellung des vom Bauteil absorbierten Energiestroms in Abhängigkeit von Datum (X-Achse vom 01.01. bis 31.12.) und Uhrzeit (Y-Achse von 00:00 bis 24:00 Uhr) und wird beispielhaft für das im Hauptversuch verwendete Bauteil in Abbildung 3 gezeigt. Um nun einen Vergleich zu einer normalen ebenen Oberfläche herzustellen, werden neben dem Fassadenelement  auch noch eine schwarze sowie eine Spiegel-Referenzfläche berechnet, die sich vom eigentlichen Bauteil nur durch ihre konstanten Absorptionsgrade unterscheiden. Die Ausrichtung der Flächen ist die gleiche, ebenso Ort und Zeit. Ihre Wärmeströme zu bestimmten Zeitpunkten werden analog denen des zickzackprofilierten Bauteils im Programm angezeigt. Um sie qualitativ einstufen zu können ist ihre unterschiedliche Skalierung zu beachten.

![Prototyp](images/prototyp.png)

*Abbildung 5: Wärmestrom in den Prototyp über Datum und Tageszeit*

![Schwarz](images/schwarz.png)

*Abbildung 6: Wärmestrom auf Schwarz*

![Weiß](images/weiss.png)

*Abbildung 7: Wärmestrom auf Spiegel*

## Versuche

### Vorversuch

*Abbildung 8: Natriumhochdrucklampe*

Ziel der Voruntersuchungen war neben der Einarbeitung in die Messtechnik, eine geeignete Lampe zu finden, welche das in DINV 4108-6 angegebene Verhältnis von 2,0 der Strahlungsabsorptionsgerade im energetisch wirksamen Spektrum des Sonnenlichtes für helle und dunkle Oberflächen, möglichst materialunabhängig auch für die verwendeten Sprühfarboberflächen Schwarz und Weiß, gewährleistet. Zur Verfügung standen als Strahlungsquellen:

*	eine Natriumhochdrucklampe  400W (Sylvania)
*	drei Wolframbandlampen (Osram)
    * TerrathermDeluxe 150W
    * Siccatherm Rot 150W
    * Siccatherm Weiß  375W

Des weiteren waren noch Halogenstrahler (1000 W) vorhanden, welche jedoch mit Lüftungsventilatoren ausgestattet waren, was zu einer  unkontrollierbaren Luftbewegung in der Klimakammer geführt hätte. In wie weit die Abgeschlossenheit des Systems sich bei diesen 1000 W Birnen zu Ungunsten der Lufttemperatur bzw. der Birne selber verhalten hätte, wurde lieber unversucht gelassen. Außerdem ist nach [7] der nutzbare Spektralbereich von Halogenglühlampen nahezu deckungsgleich mit dem der Wolframbandlampen.

#### Gerät

*Abbildung 9: Messwerterfassungsanlage*

In den Versuchen wurden grundsätzlich nur Temperaturen gemessen und zwar mit der Messwerterfassungsanlage des Institutes für Bauphysik. An den in Abbildung 9 dargestellten Haupteinschub des Meßplatzes waren zwei Boxen angeschlossen,  die jeweils mit sechs Temperatursensoren über Präzisionsteckverbinder bestückt wurden. Es handelte sich dabei um Wiederstandsmessfühler der  Firma Thermocoax mit einer Länge von 25 cm und einem Durchmesser von 2m (NiCr-Ni Elemente Typ K nach [8]). Das Thermoelement ist isoliert im Stahlmantel, welcher über die Abschirmung des Anschlusskabels mit der Masse des Mehrkanalmessplatzes verbunden ist. Die jeweils für eine Messreihe verwendeten Temperaturfühler wurden vorab zur Kalibrierung dicht zusammengebunden und über einen Zeitraum von 2h auf Messwertgleichheit überprüft. Die Standardabweichung der Stichproben lag bei diesen Messungen stets unter 0,2 K.

Um von stationären Bedingungen und somit konstanten Energieströmen ausgehen zu können, wurden die Versuche in einer Klimakammer (2,4*2,4*3,2m) aufgebaut, und eine Laufzeit von jeweils 15 h gewählt.

#### Aufbau

In der Klimakammer wurden auf einem, ein Meter hohen mit einem schwarzen Tuch abgedeckten,  Lochblechtisch je zwei Tafelelemente aus Holz (23,5*38,5*0,3 [cm]) und Metall (23,5*38,5*0,07 [cm]) - an ihren Eckpunkten auf 5cm hohem Dämmstoffklötzchen aufgelagert - platziert. Jeweils ein Metall- und ein Holztafelelement wurden auf der Oberseite gefärbt mit Sprühlack seidenmatt Tiefschwarz (RAL 9005), bzw. seidenmatt Reinweiß (RAL 9010). Die Temperaturfühler waren mit einem Streifen Aluminiumkaschierband ganzflächig anliegend jeweils auf der Rückseite befestigt (Abbildung 11). Die vier Platten waren gleichmäßig auf die Quadranten eines xy-Koordinatensystems in Tischebene verteilt, dessen Ursprung im Lotfußpunkt der jeweiligen Lampe lag. Der Abstand zwischen der Lampe und den Tafelelement betrug 80cm (Abbildung 10).

Die Lufttemperatur wurde in allen Versuchen mit fünf Thermosonden gemessen, welche sich im Abstand von 2 cm parallel in einem 3*15*25 cm großen Schaumstoffklotz befinden, der auf Höhe der Tafelelemente direkt neben dem Tisch platziert  ist und durch ein weißes Baumwolltuch verschattet wird (Abbildung 20).

*Abbildung 10: Aufbau Vorversuch*

*Abbildung 11: Befestigung der Thermoelemente*

#### Auswertung
Ausgehend von stationären Verhältnissen und einer sehr guten zeitlichen Konstanz des eingestrahlten Energiestroms und der Tatsache,  dass die Menge der Energieabgabe durch Strahlung und Leitung nur von der Temperaturdifferenz zum angrenzenden Medium abhängt, kann man mit Hilfe des Energieerhaltungssatzes (aus dem Strahlungsangebot aufgenommene Energie = durch Strahlung und Leitung abgegebene Energie) aus den beiden unterschiedlich gefärbten aber ansonsten gleichen Materialproben und ihrer Temperaturdifferenz zur Umluft Aussagen über das Verhältnis der Absorptionsgrade as/aw der Oberflächen machen.

Die Stationarität in den durchgeführten Versuchen bezieht sich auf die Temperaturdifferenz der Proben zur Außenluft, denn wie sich aus den Messergebnissen im Anhang ersehen lässt, stieg die Lufttemperatur aufgrund der sehr gut gedämmten Klimakammer über den gesamten Versuchszeitraum.

Betrachtet man die aus den Messergebnissen gewonnenen Graphen as/aw der vier getesteten Lampen im Anhang, stellt sich zwar nach dem eingangs beschriebenen Kriterium die weiße Siccatherm – Lampe als die brauchbarste dar, da diese sowohl für die Holz- als auch für die Metallproben ein Verhältnis der Absorptionsgrade von 2 liefert. Vergleicht man aber ihre spektrale Intensitätsverteilung mit der in [9] angegebenen Strahlungsfunktion der Globalstrahlung und bedenkt die Wellenlängenabhängigkeit des Absorptionsfaktors, wird deutlich,  weshalb mit diesen Versuchen keineswegs auf Absolutwerte für das Temperaturverhalten des Fassadenelementes unter realer Sonnenbeanspruchung geschlossen werden konnte.

![Spektrum](images/spektrum.png)

*Abbildung 12: Spektralverteilung Sonnenlicht nach [9] und  Lampe laut Herstellerangaben*

Auch der angestrebte Versuch aus den lichttechnischen Größen der Lampe über Normlichtarten einen Bezug zu realen Sonnenstrahlintensitäten zu bekommen, gestaltete sich als schwierig, da diese Größen alle auf der Basiseinheit Candela fußen. In [10] wird die Definition dieser Einheit angegeben als die Lichtstärke einer bestimmten Richtung einer Strahlungsquelle, die monochromatische Strahlung der Frequenz 540 THz (TeraHertz = 1012 Hertz) aussendet und deren Strahlstärke in dieser Richtung (1/683) Watt durch Steradiant  beträgt.

Bei den Ergebnissen der Natriumhochdrucklampe fällt auf, dass das Verhältnis der Energieaufnahme bei der von ihr ausgesendeten Strahlung extrem materialabhängig ist. Beim Holz ist es doppelt so hoch wie bei den Metallproben, was sinnvoll erscheint, wenn man bedenkt, dass es sich hierbei um eine Pflanzenlampe handelt.

#### Intermezzo

*Abbildung 13: Intermezzo*

Um zu zeigen, dass die unter stationären Bedingungen gemessenen Temperaturdifferenzen von dem Verhältnis der Oberfläche zum Volumen der Probekörper  unabhängig sind, sondern vielmehr die Energieabgabe an die Umluft nur von der Größe der Oberfläche und ihrer Farbe abhängt, wurde noch ein Zwischenversuch durchgeführt.

Der Aufbau, die Geräte und die Anordnung der Probekörper wurden aus den Vorversuchen beibehalten, und als Strahlungsquelle wurde für diesen und alle folgenden Versuchen ausschließlich die weiße Siccathermlampe benutzt. In Abbildung 13 sind die vier hier verwendeten Tafelelemente zu sehen. Die beiden im Bild links liegenden Platten sind bis auf die Tatsache, dass die hintere  die doppelte Dicke besitzt, identisch in Abmessungen und Material. Trotz des größeren Volumens stellte sich aufgrund der geringfügig größeren Oberfläche beim Hinteren eine etwas geringere Temperaturdifferenz (1 K) zur Umluft ein.

Bei den beiden rechts im Bild zu sehenden Tafelelementen bestand der einzige Unterschied darin, dass die Vordere komplett, und die Hintere nur auf der Oberseite schwarz gefärbt war. Erwartungsgemäß stellte sich bei dem ganz schwarzen Probekörper, wegen der höheren Temperaturabstrahlung von der Rückseite eine deutlich geringere (5 K)  Temperatur ein.

### Versuch zur Ermittlung der Eingangswerte

*Abbildung 14: Eingangswertversuch*

Um Aussagen über das Verhältnis der Absorptionsgrade der im Hauptversuch verwendeten Oberflächen zu erhalten und somit Eingangswerte für die Verifizierung des analytischen Weges zu bekommen, wurden zwei Tafelelemente aus demselben Material – 9schichtige senkrecht zueinander verleimte Furnierschichtholzplatten (Abmessungen 20*30*1,85 cm) - und den gleichen Oberflächen hergestellt.

Der Aufbau und die Geräte zur Temperaturerfassung sind analog zu den Vorversuchen. Auch hier wurden die Temperaturfühler ganzflächig anliegend auf der Unterseite der Tafelelemente mit Aluminiumkaschierband befestigt.

#### Ergebnisse

![Eingangswertversuch](images/eingangswertversuch.png)

*Abbildung 15: Ergebnis des Eingangswertversuchs*

Das gesuchte Verhältnis ergab, wie aus dem Diagramm (Abbildung 15) hervorgeht, zu 3,8. Dies bedeutet,  dass davon ausgegangen werden kann, dass der Energieabsorptionsgrad bezüglich der ja auch im Hauptversuch verwendeten Strahlung für die schwarzen Flächen 3,8mal so groß ist,  wie für die mit Spiegelfolie beklebten Flächen.

### Hauptversuch
In diesem Versuch soll gezeigt werden, wie sich die Energieaufnahme der Fassade bei unterschiedlichen Einstrahlwinkeln verhält. Dabei ist zu berücksichtigen, dass der Wärmestrom, der in die Fassade geht, bei konstanter Intensität des Strahlers sowohl abhängig ist vom Absorptionsgrad der jeweils beschienenen Fläche, als auch von dem Einstrahlwinkel.

Nach Kapitel 2 ergibt sich für die beiden Winkel 62° (Höchststand der Sonne im Sommer) und 15° (Tiefststand der Sonne im Winter) ein Verhältnis der wirksamen Intensitäten von I(15°)/I(62°) = 2,06. Eine darüber hinaus gehende Differenz der Energieaufnahme bei dem von uns gewählten Prototyp soll dargestellt werden

#### Beschreibung des Prototyps

Das für die Maximierung der Energiegewinne (bzw. deren optimale Umsetzung) geeignetste Material unserer geometrischen Struktur zu finden bedarf einer tiefgehenden Berücksichtigung der instationären Temperaturverläufe, die über die angesetzten Untersuchungen hinausgehen. Da Metall aufgrund seiner intensiven Wärmeabstrahlungsfähigkeit [11] und der daraus resultierenden,  im Vergleich zur angrenzenden Luft, niedrigeren Temperatur für alle Zeiträume ohne Sonneneinstrahlung ungeeignet erschien, wurde unter Berücksichtigung der in diesem Rahmen möglichen Herstellbarkeit das Material Holz in Form der oben beschriebenen Furnierschichtholzplatte gewählt.

Um die angestrebte einstrahlungswinkelabhängige Zweifarbigkeit  der Oberfläche ohne mechanische Bewegung, also durch eine rein statische Konstruktion, zu realisieren, wurde eine Zickzackstruktur gewählt. Diese ermöglicht dem Fassadenelement die Funktion, in Abhängigkeit des Sonnenstandes (Winter/Sommer), die Sonnenstrahlung über die verspiegelte auf die schwarze Fläche,  bzw. von der Wand weg zu reflektieren.

Ausgehend von der geographischen Lage Hannover (52° nördlicher  Breite) variiert der Sonnenhöhenwinkel zur Mittagszeit zwischen 15° und 62° im Verlauf eines Jahres. Ausschlaggebend für die Wahl der Winkelstellungen der Spiegelflächen war, dass die Sonnenstrahlung zur Mittagszeit drei Monate voll über den Spiegel aus unserer Fassade herausreflektiert  würde (im Sommer)  und drei Monate lang mit ihrer ganzen Intensität auf die schwarze Fläche fallen sollte (Abbildung 6).

In einem Zeitraum zwischen dem 21.06. des einen und dem 21.06. des darauffolgenden Jahres kann man von einem cosinus-förmigen Verlauf des jahreszeitabhängigen Sonnenhöchststandes ausgehen (Abbildung 16). Für die im Prototyp gewählte Spiegelstellung von 56° zur Vertikalen ergibt sich so für die Sonnenstrahlung zur Mittagszeit ein Zeitraum von 92 Tagen in dem die gesamte Strahlung auf die schwarzen Flächen der Fassade trifft (rot schraffiert). Hingegen wird an 86 Tagen des gewählten Zeitraumes die Sonneneinstrahlung vollständig von der Fassade weg reflektiert (blau schraffiert).

![Mittlere Sonnenhöhe](images/mittlere-sonnenhoehe.png)

*Abbildung 16: Mittaglicher Sonnenhöhenwinkel im Verlauf eines Jahres bei 51° N*

Um die Strahlen im Winter möglichst tief in das Profil einfallen zu lassen und die Gesamtaußenoberfläche möglichst gering zu halten, wurde der Winkel zwischen verspiegelter und schwarzer Fläche auf 90° festgelegt.

MDiese Winkelstellung ließ sich mit den zur Verfügung stehenden Werkzeugen nicht aus einer Platte herausarbeiten, so dass eine Leimfuge zwischen der Basisplatte und den extra dafür hergestellten Dreiecksleisten entstand. Ein weiterer sich daraus ergebender Vorteil war außerdem, dass durch 45°-Fräsungen in der Basisplatte die Temperaturfühler dichter unter der zu untersuchenden Oberfläche anordnet werden konnten.

*Abbildung 17: Anordnung der Messfühler im Prototyp*

*Abbildung 18: Die Wanne ist voll*

*Abbildung 19: Under Pressure*

Wie in Abbildung 17 zu erkennen ist, wurden zur besseren Temperaturleitung die bei eingelegten Temperaturfühlern verbleibenden Lufträume vor dem Verleimen mit Fett aufgefüllt.

Die nach dem Leimen entstandene Oberflächenstruktur wurde mit dem schwarzen Sprühlack gefärbt und anschließend auf den kürzeren Seiten (die um 56° zur Basisplatte geneigt sind) mit einer verspiegelten Klebefolie ( “X-film“ Nortmex) beklebt.

Die Abmessungen des Prototyps betragen 49 * 49 cm bei einer Gesamthöhe von 1,85 (Grundplattenstärke) + 1,05 (Höhe der Dreiecksleisten) = 2,9 cm. Die 49 cm Bauteillänge ergaben sich - ausgehend von ungefähr einem viertel Quadratmeter - als ganzzahliges Vielfaches der Grundseiten der Dreiecksleisten bei den oben begründeten Winkelstellungen.

#### Aufbau

*Abbildung 20: Anordnung der Lufttemperaturfühler*

Wie alle Vorversuche fanden auch die Hauptversuche auf dem Tisch in der Klimakammer statt. Variiert wurden die Winkel zwischen der Horizontalen und der Platte, wobei der Abstand zwischen der Lampe und dem Plattenschwerpunkt konstant 70 cm betrug. Da es sich bei der Strahlungsquelle um einen Punktstrahler handelte, war es nur in der Prototypmitte (vertikal unter der Lampe) der Fall, dass die Neigung der Platte zur Horizontalen auch dem Einstrahlwinkel auf dem Fassadenelement entsprach. Die innen liegenden Messfühler wurden deshalb wie in Abbildung 17 zu sehen um die Mittelachse der Platte angeordnet.

*Abbildung 21: Aufbau Hauptversuch, Einstrahlwinkel 62°*

*Abbildung 22: Ansicht Hauptversuch 15°*

*Abbildung 23: Seitenansicht Hauptversuch 15°*

#### Ergebnis

Da die Messergebnisse der einzelnen Fühler, die bei beiden Neigungen (15°/62°) - hervorgerufen durch den trichterförmige Strahlungsstrom des Punktstrahlers – unterschiedlichen Einstrahlungswinkel unterlagen, über das Quadrat der Entfernung zur Lampe hinaus differierten, zeigt sich deutlich, dass eine Fassadestruktur konstruiert wurde, deren Energieaufnahme einstrahlungswinkelabhängig ist. Je größer der Winkel zwischen der Flächennormalen des Fassadenelementes und der Einstrahlung, um so mehr wurde über die verspiegelte auf die schwarze Fläche projiziert und um so höhere Temperaturdifferenzen zur Außenluft konnten festgestellt werden (siehe Anhang Hauptversuch).

Der Vergleich des mittig gelegenen Fühlers (3) zwischen den beiden Winkelstellungen des Prototyps zeigt, dass unser Fassadenelement unter 15° Neigung in etwa die 11-fache Energiemenge aus dem Strahlungsstrom aufgenommen hat wie unter der um 62° zur Horizontalen geneigten Stellung:

![Ergebnis Hauptversuch](images/ergebnis-hauptversuch.png)

*Abbildung 24: Ergebnis Hauptversuch*

Unter Berücksichtigung der obenerwähnten winkelabhängigen Intensitätsverringerung bleibt als Absorptionsgradverhältnis der unterschiedlichen Einstrahlrichtungen ein Wert von 5,36.

## Zusammenfassung

### Vergleich Versuch/Rechnung

Werden nun in dem Excel-Programm die Abmessungen des Prototyps eingegeben und der Absorptionsgrad 0,8 der schwarzen Flächen angenommen, so ergibt sich der Absorptionsgrad der verspiegelten Flächen auf Grund des im Vorversuch ermittelten Verhältnisses von 3,8 zu 0,21. Für den Höhenwinkel von 62° am 21. Juni zur Mittagszeit errechnet das Programm für das um 90° gegen die Horizontale geneigte und nach Süden ausgerichtete Fassadenelement einen Wärmestrom von 22,81 Watt. Soll nun das Ergebnis für die um 15° gegen die Flächennormale geneigte Einstrahlrichtung ermittelt werden ohne jedoch die Intensität zu verändern, so ist nur der Neigungswinkel des Elementes zur Horizontalen um 47° auf 43° zu reduzieren. Daraus ergibt sich dann ergibt der absorbierte Energiestrom zu 171,06 Watt.

Das Verhältnis der Energieaufnahme ergibt sich also zu 7,5 im Vergleich zu dem im Versuch ermittelten Verhältnis von 11. Die Differenz zwischen diesen beiden liegt zum einen in der Vernachlässigung des diffusen Strahlungsanteils und zum anderen sicherlich an der Tatsache, dass beim Versuch zur Eingangsparameterermittlung der Fehler begangen wurde, die Anisotropie des verwendeten Materials zu vernachlässigen. Im Hauptversuch waren die schwarzen Flächen nämlich im Gegensatz zum Eingangsparameterversuch auf dem “Hirnholz“ und somit dürfte der Absorptionsfaktor der schwarzen Flächen im Hauptversuch also größer sein.

Wie in den Abbildungen 3 bis 5 zu erkennen ist, wurde der in den Grundgedanken erwähnte Effekt der Strahlungsgewinnumlagerung deutlich erreicht. Was bisher jedoch unberücksichtigt blieb, ist die Tatsache, dass senkrechte Südwände in diesen Breiten die höchste Energieaufnahme nicht am 21. Juni sondern im Frühling und Herbst erzielen.

## Ausblick

### Verwendungsmöglichkeiten

Das im Rahmen dieser Studienarbeit entwickelte Excel-Programm ermöglicht es dem Benutzer für jeden Standort auf der Erde die solaren Energiegewinne auf beliebig orientierten Flächen zu ermitteln, und diese dann mit dem für seine Bedürfnisse angepassten Zickzackprofil zu vergleichen.

### Weiterentwicklungsmöglichkeiten

Um die tatsächlich nutzbaren Energiegewinne noch realistischer für geplante Bauwerke zu prognostizieren, könnte unter Berücksichtigung der Wärmespeicherfähigkeit der instationäre Wärmestrom durch die Außenwand berücksichtigt werden.

Unter zur Hilfenahme von meteorologischen Daten (z. B. Testreferenzjahr [12]) könnten statt der hier verwendeten Intensitäten für klaren Himmel die Energiesummen brauchbarer gestaltet werden.

Auch die Berücksichtigung eventueller Nachbarbebauung bzw. anderer Verschattungsspender durch die Beschneidung des Sonnenlaufs wäre ein möglicher Entwicklungsschritt.

Die Höhenabhängigkeit der Solarstrahlung könnte mit formelmäßigen Beziehungen, wie sie in [13] zu finden sind, mit wenig Aufwand in das Programm integriert werden, da die Datenbank [14] mit knapp 6000 Städten Deutschlands neben den Längen- und Breitengraden auch die zugehörige Höhe über NN auf das Arbeitsblatt liefert.    

### Bedeutung der Ergebnisse

Aufgezeigt wurde also, dass durch das entwickelte Fassadenmodell das Verhältnis der Energieaufnahme deutlich höher gegenüber dem Verhältnis der dafür verwendeten Einzelflächen liegt. So ist es möglich, die Energiegewinne tatsächlich vorwiegend im Winter zu erhalten, im Sommer jedoch die Wärmeeinstrahlung von der Wand fern zu halten.

## Anhang

### Messergebnisse

#### Vorversuche

*Abbildung 25: Natriumhochdrucklampe*

*Abbildung 26: Siccatherm - Rot*

Fehler! Keine gültige Verknüpfung.

*Abbildung 27: Siccatherm - Weiß*

*Abbildung 28: TerrathermDeluxe*

#### Hauptversuch

*Abbildung 29: 15° Neigung des Prototyps gegen die Horizontale*

*Abbildung 30: 62° Neigung des Prototyps gegen die Horizontale*

### VBA Funktionen

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

## Abbildungsverzeichnis

Abbildung 1: Deklination und Rektaszension	8

Abbildung 2: Azimut und Höhe	9

Abbildung 3: Schnitt der Fassade	11

Abbildung 4: Draufsicht der Fassade	11

Abbildung 5: Wärmestrom in den Prototyp über Datum und Tageszeit	13

Abbildung 6: Wärmestrom auf Schwarz	14

Abbildung 7: Wärmestrom auf Spiegel	14

Abbildung 8: Natriumhochdrucklampe	15

Abbildung 9: Messwerterfassungsanlage	16

Abbildung 10: Aufbau Vorversuch	17

Abbildung 11: Befestigung der Thermoelemente	17

Abbildung 12: Spektralverteilung Sonnenlicht nach [9] und  Lampe laut Herstellerangaben	18

Abbildung 13: Intermezzo	19

Abbildung 14: Eingangswertversuch	20

Abbildung 15: Ergebnis des Eingangswertversuchs	20

Abbildung 16: Mittaglicher Sonnenhöhenwinkel im Verlauf eines Jahres bei 51° N	22

Abbildung 17: Anordnung der Messfühler im Prototyp	23

Abbildung 18: Die Wanne ist voll	23

Abbildung 19: Under Pressure	23

Abbildung 20: Anordnung der Lufttemperaturfühler	24

Abbildung 21: Aufbau Hauptversuch, Einstrahlwinkel 62°	25

Abbildung 22: Ansicht Hauptversuch 15°	25

Abbildung 23: Seitenansicht Hauptversuch 15°	25

Abbildung 24: Ergebnis Hauptversuch	26

Abbildung 25: Natriumhochdrucklampe	29

Abbildung 26: Siccatherm - Rot	29

Abbildung 27: Siccatherm - Weiß	30

Abbildung 28: TerrathermDeluxe	30

Abbildung 29: 15° Neigung des Prototyps gegen die Horizontale	31

Abbildung 30: 62° Neigung des Prototyps gegen die Horizontale	31

## Literaturverzeichnis

[1]	DIN 4108, “Wärmeschutz im Hochbau“, 1981

[2] 	DIN V 4108-6, “Berechnung des Jahresheizwärmebedarfs von Gebäuden“, 1995

[3] 	Wärmeschutzverordnung, 1995

[4]	VDI 2078, “Berechnung der Kühllast klimatisierter Räume“, 1996

[5] 	Kasten, F., “Parametrisierung der Globalstrahlung durch Bedeckungsgrad und Trübungsfaktor“, 1983

[6] 	dtv-Atlas zur Astronomie,  1990

[7] 	DIN 5030-2, “Spektrale Strahlungsmessung“ Tabelle 2, 1982

[8] 	DIN IEC 584, 1983

[9] 	DIN 67507, “Transmissions- und Durchlassgrade“, 1980

[10] 	DIN 1301, “Einheiten“, 1993

[11] 	Hohmann/Setzer, “Bauphysikalische Formeln und Tabellen“, 1997

[12] 	Blümel/Hollan/Kähler/Peter, “Entwicklung von Testreferenzjahren“, 1986

[13] 	Schmid, J., “Transparente Wärmedämmung“, 1995

[14] 	Deutscher Wetterdienst, Stationsdatenbank,
http://www.dwd.de/research/klis/daten/stationen/lex_mirakel.txt

[15]	Schultz, P., “Schallschutz, Wärmeschutz, Feuchteschutz und Brandschutz im Innenausbau“, 1996

[16]	Recknagel/Sprenger/Schramek, “Heizung + Klima Technik 2000“, 1999
