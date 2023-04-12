# 3D Context Creator

![](<../../.gitbook/assets/3D Context Creator_new.gif>)

## Worum handelt es sich?

3D Context Creator ist ein benutzerfreundliches Plugin, mit dem Gebäude im 3D-Kontext in FormIt erstellt werden können. 

Dieses Plugin kann Ihnen helfen, Ihren Projektstandort im Umgebungskontext zu visualisieren und bereits in der frühen Phase des Entwurfsprozesses fundierte Entscheidungen zu treffen.

Das Plugin ruft Daten aus [Open Street Map](https://www.openstreetmap.org/about) ab, um sie in FormIt-Geometrien zu transformieren. Der Quellcode für dieses Plugin ist auf [Github](https://github.com/matterlab-co/FormIt-Context-Plugin) verfügbar.

## Wie wird es verwendet?

Um es zu installieren, aktivieren Sie einfach den Schalter des Plugins im Plugin-Manager, wie Sie es bei jedem anderen Plugin tun würden.

![](../../.gitbook/assets/contextcreator3.png)

Nach dem Aktivieren sollte das Plugin auf der rechten Seite der App angezeigt werden und einsatzbereit sein.

![](<../../.gitbook/assets/3D Context Creator new_no location (1).png>)

Wenn Ihr Gebiet noch keinen Standort hat, können Sie auf die Verknüpfung **Standort festlegen...** klicken, um einen Standort festzulegen und die Begrenzung zu definieren, die zum Erstellen von 3D-Kontext verwendet wird.

Nachdem Sie Ihren Standort festgelegt haben, wird der 3D Context Creator mit dem aktuellen Standort aktualisiert, und die Schaltfläche wird aktiviert:

![](<../../.gitbook/assets/3D Context Creator new_with location.png>)

Der 3D Context Creator verwendet einfach die Grenzen des Satellitenbilds, um 3D-Kontext zu generieren. Sie müssen nur auf **Generate 3D Context** (3D-Kontext generieren) klicken.

Je nach den Grenzen des Satellitenbilds und der Komplexität der Gebäude kann die Erstellung einige Sekunden dauern.

Die Gebäude im 3D-Kontext werden automatisch in ein Gruppenexemplar eingefügt und auf einem Layer mit der Bezeichnung "Context Buildings" platziert. Sie können die Sichtbarkeit des Kontexts mit diesem Layer umschalten.

![](<../../.gitbook/assets/3D Context Creator_layers.png>)

![](<../../.gitbook/assets/3D Context Creator_NYC.png>)

Wenn Sie später beschließen, Ihren Standort zu ändern oder den Umfang des Satellitenbilds anzupassen, können Sie erneut auf **Generate 3D Context** (3D-Kontext generieren) klicken, um die Gebäude neu zu generieren. 

_Beachten Sie, dass durch die Neugenerierung des Kontexts das Gruppenexemplar mit den Gebäuden durch ein neues Exemplar ersetzt wird, sodass alle bisherigen Änderungen an den Gebäuden verloren gehen._ Um dies zu verhindern, können Sie die Gruppierung des Kontextcontainers aufheben und ihn anschließend erneut gruppieren.

## **Einige Beispiele**

Versuchen Sie zu erraten, welche symbolträchtigen Städte in den folgenden Kontexten dargestellt werden:

![](<../../.gitbook/assets/image (2) (1).png>)

![](<../../.gitbook/assets/image (34).png>)

![](<../../.gitbook/assets/image (13) (1) (1).png>)

![](<../../.gitbook/assets/image (59).png>)
