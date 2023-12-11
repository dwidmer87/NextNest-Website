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

## Reflexion

Was war einfach zu implementieren?<br>
Wo gab es Schwierigkeiten und welche? Wie konnten sie gelöst werden?<br>
Welche technischen und organisatorischen Entscheidungen haben wir getroffen und warum?<br>

### Gesamte Website - CSS

Um den Arbeitsprozess zu vereinfachen, haben wir uns dazu entschieden, dass für jede Seite ein separates CSS-File erstellt wird.
Wenn jemand zwei Seiten zu programmieren hatte, konnte die betreffende Person selbstverständlich auch bloss ein File dafür verwenden.
Elemente, die überall benötigt werden, wie root, h1, etc. können einfach kopiert werden. Hier gilt es, am Schluss den Überblick zu beachten.
Evt. macht es Sinn, die gemeinsamen Elemente auf ein style_main.css zu nehmen, wenn alle mit der Programmierung ihrer Seite fertig sind.
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
    <li>body<br>
    Für die Desktop-Ansicht habe ich ein seitliches Padding von 100px eingestellt, damit die Texte nicht zu breit werden. Dieses Padding entfernte ich für die Mobile-Ansicht.</li>
    <li>carousel<br>
    Hier musst ich für die Mobile-Optimierung nur eine kleine Änderung vornehmen. Ich setzte den Parameter für Width auf 350px.(In der Vorschau unter dem "Untersuchen-Tool" ist die schmalste Voreinstellung 360px, deshalb erschien mir das sinnvoll.)</li>
    <li>Angebots- und Imageboxen<br>
    Breite, Margin und Padding angepasst.</li>
    <li>Bilder Angebot<br>
    Hier zeigte sich plötzlich ein Problem. Die Bildergrösse waren im html auf "width=200px" festgelegt. Dies war für die Mobile-Ansicht zu gross. Es gelang mir allerdings nicht, den Parameter im html zu entfernen und die Bildergrösse via CSS zu steuern. Ich musste den Wert im html belassen. Als Alternative habe ich nun im CSS den Parameter "scale" gesetzt. So konnte ich die Bilder auf die Grösse skalieren, in der ich sie benötigte. Wie oben bereits geschildert, mussten die Parameter für die Positionierung (right, transform: translate) neu angepasst werden.<br>
    <li>Community-Box<br>
    Hier nahm ich eine kleine Änderung mit grosser Wirkung vor. Ich änderte die ganze Box mit "display: flex" und "flex-direction: column" in eine vertikale Flexbox. So erscheinen die Inhalte in der Mobile-Ansicht schlicht und einfach untereinander statt in einer wohlportionierten Rasterbox.</li>
    <li>prev- und next-Pfeile bei Community-Box<br>
    Die hatten in der Mobile-Ansicht keinen Platz mehr. Deshalb blendete ich sie mit "display: none" aus.</li>
    <br><br>
    DW, 11.12.23
