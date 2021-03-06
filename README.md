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
![](/Images/netzwerkp.PNG)


Für das Projekt benötige ich Virtual Box, Vagrant und einen funktionalen Laptop


#### Reverse-Proxy
The REverse Proxy is managed by IAM01 Server which allows the Web server to be accessed by outside connection:
Test connection by calling up http://localhost:8080/

#### Firewall
| Server | Firewall Rules |
|:-:|-|
| web01 | sudo ufw allow 80/tcp<br>sudo ufw allow 22/tcp |
| iam01 | sudo ufw allow 22/tcp<br>sudo ufw allow from 192.168.11.101 to any port 80 |
| db01 | sudo ufw allow 22/tcp<br>sudo ufw allow from 192.168.11.101 to any port 3306 |

### Test cases LB2
| Nr. | Beschreibung | Check | Soll Stand | Ist Stand | OK? |
|:-:|-|-|-|-|:-:|
| 1 | `web` should be able to ping `db` on port `3306` | `nc -vz 192.168.11.100 PORT: 3306` | `Connection to 192.168.11.100 PORT: 3306 [tcp/mysql] Failed` | `No Route to Host!` | Y |
| 2 | `db` should NOT be able to ping `iam` on port `80` | `nc -vz 192.168.11.102 PORT: 80` | `nc: connect to 192.168.11.102 PORT: 80 (tcp) failed: No Rout to Host` | `No Route to Host!` | Y |
| 3 | `web01` should NOT be able to ping `iam01` on port `80` | `nc -vz 192.168.11.102 PORT: 80` | `Connection to 192.168.11.102 PORT: 80 [tcp/http] Failed!` | `No Route to Host!` | Y |
| 4 | Check if reverse proxy works | Visiting [localhost:8080/](http://localhost:8080/) should show the default apache2 site | Show apache2 default page | Show apache2 default page | Y |
| 5 | Check if `Adminer` works | Open [localhost:8080/adminer.php](http://localhost:8080/adminer.php) <br>Presents Table to Select Log-In. | Presented with the view to select the `data` table. | Presented with the view to select the `data` table. | Y |
| 6 | `iam` should NOT be able to ping `db` on port `3306` | `nc -vz 192.168.11.100 PORT: 3306` | `nc: connect to 192.168.11.100 PORT: 3306 (tcp) failed: No Route to Host` | ` No Route to Host!` | Y |


Adminer.php (http://localhost:8080/adminer.php)
  - Server: `192.168.11.100`
  - Username: `root`
  - Password: `admin`
  - Database: `proposals`.
## LB3

### Docker
Docker ist eine Software zur Isolierung von Anwendungen mit Containervirtualisierung. Die Software benötigt keine Lizenzen.

Docker nahm damals die bestehende Linux-Containertechnologie auf und verpackte und erweiterte sie in vielerlei Hinsicht – vor allem durch portable Images und eine benutzerfreundliche Schnittstelle.

### Containisierung
Das Containerkonzept ist eine Virtualisierungstechnik, die Anwendungen auf einem Host-System voneinander isoliert. Im Vergleich zu virtuellen Maschinen werden nicht komplette Rechner inklusive Betriebssystem virtualisiert, sondern nur die zur Ausführung der Anwendungen benötigten Laufzeitumgebungen mit ihren Ressourcen wie Anwendungscode, Bibliotheken oder Konfigurationen. Das Containerformat ist genau definiert. Container inklusive ihrer Anwendungen und Laufzeitumgebung lassen sich in Form einer Datei leicht auf andere Host-Systeme übertragen.

### Dockerfile 
Ein Dockerfile ist eine Textdatei mit einer Reihe von Schritten, die genutzt werden können, um ein Docker-Image zu erzeugen.

Dazu wird zuerst ein Verzeichnis erstellt und darin eine Datei mit Namen "Dockerfile".

### Elastalert
Für das Projekt habe ich mit hilfe von docker-compose.yml file einen Multi node Cluster erstellt. dieser sollte Information an Kibana weitergeben, welcher unter der adresse (localhost:5601) Dieser ist aber nicht bereit um informationen entgegenzunehmen.

### Elasticsearch
Basierend auf Apache Lucene – einer bewährten Such-Engine für Java – stellt Elasticsearch eine Vielzahl von Möglichkeiten für Freitextabfragen, für die Indexierung von Daten, sowie für die Administration über eine HTTP / RESTful Schnittstelle zur Verfügung. Darüber hinaus erweitert Elasticsearch Lucene mit zusätzlichen Features wie Clustering und Monitoring. Auch erweiterte Werkzeuge für die Auswertung und Analyse der indexierten Daten (z.B. Aggregationen) werden zur Verfügung gestellt. Eines der mächtigsten Features ist die Cluster-Fähigkeit von Elasticsearch. Dabei werden die Such-Indizes auf mehrere Elasticsearch-Knoten verteilt, um eine bessere Suchperformance bei grosser Abfragelast sowie bessere Verfügbarkeit und Ausfallsicherheit zu erreichen. Trotz des grossen Funktionsumfanges von Elasticsearch legen die Entwickler viel Wert auf einfache Bedienung. So lässt sich beispielsweise mittels Autodiscovery automatisch ein Such-Cluster formieren: Sobald neue Knoten im Netzwerk vorhanden sind, werden diese automatisch in den Cluster-Verbund aufgenommen.

### Test cases LB3
| Nr. | Beschreibung | Check | Soll Stand | Ist Stand | OK? |
|:-:|-|-|-|-|:-:|
| 1 | `docker-compose up should start up the compose file and start the node cluster | sudo docker-compose up | `kb01 node is running` | `kb01 node is running but cannot connect to net` | Y |
| 2 | `docker compose should set up kibana server` | `sudo docker-compose up` | `Kibana Server is running via (localhost:5601)` | `Kibana server can connect but doesn't display any info` | Y |
| 3 | `docker containers should be runni g from tests` | `docker build .` | `docker containers are running images used in experiment` | `docker containers are running images used in experiment` | Y |
| 4 | nginx webserver should work | sudo docker build . | Starterpage for nginx is should show by calling up (localhost:8080)  | nginx starter webpage is displyed when calling up (localhost:8080) | Y |

### Command Sheet
#### Docker

> docker ps -a				List all Containers active & inactive

> docker run				create and run docker

> docker build .				uses docker image withing directory	

> docker pull				pulls docker image from repository

> docker run --name jaron container ID	starts docker container with folowing name / ID

> docker rm name				kills docker container

> docker stop				stops active running container	

> docker image ls				lists all docker images

> docker run -d -P --name jaron nginx	creates docker container with nginx running

> docker-machine ip default		sets ip from container to default

> docker ps				lists all active docker container

> docker network is			lists all networks

> docker network create			create new network

> docker network rm			removes network

> docker run -i --expose=22 ID		 

> docker run -d -P --name cname image	REAL CONTAINER CREATE

> docker port CName			show ports used by docker container

> docker exec -it CName /bin/bash		enter Docker container and leave with exit

> docker-machine ip default		make docker container



#### Vagrant
> <"vagrant Init">  -->    #Erstellt VM

> <"vagrant up">    -->    #Startet VM

> <"vagrant ssh">   -->    #Verbindet sich per SSH zur VM

> <"vagrant status"> -->   #Zeigt Status der VM an

> <"vagrant port">  -->    #Zeigt weitergeleitete Ports der VM an

> <"vagrant halt">  -->    #stoppt die VM

> <"vagrant destroy"> -->  #Zerstört / löscht die VM

### Lernfortschritt LB2
Ich habe viel über Vagrant gelernt, welch ich nicht mal wusste wie es genau funktioniert. Ich fand es sehr gut das wir das Thema bearbeitet hatten. Somit ist das erstellen von VM's einiges EInfacher, da ich nicht jede VM selber beim erstellen konfigurieren muss. 
### Reflexion LB2
In diesem Projekt konnte ich viel über die Virtualisierung lernen, und wie es funktionert. Vagrant was am anfang sehr verwirrend, da ich nicht genau verstanden habe, wie ich das Vagrantfile richtig bearbeiten muss. Nachdem ich ein paar examples angeschaut habe, konnte ich festellen, was genau für das Projekt gebraucht wird. Ich habe somit 3 Maschinen erstellt. Web Server / IAM Server / Database Server. Nach dem konnte ich das reverse proxy problem beheben.

### Lernfortschritt LB3
Ich habe in der LB3 viel über die Containisierung gelernt. Ich konnte dieses Wissen somit auch in meinem Betrieb anwenden. Ich habe somit eine Golang Rest API ertellt.
Das umsetzen der Docker Theorie war ein sehr grosser Vorteil. 

### Reflexion LB3
In diesem Projekt konnte ich viel über das Docker Container System lernen, welches 
