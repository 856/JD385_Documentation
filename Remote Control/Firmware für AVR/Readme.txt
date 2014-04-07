Anbei ein paar Programme, um die Fernbedienung JD-385 simulieren/empfangen
zu k�nnen.

Als Hardware sowohl f�r Sender als auch Empf�nger dient eine
kleine Schaltung mit einem ATMega328 (oder anderen, bitte im Programm
dann die SPI Belegung anpassen) und einem RFM70-Modul. Das Schaltbild 
ist in RFM70-rx-tx-sch.png zu finden.

Monitor.c dekodiert die Pakete der Fernsteuerung. Es wird nur Kanal 8 
empfangen. Da der Empf�nger sehr breitbandig ist, h�rt er auf dem
Labortisch auch den h�pfenden Sender zuverl�ssig.

RFM70-fb-rx.c ist ein Empf�nger, der auf den Sender synchronisiert und
ihm in der Frequenz folgt. �ber Pulsfolgen an einigen Pins (siehe
Programm) kann man verfolgen, ob es zu Aussetzern kommt. Das Folgen l�sst 
sich auch stoppen und man kann gezielt einzelne Kan�le einstellen.
Der Helptext im Programm sollte ausreichen.

RFM70-fb-tx.c ist ein Sender, der passend zu seiner Seriennummer h�pfen
kann, der aber auch auf festen Kan�len senden kann. Der Helptext zeigt
die m�glichen Funktionen.

RFM70.c is eine Lib f�r das Modul. Sie stammt aus dem Internet und wurde
f�r die Fernbedienung modifiziert und an einigen Stellen etwas umger�umt.
Nicht alle Funktionen sind getestet. Mit �berraschungen sollte man daher
rechnen.

Wer Fehler findet oder Anregungen hat, schickt mir bitte eine Mail. Dann
will ich das gern einarbeiten.

Der n�chste Schritt ist, das alles in den originalen Sender zu stopfen.
Sein HF-Modul ist zum RFM70 kompatibel (_nicht_ zum nRF24L01!).
