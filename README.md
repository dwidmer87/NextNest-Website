# Projektdoku NextNest

Hier dokumentieren wir unsere Fortschritte an der Website:

## Aufgabenverteilung:

Header, inkl. NavBar: Livia<br>
Footer: Livia <br>
Buttons: Aaron <br>
Home: Aaron <br>
Angebot: David <br>
About us: Gina <br>
Kontakt: Gina <br>
Impressum: David <br>
Responsive-Design: David, Aaron <br>
Schlusskontrolle und allfällige Überarbeitung <br>

## Reflexion

Was war einfach zu implementieren?<br>
Wo gab es Schwierigkeiten und welche? Wie konnten sie gelöst werden?<br>
Welche technischen und organisatorischen Entscheidungen haben wir getroffen und warum?<br>

### Gesamte Website - CSS

Um den Arbeitsprozess zu vereinfachen, haben wir uns dazu entschieden, dass für jede Seite ein separates CSS-File erstellt wird.
Wenn jemand zwei Seiten zu programmieren hatte, konnte die betreffende Person selbstverständlich auch bloss ein File dafür verwenden.
Elemente, die überall benötigt werden, wie root, h1, etc. können einfach kopiert werden. Hier gilt es, am Schluss den Überblick zu beachten.
Evt. macht es Sinn, die gemeinsamen Elemente auf ein style_overall.css zu nehmen, wenn alle mit der Programmierung ihrer Seite fertig sind.
So können Änderungen zentral in einem File vorgenommen werden.<br>
Viele CSS-Parameter konnten direkt aus Figma entnommen werden.

### angebot.html

Einfach zu bewerkstelligen waren die Elemente ganz oben und unten auf der Page (ohne Header, resp. Footer). Die zwei unterschiedlichen Span-Elemente (bold und underline) konnte ich mit der Spezifizierung in span1 und span2 lösen. Eine andere Variante wäre es gewesen, mit Klassen zu arbeiten. Meine Lösung erschien mir aber einfacher. Auf einer Page mit vielen unterschiedlichen Span-Elementen ist es aber wohl übersichtlicher, Klassen (z.B class="bold") zu verwenden.
<br><br>
Eine grosse Herausforderung stellte das Angebotskarrussel dar. Nach einer ausgedehnten Google-Recherche, Ausprobieren auf w3schools und der Nachfrage beim Co-Pilot wurde mir klar, dass ein Karrussel wie auf dem Mockup ohne JavaScript nicht möglich sein wird und ich stattdessen auf eine klassische und optisch nicht sehr attraktive Scrollbar zurückgreifen muss.<br>
w3schools war mir diesbezüglich eine grosse Hilfe. Mit dem "scroll-snap-type: x mandatory" konnte ich die Slideshow zumindest so programmieren, dass sie von Bild zu Bild hüpft.
<br><br>
Den h2 in den Slides musste ich im CSS via Klasse (.box_angebot h2) anpassen, da die generelle top-margin für h2 (80px) sonst viel zu gross gewesen wäre.<br>
Das Einfügen der Bilder war schwieriger als gedacht. Mithilfe w3schools und einigem Tüfteln konnte ich die Parameter "position" (relative vs. absolute), "right" und "transform: translate" so konfigurieren, dass die Bilder in der Imagebox positioniert waren. Prozentwerte waren hilfreich.
<br><br>
Bei der Community-Box habe ich auf eine Kombination aus Grid und Flex gesetzt. Die ganze Box, bestehend aus div-Elementen ist grundsätzlich als Grid aufgebaut, aber z. B. die Unterbox "Testimonial" wieder in sich als Flexbox.
<br><br>
Als die Page am Ende als Desktop-Version stand, setzte ich mich noch daran, sie für Mobile zu optimieren. Elemente wie das Karrussel oder auch die Community-Box wären zu breit für den Mobile-Screen. Ich setzte als min-width für die Desktop-Anzeige 1200 px. Da die Elemente "Karrussel" und "Community-Box" eine Breite von 1000px aufweisen, erschien mir das sinnvoll. Da ich mit min-width arbeite, setzte ich die für Mobile-Screen anzupassenden Elemente in ein separates Media-Query, kopierte die Parameter darin und setzte sie unmittelbar vor dem Element wieder ein. In diesem Abschnitt nahm ich nun die Änderungen für Mobile vor. In der Definition gilt somit der Media-Screen als Standard, sobald die Bildschirmbreite 1200px überschreitet, wechselt die Page in die Desktop-Ansicht.<br> Folgende Änderungen nahm ich für die Mobile-Ansicht vor:
<ul>
    <li>main<br>
    Für die Desktop-Ansicht habe ich ein seitliches Padding von 100px eingestellt, damit die Texte nicht zu breit werden. Dieses Padding entfernte ich für die Mobile-Ansicht.</li>
    <li>carousel<br>
    Hier musst ich für die Mobile-Optimierung nur eine kleine Änderung vornehmen. Ich setzte den Parameter für Width auf 350px. (In der Vorschau unter dem "Untersuchen-Tool" ist die schmalste Voreinstellung 360px, deshalb erschien mir das sinnvoll.)</li>
    <li>Angebots- und Imageboxen<br>
    Breite, Margin und Padding angepasst.</li>
    <li>Bilder Angebot<br>
    Hier zeigte sich plötzlich ein Problem. Die Bildergrösse waren im html auf "width=200px" festgelegt. Dies war für die Mobile-Ansicht zu gross. Es gelang mir allerdings nicht, den Parameter im html zu entfernen und die Bildergrösse via CSS zu steuern. Ich musste den Wert im html belassen. Als Alternative habe ich nun im CSS den Parameter "scale" gesetzt. So konnte ich die Bilder auf die Grösse skalieren, in der ich sie benötigte. Wie oben bereits geschildert, mussten die Parameter für die Positionierung (right, transform: translate) neu angepasst werden.<br>
    <li>Community-Box<br>
    Hier nahm ich eine kleine Änderung mit grosser Wirkung vor. Ich änderte die ganze Box mit "display: flex" und "flex-direction: column" in eine vertikale Flexbox. So erscheinen die Inhalte in der Mobile-Ansicht schlicht und einfach untereinander statt in einer wohlportionierten Rasterbox.</li>
    <li>prev- und next-Pfeile bei Community-Box<br>
    Diese hatten in der Mobile-Ansicht keinen Platz mehr. Deshalb blendete ich sie mit "display: none" aus.</li>
    <br><br>
