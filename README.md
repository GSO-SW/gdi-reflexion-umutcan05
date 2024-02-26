[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-24ddc0f5d75046c5622901739e7c5dd533143b0c8e959d652212380cedb1ea36.svg)](https://classroom.github.com/a/OwH8KTXH)
# GDI+
Eine Sammlung von Tipps und Tricks zum Thema Grafikprogrammierung mit GDI+.

## Klassen / Ereignisse
### Timer
Ein Timer führt in regelmäßigen Abständen ein `Tick`-Event aus. Der [`System.Windows.Forms`.`Timer`](https://learn.microsoft.com/de-de/dotnet/api/system.windows.forms.timer?view=windowsdesktop-8.0&viewFallbackFrom=net-6.0) kann über die Toolbox auf die GUI gezogen werden. 

Anschließend können wir 
- die Zeit zwischen jedem `Tick`-Event einstellen (`+ Interval { get; set; }: int`) und
- den Timer starten (`+ Start():void`) oder
- stoppen (`+ Stop():void`) oder
- den Zustand abfragen. (`+ Enabled{ get; set; }: bool`) (Standard ist ausgeschaltet: `enabled = false`)



## Tipps und Tricks
Ergänzen Sie hier die notwendigen Code-Ausschnitte, um zu zeigen, wie man es macht. 
- Sie können [CodeBlöcke mit Syntax-Highlighting](https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/creating-and-highlighting-code-blocks#syntax-highlighting) einsetzen
- Wird es zu unübersichtlich? Sie können auch Unterordner mit Beispiel-Code anlegen und auf die entsprechenden Dateien verlinken. [Inspiration](https://github.com/gsoTH/flaskShowcase/tree/master/datenbanken)
- Die folgende Liste kann gerne ergänzt werden :)

### Bewegung animieren


### Objekte mit Tasten steuern

Tastendruck = e.KeyCode
Keys.(KeyOnKeyboard)

if (e.KeyCode == Keys.Right || e.KeyCode == Keys.D) 
{
    spieler.X = spieler.X + hoeheJeBereich;
}
### Verhindern, dass ein Spieler aus dem Bild läuft

2 neue int Variablen:

- eine für x (int xCounter = 0;)
- eine für y (int bahnCounter = 0;)

z.B. nicht rechts aus dem Bild laufen:

if (e.KeyCode == Keys.Right || e.KeyCode == Keys.D) 
{
    if (xCounter < 4)
    {
        spieler.X = spieler.X + hoeheJeBereich;
        xCounter++;
    }
}
### Spiel pausieren

tmrgametick.Stop(); für alle Objekte
### Ihr schönstes Ergebnis

helle und dunkle Bahnen abwechselnd erstellen:

for (int i = 0; i < helleBahnen.Length; i+=2)
{
    helleBahnen[i] = new Rectangle(0, i * hoeheJeBereich, breite, hoeheJeBereich);
}

for (int i = 1; i < dunkleBahnen.Length; i +=2)
{
    dunkleBahnen[i] = new Rectangle(0, i * hoeheJeBereich, breite, hoeheJeBereich);
}



SolidBrush brBahnHell = new SolidBrush(Color.LightGray);
SolidBrush brBahnDunkel = new SolidBrush(Color.Gray);




### nützliche Funktionen

Graphics g = e.Graphics;

dvdLogo.X+=15;
dvdLogo.Y+=15;