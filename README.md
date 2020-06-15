# M300
Modul 300 Dokumentation Jaron Alig ST17b
## LB2 Theorie
### Virtualisierung
#### Erklärung: Was ist eine Virtuele Machine (VM)
Eine VM verfügt im Vergleich zu einem physischen Computer keine eigene Hardware, sie wird, sondern mittels eines Hypervisors verwaltet.
Ein Hypervisor ist eine Softwarekomponente, die auf einem Computer oder Server
(Host-System), innerhalb eines vorhandenen Betriebssystems, ausgeführt wird. Er wird ebenfalls als Virtual Machine Monitor (VMM) bezeichnet. Er verteilt die Ressourcen des physischen Computers (resp. Die Ressourcen des Systems, dass die Virtuelle Maschinen hostet) auf die verschiedenen, laufenden VM’s. Der Hypervisor ist sozusagen der Vermittler zwischen den virtuellen Systemen auf einem Host-System und dem Host-System selbst.
Also kann ein Host-System, unabhängig vom Betriebssystem, eine virtuelle Maschine beheimaten.

Heisst ein Windows-System kann ein oder mehrere VM’s mit Linux-Betriebssysteme bereitstellen, sowie kann auch entgegengesetzt ein Linux-System ein oder mehrere VM’s mit Windows-Betriebssystemen bereitstellen.

#### Hypervisor
Ein Hypervisor stellt die Schnittstelle des Betriebssystems mit der darunter liegenden Hardware und der virtuellen Maschinen dar. Es wird in 2 Arten Hypervisoren unterschieden:

![](/Images/Theorie/hyperv.JPG)

Typ 1 (Hypervisor ist das Betriebssystem)
Typ 2 (Der Hypervisor kommuniziert mit dem Betriebssystem und den VMs auf dem Hostsystem)

#### Vollvirtualisierung

Eine Methode der Virtualisierung ist die Vollvirtualisierung, dabei werden die Hardwareressourcen für das Gast-System, durch eine Virtualisierungssoftware bereitgestellt. Die Ressourcen werden vollständig den virtuellen Maschinen zugewiesen. Zu den Ressourcen gehören CPU, Arbeitsspeicher, Laufwerke, Netzwerkkarten sowie auch das BIOS. Sie werden durch den Virtual Machine Monitor verwaltet. Der VMM, also der Hypervisor wird auf dem Host-Betriebssystem ausgeführt und reguliert die Verteilung der Hardwareressourcen des Host-Systems und die verschiedenen Gast-Systeme. Diese Gast-Systeme haben jedoch keinerlei Zugriff. Darum muss die Verteilung der Ressourcen über den Hypervisor mit höheren rechten stattfinden. Es wird dabei die Hardware jeder virtuellen Maschine emuliert. Es können, Dank der Emulation kann unter anderem mehrere unterschiedliche Netzwerkkarten zur Verfügung gestellt werden, diese müssen jedoch mit dem Gerät, wo das Host-System darauf am Laufen ist, übereinstimmen. So können Gast-Systeme mit altem Betriebssystem, die keine Unterstützung von moderner Hardware verfügen, weiterhin genutzt werden.

Es muss jedoch beachtet werden, dass alte Betriebssysteme nicht mehr mit Sicherheitsupdates versorgt werden, wie zum Beispiel Windows XP, daher sollte man aktuelle, moderne Betriebssysteme verwenden.

#### Host
Ein Host, (auf Deutsch Wirt, Gastgeber, Veranstalter) kann man als ein Computer, der Virtuelle Maschinen beheimatet, verstehen. Es wird grundsätzlich zwischen Desktop- und Server-Virtualisierung unterscheiden. Desktop-Virtualisierung wird ist im Betrieb, wenn man auf einem normalen Desktop-PC eine, oder mehrere virtuellen Maschinen laufen hat. Bei Server-Virtualisierung sind normalerweise deutlich mehr Ressourcen vorhanden, die den Virtuellen Maschinen zugeteilt werden können.

#### Kernel
Ein Kernel ist eine grundlegende Softwarekomponente in einem Betriebssystem, welcher die Verbindung zwischen der Hardware und der Anwendungsverwaltung auf einem Computer bildet.
Die Aufgabe von einem Kernel sind es unterandere Funktionen für eine Anwendungssoftware bereitzustellen. Damit diese Anwendungssoftware die nötigen Ressourcen von Hardwarekomponenten beziehen kann, wie unteranderem Prozessorleistung, Arbeitsspeicher und andere Komponenten. Damit die Anwendungssoftware eine Kommunikation mit den Hardwarekomponenten aufbauen kann, muss das Kernel beim Systemstart, also während des Bootvorgangs, direkt in den Arbeitsspeicher geladen werden. Dieser bietet dann in unterschiedlichen Abstraktionsschichten Schnittstellen für die Anwendersoftware an.
Es gibt unterschiedliche Kernel-Varianten. Damit das Kernel mit den Hardwarekomponenten kommunizieren kann, benötigt er bestimmte Gerätetreiber, diese sind je nach Produkt unterschiedlich. Es werden jedoch drei Kernel-Architekturen unterschieden, die unterschiedliche Merkmale aufweisen.

#### Microkernel
Der Mikrokernel besitzt nur die notwendigsten Funktionen zur Prozess- und Speicherverwaltung. Die Treiber befinden sich alle ausserhalb des Kernels. Die Treiber laufen auf Benutzerebene.

Dieses Kernel ermöglicht eine hohe Stabilität sowie auch mehr Sicherheit. Die Struktur des Kernels
macht jedoch einen kontinuierlichen Kontextwechsel8 notwendig, da für die
Ausführung der Treibersoftware immer zwischen Kernel- und Benutzerebene hin und
hergewechselt wird und erzeugt so einen höheren Datenaufwand. Das Design des Kernels ist im Vergleich zum Monolithischen Kernel schlanker, besitzt jedoch weniger Performance als der Monolithische Kernel. Die Micro-Kernel werden noch unteranderem bei den Betriebssystemen AmigaOS und Symbian OS, Minix und ChorusOS verwendet. Die Micro-Kernel werden auch im Bereich mit eingebetteten-Systeme und Spezialhardware gerne eingesetzt, z.B. in der Flug- und Fahrzeugindustrie.



### Vagrant
Vagrant ist ein effizientes Programm welches das erstellen von Virtuellen Machinen ermöglicht. Die Konfigurationen der Virtuellen Machine, werden von einem Vagrant-File angepasst.

Siehe (Command Sheet / Vagrant)

Für weitere Informationen zu Vagrant gehen sie zur offitielen Webseite von Vagrant.

Webseite: [Vagrant](https://www.vagrantup.com/)
### Git
### Systemsicherheit
### Markdown
Markdown ist eine aufzeichnungssprache die es vereinfacht, ein Format zu erstellen welches ohne konvertierung gelesen werden kann.
Dieses README.md wird mir Markdown bearbeitet. Für die bearbeitung habe ich ein Cheatsheet verwendet von Markdown.
#### Cheatsheet:
https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet

### Setup

Für das Projekt benötige ich Virtual Box, Vagrant und einen funktionalen Laptop


### Command Sheet
#### Docker

#### Vagrant


### Lernfortschritt
### Reflexion
