# File Ordner  

Speicherort für Dateien, welche in der Ansible Rolle benötigt werden, jedoch nicht von Ansible selber bearbeitet werden. 

## Beispiele

* Binaries (tomcat.tar.gz, mvn.tar.gz,...)
* Pakete (RPM, ...)

## Verwendung

Die Dateien werden einfach in den file Ordner gelegt. Danach kann auf sie aus der Ansible Rolle referenziert werden. 
Es wird keine main.yml benötigt