</ul>
DW, 11.12.23


### index.html / style_home.css

Meine Seite ist mit dem kleinsten Arbeitsaufwand verbunden, da sie nicht sehr komplex war.
Deshalb habe ich mich zusätzlich den Buttons gewidmet.
Dennoch dachte ich zu Beginn, ich werde es nie und nimmer hinkriegen, da ich im Unterricht nur Bahnhof verstanden habe.
Aber ich muss gestehen, es fiel mir überhaupt nicht schwer.
Relativ schnell war mir bewusst, dass das Zusammensammeln anderer Codes Usus sein muss.
Ich habe sowohl das .html, wie auch das .css von David kopiert und umbenannt (index.html, style_home.css).
Dann habe ich jene Zeilen rausgelöscht, die ich nicht brauchte oder sie einfach auf meine Page angepasst.
Dabei habe ich schon sehr viel gelernt, weil ich nun verstehen musste, wie sich die einzelnen Elemente verhalten.

Ich musste im .html nur innerhalb vom main operieren und dort vorallem mit img, div, h1, p, ul.<
Und natürlich im .css, dort liegt der Hund begraben.

img:

Hier stellte sich für mich das grösste Problem dar.
Die Grösse der Bilder musste ich im .html definieren, da sie sonst ihre überproportionale Originalgrösse angenommen hätten.
Da ich die Bilder mit height im .html definiert habe, konnte ich ihre Grösse im .css nicht mehr verändern.
So weit so gut und klar, bei der Desktop Ansicht (@media (min-width: 1200px)) sind die Bilder fast bis zu den 1200px ganz sichtbar,
aber danach hätte ich gerne die ganzen Bilder in der flex-box .raster-bilder proportional zur Box zum schrumpfen gebracht.
Nach langem rumpröbeln habe ich mich entschieden, dass es in diesem Fall (vw<1200px) sowieso mehr Sinn ergibt, die beiden Bilder untereindander anzuordnen (flex-direction: column). So konnte ich im Normalformat (Handy Format) auch gerade eine fixen Wert angeben (scale: ...), welches z.B das .bild_sedel innerhalb des Rasters ein nimmt.

div/ul:

Ich musste eine Raster für die Bilder haben (raster_bilder) und je eines für die Texte mit den Buttons (box_1, box_2).
Der bold-Textblock in der Mitte war per Definition ein h1 übertitel, den konnte ich als solchen lassen.
Nun waren die Texte und Buttons untereineander zu bringen, jedoch sollte die erste Box links und die Zweite rechts sein.
Ich habe mich bei beiden Boxen für grid-templates entschieden, weil ich so relativ einfach dinge untereinander platzieren konnte.
Mit jusify-items, lässt sich auch einfach alles innerhalb der einzelnen Kacheln zentrieren.
Hier war die Schwierigkeit, die Liste so hin zu kriegen, wie in unserem FIGMA File.
Dort waren zuerst waren nämlich die Aufzählungspunkte nicht mit dem Text zentriert, aber mit ::marker {position: sticky} konnte ich das lösen.

Buttons:

Die Farbe und der Style der Button konnte ich aus FIGMA rauskopieren.
Ich fand das mit der transition-duration: 0.4s cool, deshalb habe ich diese Spielerei auch übernommen.
Der Klassiker war hier natürlich, dass der Link-Text bei hier buchen unterstrichen war, aber text-decoration: none; regelte das.

Ergänzungen:

Weil ich wirklich erstaunlich schnell fertig war mit meinem Teil und es kaum glauben konnte,
habe ich immer wieder sporadisch an den anderen Seiten Feinkosmetik betrieben.
Mal die Linkfarben im Header richtig gestellt, damit nur der geklickte und gehoverte Text schwarz ist,
mal geschaut, dass die Mail-/ und Telefon Links auch alle ans richtige Ort führen (href="tel:+41 (0)79 566 78 90").

Fazit:

Ich hätte es zu Beginn wirklich nicht für möglich gehalten, aber mit der Zeit hat mir das Coden tatsächlich so etwas wie Spass bereitet und ich habe sogar verstanden, was ich da mache.

AT, 29.12.23








