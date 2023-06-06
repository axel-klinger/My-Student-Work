# Grundgedanke

In der vorliegenden Arbeit wird die von der Sonne auf die nicht transparente (opake) Gebäudehülle wirkende Energie untersucht.
Das Ziel des Optimierungsansatzes ist es, einen möglichst großen Teil dieser Energie in der Heizperiode zu nutzen und im Sommer abzuführen. Durch die Verschiebung der Oberflächentemperatur einer Fassade in Richtung Innenraumtemperatur ergibt sich ein geringeres Energiegefälle in der Wand, was zu einer geringeren Ausgleichsleistung durch Klimaanlage bzw. Heizung führt.

Mit den von uns im Rahmen dieser Studienarbeit ausgeführten Versuchen soll  der Berechnungsalgorithmus für die sonneneinstrahlungswinkelabhängige Energieaufnahme  unser geometrischen Struktur verifiziert werden. Als Ansatz müssen dafür Angaben für das Verhältnis der Absorptionsgrade der von uns verwendeten Oberflächen durch Vorversuche gewonnen werden.  

In wie weit sich die Transmissionsverluste, bzw. die äußeren Kühllasten durch opake Außenbauteile zugunsten der Gesamtenergiebilanz eines Hochbaus durch eine zur Sonne optimierte Fassade, reduzieren lassen, soll prognostiziert werden.

## Winterliche Nutzung

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

## Sommerlicher Wärmeschutz

In den Sommermonaten gilt es im Gegensatz zum Winter, die einfallende Wärmeenergie möglichst gering zu halten. Die Grundlagen und Berechnungsverfahren für den sommerlichen Wärmeschutz sind unter anderem in [1] und [4] zu finden. Nach [4] unterteilt man bei der Berechnung der anfallenden Kühllast, zur Dimensionierung etwaiger Klimaanlagen beispielsweise, die innere und äußere. Letztere umfasst die über die Gebäudeumschließungsfläche eintretende Energie, die für die Untersuchung von besonderem Interesse ist. Die Strahlungsbeeinflussung der Außenoberfläche im Sommerhalbjahr gering zu halten und die dadurch anfallenden (wenn auch vergleichsweise geringen) zusätzlichen Kühllasten zu minimieren ist Ziel dieser Untersuchung.

Nach dem Kurzverfahren der [4] werden Bauartklassen (Dämpfungsfaktoren und Zeitverschiebungen charakterisieren diese), so wie Flächenorientierungs- und tageszeitabhängig äquivalente Temperaturdifferenzen verwendet, um den Wärmestrom durch die Außenwände zu bestimmen. In die äquivalente Temperaturdifferenz ist dabei nach einem Verfahren von G. Nehrling die Lösung des instationären Wärmedurchgangs durch äußere Raumumschließungsflächen eingearbeitet. Sie berücksichtigt des weiteren metrologische Einflussfaktoren wie die Ausstrahlung der Fläche gegen die Atmosphäre und die atmosphärische Gegenstrahlung.

Für diese Betrachtungen soll aber der,  die Speicherfähigkeit der Baustoffes vernachlässigende,  Wärmestrom unter stationären Bedingungen eine ausreichende Basis darstellen.

## Randbedingungen der Untersuchung
Zur Untersuchung der Energieaufnahme einer Fassade sind diverse Einflussfaktoren von Bedeutung. Da im Rahmen dieser Studienarbeit nicht alle Größen berücksichtigt werden können, werden folgende Parameter konstant gesetzt:

* Klarer Himmel
* Kein Wind und kein Niederschlag
* Auswirkungen von Luftfeuchtigkeit und Luftdruck auf die Intensität bleiben unberücksichtigt
* Ausschließlich Energiestrom in das Fassadenelement
* Vernachlässigung der thermischen Längenänderungen und daraus entstehende erhöhte Temperaturspannungen
* Kein diffuser Strahlungsanteil
* Stationär
* Sonnenäquivalenz im Rahmen des im Vorversuch angewandten Materials (s. 3.1)
