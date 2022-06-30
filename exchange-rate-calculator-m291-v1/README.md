# exchange-rate-calculator-m291-v1

#### 1.0 Ausgangslage/ Projektbeschreibung
#### 2.0 Testing
#### 3.0 Fazit / Lessons Learned

## 1.0 Ausgangslage/ Projektbeschreibung
#### Als Abschlussauftrag für da M291 entschied ich mich für einen Währungsrechner, welcher es ermöglicht Währungskurse mithilfe einer externen Api (https://www.exchangerate-api.com) zu berechnen.
#### Persönliche Ausgangslage: Ich persönlich absolvierte bereits ein paar Module welche sich mit dem Thema JavaScript auseinandersetzten, somit hatte ich schon ein paar Vorkenntnisse beim erstellen von Formularen und dem Arbeiten mit JavaScript. Was allerdings neu war, war die App Erstellung mithilfe von VueJS.

## 2.0 Testing
### Eingabe in Formular

<img width="588" alt="image" src="https://user-images.githubusercontent.com/97659996/176668581-c71a7c33-919e-4d3d-ac03-7427ea0e4d41.png">

#### Eingabe in Formular funktioniert Problemlos. Die verschiedenen Währungen können aus dem Drop down auf der linken Seite des Formulars problemlos ausgewählt werden. Als Beispiel rechnete ich 1 US Dollar in Euro um. Die Validierung über die API funktionierte, und das Resultat wurde im unteren Formular Feld angezeigt. Ebenfalls kann man auf der rechten Seite des Eingabefeldes mithilfe von Pfeilen die Zahl grösser oder kleiner machen.

<img width="588" alt="image" src="https://user-images.githubusercontent.com/97659996/176670697-35be6ca9-dfb6-4edb-8d53-070282844ded.png">

#### Der "Switch" Button funktioniert  Problemlos. Der "Switch" Button dient dazu, die ausgewählten Rechnung untereinander auszuwechseln.

## Herunterladen von Ergebnissen

<img width="588" alt="image" src="https://user-images.githubusercontent.com/97659996/176670697-35be6ca9-dfb6-4edb-8d53-070282844ded.png">

#### Der "Download" Button funktioniert ebenfalls Problemlos. Der Download Button ist dazu da, die Eingegeben + Validierten Daten aus dem Formular als Text Datei herunterzuladen. Der Dateiname sollte jeweil das Datum und die Uhrzeit des Downloads aus dem Formular. Dies wurde ebenfalls bei verschiedenen Tests in verschiedenen Browsern ausgegeben.

<img width="794" alt="image" src="https://user-images.githubusercontent.com/97659996/176672257-8befa622-7931-4b31-af29-afc228ec22d6.png">

## 3.0 Fazit / Lessons Learned

#### Dieses Modul bot einige herausforderungen für mich, da der Workflow sich mit VueJS meiner Meinung nach stark vom normalen Workflow unterscheidet, das Arbeiten in einem Dokument (App.vue) war neu für mich. Ich lernte einige Dinge von JavaScript dazu, insbesondere die Validierung von Daten aus einem Formular. Auch lernte ich besser mit dem auf CSS aufbauenden SASS umzugehen. Im grossen und ganzen muss ich sagen, dass mir das Modul extrem viel gebracht hat, ich hatte zwar oft Probleme, diese jedoch halfen mir bei der Problemlösung umso mehr und ich lernte einiges dazu.
