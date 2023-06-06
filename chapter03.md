# Analytischer Weg

Zur Praktischen Anwendung der in diesem Kapitel beschriebenen Größen können anhand des unter Visual Basic entwickelten Excel-Programms die einzelnen Schritte nachvollzogen werden. Die Inhalte der wichtigsten Funktionen sind als Listings im Anhang zu finden. Hier klicken:

Um eine möglichst allgemeine Aussage über die Jahres- und Tageszeitlich schwankenden Intensitäten der Sonne machen zu können, ist es zunächst einmal erforderlich, den aktuellen, bzw. auf eine Uhrzeit und einen Ort bezogenen, Sonnenstand zu ermitteln.

Die Berechnung der Energie, die von der Sonne auf eine Fassade abgegeben wird, ist abhängig vom Winkel zwischen Strahlungsquelle und Oberfläche und der wirksamen Intensität des Strahlers. Der Winkel wird mit Hilfe der Vektorrechnung im Horizontkoordinatensystem zwischen dem Richtungsvektor der Sonne und dem Normalenvektor der Bauteiloberfläche gebildet. Der Richtungsvektor der Sonne wird beschrieben durch einen Winkel in der Ebene des Horizonts gegen Süden, dieser Winkel heißt das Azimut a, und einem Winkel zwischen Sonne und Horizont, der Höhe h.

Der Normalenvektor einer zu betrachtenden Fläche wird auf die gleiche Weise ermittelt, durch die Verdrehung gegen Süden und die Neigung gegen den Horizont.

Die Intensität der Sonne die auf ein Bauteil wirkt, errechnet sich aus einem konstanten Wert für die außerhalb der Atmosphäre wirkende Strahlungsintensität, abgemindert durch eine jahreszeitlich schwankende Trübung der Atmosphäre.


## Sonnenstand

Zur Ermittlung des Sonnenstandes gibt es Tabellenwerke für die Parameter Azimut und Höhe in Abhängigkeit von Ort und Zeit auf der Erde. Im Rahmen der Simulation unter Excel werden die beiden Winkel jedoch berechnet, um sie allgemeingültiger handhaben zu können. Für die Berechnung wird zunächst einmal ein weiteres Koordinatensystem benötigt, welches die jahreszeitliche Veränderung des Sonnenstandes beschreibt - das sogenannte Äquatorkoordinatensystem.

### Deklination und Rektaszension der Sonne

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

### Azimut und Höhe der Sonne

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

### Orientierung der Fläche

Die Orientierung der Bauteiloberfläche wird durch die Drehung um die Z-Achse  von Süden nach Westen negativ, von Süden nach Osten positiv und die Neigung der Fläche gegen den Horizont  beschrieben.

## Berechnung der Fassade

### Abmessungen und Eigenschaften des Bauteils

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

### Abmessungen und Eigenschaften der Referenzflächen

| Wert | Abbr. | Beispiel |
| ---- | ----- | -------- |
| Neigung wie Bauteil |  | 90,00° |
| Drehung wie Bauteil |  | 0,00° |
| Fläche wie Bauteil |  | 0,24m² |
| **Schwarz** |  |  |
| Absorptionsgrad Schwarz | abSch | 0,80 |
| **Spiegel** |  |  |
| Absorptionsgrad Spiegel | abSp | 0,21 |

## Intensitäten der Sonne

### Globalstrahlung
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

## Strahlungsgewinne

Das Produkt der wirksamen Intensitäten auf den jeweiligen Flächen und ihrer Absorptionsgrade ergibt  die durch den Strahlungsstrom erzeugte Wärmestromdichte an der Bauteiloberfläche. Um den dadurch erzeugten Wärmestrom in ein Bauteil zu einem bestimmten Zeitpunkt zu erhalten, wird die Wärmestromdichte mit der jeweiligen zu diesem Zeitpunkt beschienen Fläche multipliziert. Das Ergebnis dieser Berechnung (durch die Funktion $E_In$) ist eine dreidimensionale Darstellung des vom Bauteil absorbierten Energiestroms in Abhängigkeit von Datum (X-Achse vom 01.01. bis 31.12.) und Uhrzeit (Y-Achse von 00:00 bis 24:00 Uhr) und wird beispielhaft für das im Hauptversuch verwendete Bauteil in Abbildung 3 gezeigt. Um nun einen Vergleich zu einer normalen ebenen Oberfläche herzustellen, werden neben dem Fassadenelement  auch noch eine schwarze sowie eine Spiegel-Referenzfläche berechnet, die sich vom eigentlichen Bauteil nur durch ihre konstanten Absorptionsgrade unterscheiden. Die Ausrichtung der Flächen ist die gleiche, ebenso Ort und Zeit. Ihre Wärmeströme zu bestimmten Zeitpunkten werden analog denen des zickzackprofilierten Bauteils im Programm angezeigt. Um sie qualitativ einstufen zu können ist ihre unterschiedliche Skalierung zu beachten.

![Prototyp](images/prototyp.png)

*Abbildung 5: Wärmestrom in den Prototyp über Datum und Tageszeit*

![Schwarz](images/schwarz.png)

*Abbildung 6: Wärmestrom auf Schwarz*

![Weiß](images/weiss.png)

*Abbildung 7: Wärmestrom auf Spiegel*
