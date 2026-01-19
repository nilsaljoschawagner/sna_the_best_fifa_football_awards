**Codebuch: FIFA‑Voting‑Netzwerk (Men’s Player, letzte 3Jahre)**

**Datengrundlage**

Die Daten basieren auf den **offiziell veröffentlichten Stimmabgaben** der letzten **drei Ausgaben** der „The Best FIFA Men’s Player“-Awards. Erfasst wurden die Stimmen der **Nationaltrainer**, **Nationalmannschaftskapitäne** und **Journalisten jeden Landes**.

Das resultierende Netzwerk ist ein **gerichtetes One‑Mode‑Akteursnetzwerk**, in dem sowohl **Wählende** als auch **Gewählte** als Knoten geführt werden.

**\*Für den Pretest wird zunächst nur die Wahl 2025 berücksichtigt. \***

**Netzwerktyp**

**Voting‑Netzwerk„player\_vote“**

Erfasst werden ausschließlich die Stimmen für den **Best FIFA Men’s Player**.

Jede wählende Person benennt drei Spieler in einer Rangfolge:

**1\. Platz** → Gewicht 5

**2\. Platz** → Gewicht 3

**3\. Platz** → Gewicht 1

Diese Gewichtung entspricht dem offiziellen FIFA‑Voting‑Schema.

Es werden **nur die Männerkategorie** und **nur die letzten drei Jahre** berücksichtigt.

**Umgang mit fehlenden Werten**

Es fehlt die Vereinszugehörigkeit der wählenden Kapitäne sowie die Vereinszugehörigkeit und Nationalität der Gewählten. Diese wurden manuell ergänzt. Der Stimmzettel der FIFAlistet ansonsten jede einzelne Wahl auf. Bezüglich der Wahl treten also keine fehlenden Werte auf.

**EDGE‑Attribute**

**id**

Spielername

**from**

Wählende Person (Trainer, Kapitän, Journalist)

**to**

Gewählter Spieler

**weight**

Stärke der Beziehung basierend auf der Rangfolge (5/3/1)

**Relation**

1= gleiche Nationalität

2= gleicher Verein

3 = gleiche Nationalität und gleicher Verein

4 = keine Verbindung

**year**

Jahr der Abstimmung (z. B. 2022, 2023, 2024)

**NODE‑Attribute**

**id**

Identische ID wie in der Edgelist

**role**

Rolle im Voting: 1 = Spieler 2 = Trainer 3 = Journalist

4 = gewählte Spieler

5 = gewählte Spieler, die auch Kapitäne sind

**country**

Nationalität

**club**

Verein des Spielers (Wähler und Gewählter)

**Hinweise zur Interpretation**

Das gerichtete Netzwerk bildet **Präferenzbeziehungen** ab. Eine Kante bedeutet:

**Der Knoten „from“ hat den Knoten „to“ im Rahmen der FIFA‑Wahl bevorzugt.**

Die Gewichtung ermöglicht Analysen zu:

*   **Zentralität** (z. B. welche Spieler strukturell sichtbar sind)
    
*   **Clusterbildung** (z. B. regionale Präferenzmuster)
    
*   **In‑Group‑Bias** (z. B. Stimmen für Landsleute oder Teamkollegen
    

*   **Stabilität über drei Jahre** (z. B. wiederkehrende Muster)