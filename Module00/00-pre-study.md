### 1. Meine IoT-Idee: Nachtbeleuchtung im Pflegeheim

Im Video fand ich die Hausautomation im Pflegeheim besonders interessant, weil man damit Menschen im Alltag helfen kann.

Eine mögliche Umsetzung wäre eine automatische Nachtbeleuchtung. Ein Bewegungssensor erkennt, wenn ein Bewohner nachts aufsteht. Ein Helligkeitssensor prüft zusätzlich, ob es dunkel ist. Wenn beide Bedingungen erfüllt sind, schaltet eine lokale Steuerung eine dezente Beleuchtung ein. Das könnte den Bewohnern helfen, sich nachts besser zu orientieren, ohne selbst einen Lichtschalter suchen zu müssen.

Die Bewegungs- und Helligkeitssensoren müssten ihre Messwerte über das lokale Netzwerk an die Steuerung senden. Diese würde anschließend einen Schaltbefehl an die Beleuchtung übertragen. Die Funktion sollte auch ohne Internetverbindung verfügbar sein.

### 2. IP-Adresse und Subnetzmaske

Eine IP-Adresse adressiert eine Netzwerkschnittstelle eines Geräts. Die Subnetzmaske legt fest, welcher Teil der IP-Adresse zum Netzwerk gehört und welcher Teil das Gerät innerhalb dieses Netzes bezeichnet.

Bei der Subnetzmaske 255.255.255.0, kurz /24, bilden die ersten drei Zahlenblöcke den Netzanteil. Ein Laptop mit 192.168.10.20/24 und ein Sensor mit 192.168.10.80/24 befinden sich daher im selben Subnetz.

Zwei unterschiedliche Geräte dürfen im selben Subnetz nicht dieselbe IP-Adresse verwenden, weil dadurch ein Adresskonflikt entsteht. Daten können dann beim falschen Gerät ankommen oder die Kommunikation kann ausfallen.

### 3. OSI-Modell und TCP/IP in der Praxis

Das OSI-Modell beschreibt die Netzwerkkommunikation in sieben Schichten. Das TCP/IP-Modell verwendet vier Schichten und passt häufig besser zur praktischen Umsetzung. Die Aufgaben der oberen drei OSI-Schichten hängen eng zusammen und werden oft gemeinsam von einer Anwendung und ihren Bibliotheken übernommen. Deshalb fasst TCP/IP sie in einer Anwendungsschicht zusammen. Die Aufgaben selbst bleiben erhalten.

Die Grenzen zwischen den Schichten sind in der Praxis nicht immer eindeutig. Ein Router verwendet beispielsweise IP-Adressen für die Weiterleitung, kann aber zusätzlich TCP- oder UDP-Ports für Firewallregeln auswerten. Das OSI-Modell hilft dabei, diese unterschiedlichen Funktionen einzuordnen.

Bei IoT-Geräten sind Energie, Rechenleistung und Bandbreite häufig begrenzt. Überträgt ein Sensor nur einen kleinen Messwert, können die zusätzlichen Protokollheader im Verhältnis zu den Nutzdaten groß sein. Unnötige Protokollschichten oder doppelt umgesetzte Funktionen verursachen zusätzlichen Übertragungs- und Verarbeitungsaufwand. Deshalb sollten Protokolle und Funktionen passend zur Aufgabe gewählt werden.

Dieser Aufwand entsteht durch die tatsächlich eingesetzten Protokolle und ihre Umsetzung. Allein die Einteilung in vier statt sieben Schichten macht die Datenübertragung nicht schneller oder sparsamer.



