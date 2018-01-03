# templates Ordner  

Speicherort für Konfig Dateien, welche vor dem Übertragen auf den Zielserver mittels [Jinja2](http://jinja.pocoo.org/docs/2.9/) bearbeitet werden. 

## Beispiele

Wenn z. B. die Apache Konfiguration auf mehrere Stages ausgerollt werden soll, wird im grunde ein identischer Aufbau der Konfig Files verwendet und lediglich einzelne Werte angepasst wie z. B. der Servername (welcher je nach Maschine unterschiedlich ist).

## Verwendung

Dateien die im Templates Ordner liegen können mittels [Jinja2](http://jinja.pocoo.org/docs/2.9/) bearbeitet und danach ausgeliefert werden. 

Daher sind an zwei Stellen anpassungen notwendig:

### In der Rolle



Beispiel:

>-  template:
>     src: /mytemplates/foo.j2
>     dest: /etc/file.conf
>     owner: bin
>     group: wheel
>     mode: 0644

Nutzt das Jinja Template /mytemplates/foo.j2 und übersetzt es in ein Konfig File inkl. übertrag auf Ziel VM

### Im Konfig File 


Beispiel:

> Listen {{ servip }}:443
> <VirtualHost {{servip}}:443>

Auschnitt einer Apache Konfig. Die Variable servip wird vor der Übertragung durch Jinja eingesetzt und dann wird das File ausgerollt. 
