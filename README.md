
# <a id="h">Stride Lernaktivitäten Krull+Tiedemann</a>
    Informatik bei Herrn Buhl, 1. Halbjahr 2016
 
## Clash of Crabs

### Gliederung
1. [Spielprinzip](#a)
     1.1 [Ziel des Spiels](#b)
     1.2 [Steuerung](#c)
2. [Spielentwicklung](#d)
    2.1 [Greenfoot-Einstieg](#i)
    2.2 [Ideen](#g)
    2.3 [Implementierung](#e)
3. [Weitere Entwicklungsideen](#f)

___ 

### <a id="a">Spielprinzip</a>

Schlüpfen Sie in die Rolle einer Krabbe am Sandstrand! 

Es tummeln sich dort Würmer, Seesterne und Hummer. In einem ständigen Überlebens- und Konkurrenzkampf erleben Sie den ultimativen Adrenalinkick. Sie sind ständig auf der Suche nach leckeren Würmern. Doch nehmen Sie sich in Acht vor den sadistischen Hummern, die sich völlig unberechenbar bewegen und Ihnen während der Nahrungssuche nach dem Leben trachten. 
Ab und zu können Sie sich am Anblick äußerst dekorativer Seesterne beglücken.

Clash of Crabs ist zurzeit ein reines Multiplayerspiel.

#### <a id="b">Ziel des Spiels</a>

Überleben!

#### <a id="c">Steuerung</a>

Naturgetreue Darstellungen sind uns sehr wichtig. Daher bewegen sich die Krabben seitwärts fort.

Die obere Krabbe (Player 1) wird mit Hilfe der Pfeiltasten gesteuert, die untere Krabbe (Player 2) mit w,a,s,d. Beide Krabben bewegen sich von allein, einzig die Richtungsänderung muss bestimmt werden.

___ 

### <a id="d">Spielentwicklung</a>

Zuerst haben wir uns durch die Stride Lernaktivitäten gearbeitet, um uns einen ersten Einblick in die Programmiersprache Stride zu verschaffen. Dabei fiel uns vor allem das "Little Crab" Szenario ins Auge, welches unserer Meinung nach hohes Potenzial besitzt. Also haben wir uns die weiteren Informatikstunden dem "Little Crab" Szenario gewidmet, unsere eigenen Ideen eingebracht und es immer weiter verbessert, bis schließlich unser Spiel "Clash of Crabs" entstanden ist.

#### <a id="i">Greenfoot-Einstieg</a>

Um einen ersten Einblick in Greenfoot zu bekommen, haben wir uns zunächst durch die Greenfoot-Stride-Lernaktivitäten gearbeitet. Das Meet-the-Greeps Szenario gab uns einen ersten Eindruck, wie Greenfoot aufgebaut ist und wie wir Befehle im Editor erstellen und verändern. Die Grundlagen der Tastatursteuerung, sowie die Verwendung von Variablen haben wir so kennengelernt.
Anschließend haben wir uns mit dem FatCat Szenario beschäftigt. Da wir die Befehle hierbei selbst erstellen sollten, haben wir uns mit den verschiedenen Hotkeys auseinandergesetzt und anschließend verschiedene Methoden ausprobiert. Das Endergebnis der tanzenden Katze war dabei ein großer Erfolg.

#### <a id="g">Ideen</a>

Unsere erste geniale Idee für eine Verbesserung bestand darin, Clash of Crabs zu einem Multiplayerspiel zu machen, da Multiplayerspiele sich, wie allgemein bekannt ist, einer hohen Beliebtheit erfreuen. Hierfür haben wir uns überlegt, dass die eine Krabbe mit den Pfeiltasten und die andere Krabbe mit w,a,s,d, gesteuert werden kann. Natürlich müssen sich die beiden Krabben auch optisch voneinander unterscheiden.

Des Weiteren haben wir die Grafiken etwas aufgemodelt, da wir wollten, dass das Spiel einen etwas realistischeren Touch bekommt.
Einzig die Grafik der Würmer haben wir beim Alten belassen, um keinen Würgereiz beim Spieler hervorzurufen.

Für die Hummer haben wir einen praktikablen Bewegungsablauf programmiert, der sie nach dem Zufallsprinzip über den gesamten Bildschirm laufen lässt. Zudem erscheinen nach einiger Zeit neue Hummer, sodass der Schwierigkeitsgrad erhöht wird. Sie erscheinen immer genau in der Mitte des Bildschirms, damit das Spiel für beide Spieler fair bleibt.

Als letztes haben wir dem Spiel noch Sounds hinzugefügt: Eine chillige Beachmusic als Hintergrundmusik, um das Strandflair zu gewährleisten, sowie einen hippen Sound, wenn eine der Krabben gefressen wird, was den Gewinner akustisch bekanntgeben soll.

#### <a id="e">Implementierung</a>

Um den zwei Krabben eine unterschiedliche Tastatursteuerung zu geben, haben wir mit Constructors gearbeitet. 
Dafür haben wir zunächst beim Actor "Crab" in "Fields" vier Variablen vom Typ String erstellt (keyUp, keyDown, keyLeft, keyRight). In "Constructors" haben wir dann für jede Krabbe vier Constructors (keyU, keyD, keyL, keyR), ebenfalls vom Typ String, erstellt. Darunter haben wir die vier Constructors definiert, und zwar als die vier zuvor erstellten Variablen. 
Dann haben wir eine Methode namens "TastatursteuerungCrab" erstellt und für jede Bewegungsrichtung unsere Variablen keyUp, keyDown, keyLeft und keyRight eingesetzt.
Anschließend haben wir in der CrabWorld "prepare"-Methode den beiden Krabben ihre unterschiedlichen Constructors 
(w,a,s,d bzw. die Pfeiltasten) zugewiesen.

Nach demselben Prinzip haben wir beiden Krabben verschiedene Bilder zugewiesen.

Die alten Grafiken haben wir ausgetauscht, indem wir zunächst im Internet nach neuen, realitätsnaheren Grafiken gesucht haben.
Anschließend haben wir diese einfach in den "Images" Ordner eingefügt und für die jeweiligen Actors unsere Grafiken ausgewählt.

Gleiches haben wir mit den Sounds gemacht. Diese haben wir ebenfalls im Internet gefunden, in den "Sounds" Ordner eingefügt und an den richtigen Stellen in unser Spiel einprogrammiert.

Der Bewegungsablauf der Hummer erfolgt nach dem Zufallsprinzip. Dies haben wir umgesetzt, indem  wir die Hummer konstant vorwärts laufen lassen und random ("Greenfoot.getRandomNumber") deren Bewegungsrichtung mithilfe von "setRotation"  ändern. 
Mit den Wahrscheinlichkeiten haben wir so lange rumprobiert, bis die Hummer schließlich über den gesamten Bildschirm gelaufen sind.

Damit immer neue Hummer spawnen, haben wir in CrabWorld in "Fields" zuerst eine Variable vom Typ Integer erstellt ("zeitZumLobster") und diese auf 0 gesetzt. In der "act"-Methode der CrabWorld haben wir programmiert, dass die "zeitZumLobster" pro Tic um 1 erhöht wird und dass nach 600 Tics jeweils ein neuer Hummer in der Mitte der Welt gespawnt wird. Die "zeitZumLobster" wird anschließend wieder auf 0 gesetzt.

Nach dem selben Prinzip haben wir auch immer neue Würmer und Seesterne spawnen lassen. Die "zeitZumWurm" haben wir auf 75 Tics festgelegt, damit diese stets vorhanden sind. Die Seesterne spawnen nach 1000 Tics, sodass das Treffen auf einen Seestern eine seltene Begegnung bleibt.
___ 

### <a id="f">Weitere Entwicklungsideen</a>

Wir haben noch viele weitere Ideen, um unser Spiel zu verbessern, die wir jedoch aufgrund Zeitmangels (noch) nicht umsetzen konnten. 

Am wichtigsten wäre uns zunächst die Einblendung des Gewinners am Ende des Spiels. Hierfür haben wir bereits zwei Grafiken  erstellt ("Player 1 wins","Player 2 wins"). Leider ist es uns bisher nicht gelungen, diese ins Spiel zu integrieren. Die Schwierigkeit hierbei bestand vor allem darin, die jeweilige Grafik mit der betreffenden Krabbe zu verbinden.

Zudem sollte es zu Beginn des Spiels einen Titelbildschirm geben, in welchem man zwischen dem Multiplayer oder Singleplayer Modus wählen kann. Hierbei sollte auch eingeblendet werden, welche Krabbe zu welchem Spieler gehört und wie diese zu steuern sind. 

Außerdem sollten die nährstoffreichen Würmer überlebenswichtig sein. Um nicht zu verhungern, müssten ca. 5 Würmer pro Minute gefressen werden. 
Dazu müssten im oberen Drittel des Bildschirms zwei Health Bars angezeigt werden, die kontinuierlich sinken und beim Verzehr von Würmern wieder partiell aufgefüllt werden. Dadurch entstünde ein Konkurrenzkampf zwischen den Krabben, der den Spielspaß erheblich steigern würde.

Des Weiteren sollten die überaus dekorativen Seesterne eine Funktion erhalten. Wir dachten an einen Super-Mario-inspired Seestern, der die Krabben temporär unsterblich macht. Außerdem kann die Krabbe durch ihre Superkraft die Hummer zerstören, wodurch das Gameplay erheblich verbessert würde und eine längere Spieldauer ermöglicht würde. 

___ 

[nach oben](#h)
