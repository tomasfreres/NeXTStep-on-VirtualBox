# NeXTStep-on-VirtualBox
Install NeXTStep / OPENStep on VirtualBox

Wer sich ein wenig mit Computergeschichte auseinandersetzt, der wird wohl oder übel mal der Firma NeXT und ihrem Betriebssystem NeXTSTEP über den Weg gelaufen sein. Tim Berners Lee hat beispielsweise das World Wide Web (später bekannt als das Internet), den ersten Webserver und Browser der Welt unter NeXTSTEP entwickelt. Das Betriebssystem war für die damalige Zeit sehr fortschrittlich und bot bereits im Jahr 1989 Features, welche von anderen Betriebssystementwicklern erst Jahre später aufgegriffen worden sind.

Zudem wurde NeXTSTEP, zu dem Zeitpunkt OpenStep genannt, nach der Übernahme von NeXT durch Apple Basis für die Neuentwicklung MacOS X. Die OpenStep-API wurde zu Cocoa, welches bis Heute die Basis für  die meisten macOS- und iOS-Apps bildet. Folgende Anleitung zeigt nun, welche Schritt zur Installation in einer virtuellen Umgebung wie VirtualBox nötig sind:

VirtualBox auf macOS mittels Homebrew installieren:
`brew cask install virtualbox`

VirtualBox auf Linux mittels apt-get installieren:
`sudo apt-get install virtualbox virtualbox-qt virtualbox-dkms`

VirtualBox auf Windows mittels Chocolatey installieren:
`choco install virtualbox`


## VirtualBox

Zuerst sollte eine virtuelle Umgebung installiert sein. VirtualBox ist ein kostenloses Tool, welches für dieses Tutorial auch genutzt wird. VirtualBox ist sowohl für Windows, macOS als auch Linux-basierte Betriebssysteme verfügbar.

Die virtuelle Maschine muss über 1 Prozessorkern verfügen, da es damals noch keine Multitore-Prozessoren gab. Es sollten mindestens 64 Megabyte Arbeitsspeicher zur Verfügung gestellt werden, für das Tutorial verwenden wir 128 Megabyte. Das System benötigt eine per IDE angebundene Festplatte als Primary Master und ein optisches Laufwerk als Primary Slave. Zudem wird ein Diskettenlaufwerk benötigt. Als Größe der Festplatte werden 2 GB angegeben.


![VM Setup](/images/image1.png)
![VM Setup](/images/image2.png)
![VM Setup](/images/image6.png)

Ist die virtuelle Maschine aufgesetzt, so benötigen wir nur noch die entsprechenden Dateien:

Install_Floppy.img

Driver_Floppy.img

OpenStep-Install-4.2.iso

OpenStep-4.2-Patch-CD.iso

## Die Installaion

Zum Start muss die Install-Floppy.img im Diskettenlaufwerk und die OpenStep-Install-4.2.iso Datei im (virtuellen) optischen Laufwerk eingelegt sein. Die virtuelle Maschine muss nun gebootet werden. Es erscheint folgender Bootscreen, auf dem nichts eingegeben werden soll. Hier muss man einfach nur abwarten. 

![VM Setup](/images/image8.png)

Im nächsten Schritt wählen wir die Sprache für das Setup aus. Hier kann auch Deutsch ausgewählt werden, in unserem Falle wählen wir aber Englisch mit der Eingabe der 1 aus. Mit Enter wird bestätigt.

![VM Setup](/images/image10.png)


Nachdem bestätigt wurde fordert einen das System auf, die Driver_Floppy.img in das System einzulegen. Die Install_Floppy.img wird über das obere Menü der VirtualBox ausgeworfen und das andere Image eingelegt. Ist dies erfolgt, bestätigt man das Ganze mit Enter.

![VM Setup](/images/image13.png)

Wurde die Driver_Floppy.img korrekt eingelesen, kommt als nächstes ein Auswahlscreen für die Festplattentreiber. Hier geben wir 7 ein und bestätigen mit Enter. Beim nächsten Screen geben wir erneut 7 ein und bestätigen das mit Enter. Auf dem dritten Screen geben wir nun 5 ein und bestätigen das mit Enter. 

Diese Auswahl wird dann erneut kommen, wo wir die Eingaben wiederholen (7 -> Enter, 7 -> Enter, 5 -> Enter). Ist alles korrekt gelaufen, erscheint folgender Screen:

![VM Setup](/images/image16.png)

Hier geben wir nun die 1 ein und bestätigen diese erneut mit Enter. 

Ist bis hier alles korrekt gelaufen, wechseln wir bereits in den grafischen Modus des Setups. Ist dies durchgelaufen werden wir gefragt, ob wir das System auf der 2 GB großen HDD installieren möchten. Dies bestätigen wir in dem wir 1 eintippen und danach Enter. Danach wieder mit 1 und Enter bestätigen. Danach muss die Diskette entfernt werden, da es sonst Fehler beim weiteren Setup gibt. Ist dies geschehen wieder mit Enter bestätigen. 

