Instalation

Vorrausätzungen

1. HTTPS Zertifikat in SAP einbinden
2. Funktionsbaustein importieren
3. Extraktor importieren

HTTPS Zertifikat in SAP einbinden

01. In die Datenquelle navigieren
	a. Ausgangspunkt Startseite von SAP Signavio Process Mining
	b. Daten verwalten -> Verbindungen -> Verbindung auswählen (welche mit dem Prozess verknüpft ist) -> API endpoint Kopieren
02. Die API endpoint url in google Chrome öffnen
03. Links neben der URL auf das Schlosssymbol klicken
04. "Verbindung ist sicher" auswählen -> "Zertifikat ist gültig" auswählen
05. Im neuen Fenster in den Reiter Details wechseln
06. Button "Exportieren..." betätigen
07. Zertifikat an belibige Ort speichern
08. In das SAP System einloggen
09. Transaktion STRUST ausführen
10. Doppelklick auf "SSL-Client SSL-Client(Standard)
11. Unten links den Button "Zertifikat inportieren" betätigen (kleiner Pfeil nach oben)
12. Zertifikat aus Schritt 07 auswählen
	a. Nun werden die Informatione des Zertifikats in den Feldern über dem Button angezeigt
13. Button "In Zertifikat-Liste aufnehmen" betätigen (Wird als "In Zert.-Liste aufnehmen" angezeigt)
14. Nun kann eine Verbindung mittels HTTPS zwischen dem SAP System und Signavio aufgebaut werden

Funktionsbausteine importieren

1. Funktionsgruppe im SAP-System erstellen (Name sollte nach SAP Konventionen gewählt werden)
2. Funktionsgruppe aktivieren
3. Funktionsbaustein mit dem Namen "Z_PG_INGESTION_API" in der vorherigen Funktionsgruppe erstellen
4. Import Parameter festlegen:
	a. Parametername: TABLE_TO_SEND 	/ Typisierung: TYPE / Bezugstyp: STANDARD TABLE	/Otional: 
	b. Parametername: IS_EVENT_LOG 		/ Typisierung: TYPE / Bezugstyp: STRING		/Otional: X
	c. Parametername: PROCESS_NAME 		/ Typisierung: TYPE / Bezugstyp: STRING		/Otional: 
	d. Parametername: BUSINESS_OBJECT	/ Typisierung: TYPE / Bezugstyp: STRING		/Otional: X
5: Exportparameter festlegen:
	a. Parametername: MESSAGE		/ Typisierung: TYPE / Bezugstyp: STRING		/Otional: 
6. Quellcode aus der Datei "Z_PG_INGESTION_API.txt" unter Quellcode einfügen
7. Funktionsbaustein aktivieren



Extraktor J45 importieren

1. abap Programm mit dem Name "z_pg_oldenburg_evlog_j45_opt" erstellen
2. Includes erstellen
	a. Z_PG_OLDENBURG_GET_B_OPT
	b. Z_PG_OLDENBURG_GET_G_OPT
	c. Z_PG_OLDENBURG_GET_INVOICE_OPT
3. Programmcode aus txt Datein in Includes einfügen
	a. Z_PG_OLDENBURG_GET_B_OPT.txt -> Z_PG_OLDENBURG_GET_B_OPT
	b. Z_PG_OLDENBURG_GET_G_OPT.txt -> Z_PG_OLDENBURG_GET_G_OPT
	c. Z_PG_OLDENBURG_GET_INVOICE_OPT.txt -> Z_PG_OLDENBURG_GET_INVOICE_OPT
4. Programmcode aus der txt "z_pg_oldenburg_evlog_j45_opt.txt" in das abap Programm z_pg_oldenburg_evlog_j45_opt einfügen
5. den Aktivieren Button betätigen. Folgende Programme müssen bei dem aufkommenden Fenster selektiert werden
	a. Z_PG_OLDENBURG_GET_B_OPT
	b. Z_PG_OLDENBURG_GET_G_OPT
	c. Z_PG_OLDENBURG_GET_INVOICE_OPT
	d. z_pg_oldenburg_evlog_j45_opt
6. Prgramm übber die schaltfelche "direkt" oder mit der F8 Taste starten


Extraktor BD9 importieren

1. abap Programm mit dem Name "z_pg_oldenburg_evlog_bd9_opt" erstellen
2. Includes erstellen
	a. z_pg_oldenburg_get_change_opt
	b. z_pg_oldenburg_get_s_opt
	c. z_pg_oldenburg_get_d_opt
3. Programmcode aus txt Datein in Includes einfügen
	a. z_pg_oldenburg_get_change_opt.txt -> z_pg_oldenburg_get_change_opt
	b. z_pg_oldenburg_get_s_opt.txt -> z_pg_oldenburg_get_s_opt
	c. z_pg_oldenburg_get_d_opt.txt -> z_pg_oldenburg_get_d_opt
4. Programmcode aus der txt "z_pg_oldenburg_evlog_j45_opt.txt" in das abap Programm z_pg_oldenburg_evlog_j45_opt einfügen
5. den Aktivieren Button betätigen. Folgende Programme müssen bei dem aufkommenden Fenster selektiert werden
	a. z_pg_oldenburg_get_change_opt
	b. z_pg_oldenburg_get_s_opt
	c. z_pg_oldenburg_get_d_opt
	d. z_pg_oldenburg_evlog_bd9_opt
6. Prgramm übber die schaltfelche "direkt" oder mit der F8 Taste starten
	