![VM Setup](/images/image18.png)
![VM Setup](/images/image19.png)

Nach dem Reboot benötigt OpenStep bzw. NeXTSTEP erneut die Treiber-Diskette. Wir legen sie ein und bestätigen mit 1 und Enter. Die grafische Oberfläche wird nun laden. Diese begrüßt uns erstmal mit 2 Fehlermeldungen, die wir aber beide mit OK bestätigen. 

Es erscheint ein Konfigurationsdialog, den wir aber ignorieren. Wir bestätigen mit Save und danach Save Anyway um das Setup weiterzuführen. Danach kommt ein Fenster, bei dem wir auswählen können, was installiert werden soll. Hier können alle nicht benötigten Sprachen abgewählt werden. Wer später das System auf Deutsch nutzen möchte, kann dies ausgewählt lassen. Ist dies getan wird mit dem Klick auf Install die Installation gestartet. Dies kann nun einige Zeit dauern.

![VM Setup](/images/image29.png)

Nachdem die Installation durchgeführt wurde, fordert OpenStep uns zum Rebooten auf. Bevor wir das aber bestätigen, entfernen wir wieder die Treiber-Diskette. Danach bestätigen wir mit Restart. 

Nachdem die Maschine neu gestartet wurde, werden wir aufgefordert die Sprache und das Tastaturlayout auszuwählen. In unserem Falle nehmen wir Englisch und das Deutsche Tastaturlayout. Hier fragt das System nochmal nach, ob diese ungewöhnliche Kombination wirklich gewollt ist. Mit OK bestätigen wir.

![VM Setup](/images/image31.png)

Ist das geschehen landen wir auch schon auf dem OpenStep Desktop. Rechts befindet sich das Dock, links eine Menüleiste und in der Mitte unser Dateibrowser namens "File Viewer". Da es aber Schwarz-Weiß ist und die Auflösung auch nicht befriedigend, werden wir nun den Patch installieren. 

Hierfür werfen wir über die Menüleiste Disk --> Eject die bestehende CD aus und legen dann über VirtualBox die OpenStep-4.2-Patch-CD.iso ein. Wird sie nun im File Viewer angezeigt, können wir per Doppelklick auf den Inhalt zugreifen. 

Hier wählen wir alle Dateien aus und ziehen sie per Drag & Drop auf den "me" Ordner, unser Homeverzeichnis. Es wird keinen Fortschrittsbalken geben. Per Doppelklick auf das Homeverzeichnis sehen wir auch hier den Inhalt. Sobald alle Dateien nicht mehr ausgebaut sind, ist der Kopiervorgang abgeschlossen. 

![VM Setup](/images/image35.png)

Nun muss die Datei os42machuserpatch4.tar per Doppelklick entpackt werden. Auch hier gibt es keinen Fortschrittsbalken. Sobald die neue Datei OS42MachUserPatch4.pkg nicht mehr ausgegraut ist, können wir das Endpack-Programm über die Menüleiste mit einem Klick auf Quit schließen. 

Danach klicken wir auf das Computer Symbol und gehen in den Ordner NextApps. Dort scrollen wir herunter und starten die Terminal Applikation über einen Doppelklick. Ist sie gestartet geben wir folgende Befehle ein:

`su /NextAdmin/Installer.app/Installer /me/OS42MachUserPatch4.pkg`

![VM Setup](/images/image42.png)

Nachdem der zweite Befehl mit Enter bestätigt wurde, ploppt ein Installer-Fenster auf, welches wir mit Klick auf Install ausführen. Ist die Installation durchgelaufen, schließen wir das Programm mit Quittung über die Menüleiste. Sind wir wieder im Workspace-Menü, klicken wir auf Log Out und danach auf Power Off. Die Maschine wird nun herunterfahren. Wenn OpenStep uns sagt, dass es nun sicher ist auszuschalten starten wir die Maschine neu. 

![VM Setup](/images/image45.png)

Ist das System nun wieder gebootet, klicken wir erneut auf das Computer-Icon im File Viewer. Dort navigieren wir in den NextAdmin Ordner und starten die Configure.app per Doppelklick. Dort klicken wir auf das Monitor-Icon und bekommen ein Fenster, bei dem wir die Display Devices hinzufügen können. Dort scrollen wir herunter bis VESA VBE 2.0 auftaucht. Diesen wählen wir aus und klicken auf Add. Danach klicken wir auf Done und dann Save. 

Ist das geschehen, starten wir die Maschine über das Workspace Menü neu. War dies erfolgreich begrüßt uns das System endlich in Farbe.

Da die Auflösung immer noch nicht befriedigend ist, gehen wir wieder in die Configure.app, wählen dort wieder das Display Icon und klicken den Select Button im Display Mode Bereich an. Dort wählen wir dann unsere gewünschte Auflösung aus. Mit OK und Done bestätigen wir die Auswahl. Danach muss die Maschine wieder neugestartet werden.

Nach dem Neustart ist die virtuelle Maschine mit NeXTSTEP bzw. OpenStep vollständig aufgesetzt. 

![VM Setup](/images/image52.png)
