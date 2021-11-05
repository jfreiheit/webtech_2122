# Übungen

#### Übung 0

??? question "Infrastruktur einrichten"
    - wählen Sie eine [**IDE**](../tools/#integrated-development-environment-ide) aus und installieren Sie diese 
    - richten Sie sich ein Git-Repository ein (z.B. `WebTech21`) und pushen Sie es auf einen zentralen Dienst ([**siehe**](../tools/#git))
    - laden Sie mich zu Ihrem Git-Dienst ein ([**siehe**](../tools/#git))
    - commiten und pushen Sie Ihr Repository


#### Übung 1

??? question "Übungsaufgabe 1 (HTML)"
    - Erstellen Sie in einem `Uebung1`-Ordner eine Datei `uebung1.html`. Das `body`-Element soll ein `header`-Element, ein `nav`-Element, ein `section`-Element und ein `footer`-Element enthalten. 
    - Unter dieser Übungsaufgabe (siehe `mockupdata`) ist der HTML-Code einer Tabelle mit allen Teilnehmerinnen einer Veranstaltung. Kopieren Sie den Inhalt der Datei so in Ihren HTML-Code, dass folgende Seite erscheint:
    ![Uebung1](./files/49_uebung1.png)

    - Es sollen 4 Unterseiten erstellt werden. Bei Klick auf diese Seiten soll die Tabelle jeweils nur die Teilnehmerinnen enthalten, deren Nachname mit dem entsprechenden Anfangsbuchstaben beginnt (also in `ag.html` nur alle Nachnamen, die mit A bis G beginnen). Die Seiten `ag.html`, `hl.html`, `mr.html` und `sz.html` sollen im Ordner `NN` abgelegt werden, der Unterordner von `Uebung1` ist.
    - Achten Sie darauf, dass man von jeder Unterseite auf jede andere Unterseite und auch auf die Hauptseite (`uebung1.html`) wechseln können muss.
    - Das einzubindende Logo des Studiengangs liegt [hier](./files/fiw.jpg). Es soll in einen `images`-Ordner gespeichert werden, der in der Ordner-Hierarchie neben dem `Uebung1`-Ordner liegt. Um die Größe des Bildes festzulegen, können Sie mit Hilfe des `style`-Attributes die Höhe und die Breite bestimmen: `style="width:53px; height:48px;"` 
    - Nächste Woche wird Uebung1 um CSS erweitert. 

??? "mockupdata"
    ```html
    <table>
        <thead>
            <tr>
                <th>Vorname</th>
                <th>Nachname</th>
                <th>E-Mail-Adresse</th>
                <th>IP-Adresse</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>Adam</td>
                <td>Anderson</td>
                <td>aanderson8@google.fr</td>
                <td>118.93.83.157</td>
            </tr>
            <tr>
                <td>Susan</td>
                <td>Andrews</td>
                <td>sandrewsn@google.co.jp</td>
                <td>228.214.9.251</td>
            </tr>
            <tr>
                <td>Catherine</td>
                <td>Andrews</td>
                <td>candrewsp@noaa.gov</td>
                <td>112.111.87.178</td>
            </tr>
            <tr>
                <td>Alan</td>
                <td>Bradley</td>
                <td>abradley1c@globo.com</td>
                <td>229.152.117.127</td>
            </tr>
            <tr>
                <td>Anne</td>
                <td>Brooks</td>
                <td>abrooks16@bravesites.com</td>
                <td>243.159.39.234</td>
            </tr>
            <tr>
                <td>Russell</td>
                <td>Brown</td>
                <td>rbrownq@nifty.com</td>
                <td>215.38.120.242</td>
            </tr>
            <tr>
                <td>Ryan</td>
                <td>Burton</td>
                <td>rburton18@foxnews.com</td>
                <td>159.60.107.14</td>
            </tr>
            <tr>
                <td>Roy</td>
                <td>Campbell</td>
                <td>rcampbell1@geocities.com</td>
                <td>237.232.34.20</td>
            </tr>
            <tr>
                <td>Russell</td>
                <td>Campbell</td>
                <td>rcampbell17@eventbrite.com</td>
                <td>251.2.92.63</td>
            </tr>
            <tr>
                <td>Bonnie</td>
                <td>Coleman</td>
                <td>bcoleman11@fc2.com</td>
                <td>109.150.122.102</td>
            </tr>
            <tr>
                <td>Ernest</td>
                <td>Coleman</td>
                <td>ecoleman15@businessweek.com</td>
                <td>213.173.4.7</td>
            </tr>
            <tr>
                <td>Richard</td>
                <td>Cruz</td>
                <td>rcruz7@unc.edu</td>
                <td>235.124.23.221</td>
            </tr>
            <tr>
                <td>Sean</td>
                <td>Cruz</td>
                <td>scruz10@answers.com</td>
                <td>92.255.49.227</td>
            </tr>
            <tr>
                <td>Rebecca</td>
                <td>Cunningham</td>
                <td>rcunninghamd@mac.com</td>
                <td>65.79.191.52</td>
            </tr>
            <tr>
                <td>Margaret</td>
                <td>Evans</td>
                <td>mevansh@pcworld.com</td>
                <td>162.10.86.196</td>
            </tr>
            <tr>
                <td>Jeffrey</td>
                <td>Ford</td>
                <td>jford14@cnet.com</td>
                <td>210.216.54.14</td>
            </tr>
            <tr>
                <td>Andrea</td>
                <td>Gardner</td>
                <td>agardnerv@woothemes.com</td>
                <td>179.91.0.30</td>
            </tr>
            <tr>
                <td>Deborah</td>
                <td>George</td>
                <td>dgeorge6@furl.net</td>
                <td>201.76.47.162</td>
            </tr>
            <tr>
                <td>Sean</td>
                <td>Gibson</td>
                <td>sgibsony@alexa.com</td>
                <td>48.114.103.55</td>
            </tr>
            <tr>
                <td>Virginia</td>
                <td>Graham</td>
                <td>vgrahamk@aol.com</td>
                <td>165.219.171.1</td>
            </tr>
            <tr>
                <td>Steven</td>
                <td>Hamilton</td>
                <td>shamiltonu@state.tx.us</td>
                <td>38.194.91.201</td>
            </tr>
            <tr>
                <td>Virginia</td>
                <td>Hawkins</td>
                <td>vhawkinsf@ehow.com</td>
                <td>93.120.46.203</td>
            </tr>
            <tr>
                <td>Edward</td>
                <td>Hicks</td>
                <td>ehicksc@pcworld.com</td>
                <td>199.153.27.1</td>
            </tr>
            <tr>
                <td>Mark</td>
                <td>Johnson</td>
                <td>mjohnsonj@hostgator.com</td>
                <td>73.87.135.206</td>
            </tr>
            <tr>
                <td>Ruth</td>
                <td>Jordan</td>
                <td>rjordan1a@smugmug.com</td>
                <td>193.140.80.64</td>
            </tr>
            <tr>
                <td>Antonio</td>
                <td>Kim</td>
                <td>akim4@odnoklassniki.ru</td>
                <td>168.244.191.78</td>
            </tr>
            <tr>
                <td>Jennifer</td>
                <td>Marshall</td>
                <td>jmarshallt@gnu.org</td>
                <td>104.191.49.94</td>
            </tr>
            <tr>
                <td>Eric</td>
                <td>Matthews</td>
                <td>ematthews5@independent.co.uk</td>
                <td>138.194.30.1</td>
            </tr>
            <tr>
                <td>Raymond</td>
                <td>Mcdonald</td>
                <td>rmcdonald2@ihg.com</td>
                <td>161.24.42.24</td>
            </tr>
            <tr>
                <td>Eric</td>
                <td>Miller</td>
                <td>emillere@creativecommons.org</td>
                <td>122.159.17.218</td>
            </tr>
            <tr>
                <td>Jonathan</td>
                <td>Morales</td>
                <td>jmoralesa@ovh.net</td>
                <td>97.65.110.105</td>
            </tr>
            <tr>
                <td>Marie</td>
                <td>Morgan</td>
                <td>mmorganb@cloudflare.com</td>
                <td>226.79.152.112</td>
            </tr>
            <tr>
                <td>Amanda</td>
                <td>Nelson</td>
                <td>anelson13@indiatimes.com</td>
                <td>161.185.121.245</td>
            </tr>
            <tr>
                <td>Lisa</td>
                <td>Olson</td>
                <td>lolsonr@telegraph.co.uk</td>
                <td>77.245.172.100</td>
            </tr>
            <tr>
                <td>Alice</td>
                <td>Ortiz</td>
                <td>aortizw@histats.com</td>
                <td>179.52.222.21</td>
            </tr>
            <tr>
                <td>Peter</td>
                <td>Phillips</td>
                <td>pphillipss@1688.com</td>
                <td>11.158.255.76</td>
            </tr>
            <tr>
                <td>Matthew</td>
                <td>Porter</td>
                <td>mporter9@europa.eu</td>
                <td>174.81.178.88</td>
            </tr>
            <tr>
                <td>Tammy</td>
                <td>Ray</td>
                <td>trayx@weather.com</td>
                <td>192.243.38.190</td>
            </tr>
            <tr>
                <td>Mark</td>
                <td>Richardson</td>
                <td>mrichardson1d@ihg.com</td>
                <td>209.217.14.154</td>
            </tr>
            <tr>
                <td>Joan</td>
                <td>Roberts</td>
                <td>jroberts12@alibaba.com</td>
                <td>4.91.143.62</td>
            </tr>
            <tr>
                <td>Kathleen</td>
                <td>Rose</td>
                <td>kroseg@pinterest.com</td>
                <td>222.172.140.56</td>
            </tr>
            <tr>
                <td>Steve</td>
                <td>Sanders</td>
                <td>ssanders1b@wikispaces.com</td>
                <td>91.61.109.245</td>
            </tr>
            <tr>
                <td>Shirley</td>
                <td>Scott</td>
                <td>sscottm@macromedia.com</td>
                <td>219.237.108.82</td>
            </tr>
            <tr>
                <td>Lillian</td>
                <td>Stephens</td>
                <td>lstephens19@hugedomains.com</td>
                <td>89.85.137.204</td>
            </tr>
            <tr>
                <td>Nicole</td>
                <td>Thompson</td>
                <td>nthompson3@admin.ch</td>
                <td>13.183.208.155</td>
            </tr>
            <tr>
                <td>Marie</td>
                <td>Thompson</td>
                <td>mthompsonz@yelp.com</td>
                <td>162.164.5.231</td>
            </tr>
            <tr>
                <td>Alan</td>
                <td>Vasquez</td>
                <td>avasquezo@miibeian.gov.cn</td>
                <td>178.109.86.172</td>
            </tr>
            <tr>
                <td>Mildred</td>
                <td>Watkins</td>
                <td>mwatkins0@miibeian.gov.cn</td>
                <td>150.67.132.64</td>
            </tr>
            <tr>
                <td>Eugene</td>
                <td>Williams</td>
                <td>ewilliamsi@deliciousdays.com</td>
                <td>67.208.26.182</td>
            </tr>
            <tr>
                <td>Catherine</td>
                <td>Williams</td>
                <td>cwilliamsl@360.cn</td>
                <td>154.87.204.51</td>
            </tr>
        </tbody>
    </table>
    ```

??? note "Eine mögliche Lösung für Übung 1"
    ```html
    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <title>Aufgabe 1</title>
    </head>
    <body>
        <header>
            <h1>Teilnehmerinnen WebTech</h1>
            <img src="../images/fiw.jpg" alt="FIW Logo" style="width:53px; height:48px;"/>
        </header>
        <nav>
            <a href="#">ALLE</a>
            <a href="./NN/ag.html">A-G</a>
            <a href="./NN/hl.html">H-L</a>
            <a href="./NN/mr.html">M-R</a>
            <a href="./NN/sz.html">S-Z</a>
            <a href="../index.html">Startseite</a>
        </nav>
        <section>
            <table>
                <tr>
                    <th>Vorname</th>
                    <th>Nachname</th>
                    <th>E-Mail-Adresse</th>
                    <th>IP-Adresse</th>
                </tr>
                <tr>
                    <td>Adam</td>
                    <td>Anderson</td>
                    <td>aanderson8@google.fr</td>
                    <td>118.93.83.157</td>
                </tr>
                <tr>
                    <td>Susan</td>
                    <td>Andrews</td>
                    <td>sandrewsn@google.co.jp</td>
                    <td>228.214.9.251</td>
                </tr>
                <tr>
                    <td>Catherine</td>
                    <td>Andrews</td>
                    <td>candrewsp@noaa.gov</td>
                    <td>112.111.87.178</td>
                </tr>
                <tr>
                    <td>Alan</td>
                    <td>Bradley</td>
                    <td>abradley1c@globo.com</td>
                    <td>229.152.117.127</td>
                </tr>
                <tr>
                    <td>Anne</td>
                    <td>Brooks</td>
                    <td>abrooks16@bravesites.com</td>
                    <td>243.159.39.234</td>
                </tr>
                <tr>
                    <td>Russell</td>
                    <td>Brown</td>
                    <td>rbrownq@nifty.com</td>
                    <td>215.38.120.242</td>
                </tr>
                <tr>
                    <td>Ryan</td>
                    <td>Burton</td>
                    <td>rburton18@foxnews.com</td>
                    <td>159.60.107.14</td>
                </tr>
                <tr>
                    <td>Roy</td>
                    <td>Campbell</td>
                    <td>rcampbell1@geocities.com</td>
                    <td>237.232.34.20</td>
                </tr>
                <tr>
                    <td>Russell</td>
                    <td>Campbell</td>
                    <td>rcampbell17@eventbrite.com</td>
                    <td>251.2.92.63</td>
                </tr>
                <tr>
                    <td>Bonnie</td>
                    <td>Coleman</td>
                    <td>bcoleman11@fc2.com</td>
                    <td>109.150.122.102</td>
                </tr>
                <tr>
                    <td>Ernest</td>
                    <td>Coleman</td>
                    <td>ecoleman15@businessweek.com</td>
                    <td>213.173.4.7</td>
                </tr>
                <tr>
                    <td>Richard</td>
                    <td>Cruz</td>
                    <td>rcruz7@unc.edu</td>
                    <td>235.124.23.221</td>
                </tr>
                <tr>
                    <td>Sean</td>
                    <td>Cruz</td>
                    <td>scruz10@answers.com</td>
                    <td>92.255.49.227</td>
                </tr>
                <tr>
                    <td>Rebecca</td>
                    <td>Cunningham</td>
                    <td>rcunninghamd@mac.com</td>
                    <td>65.79.191.52</td>
                </tr>
                <tr>
                    <td>Margaret</td>
                    <td>Evans</td>
                    <td>mevansh@pcworld.com</td>
                    <td>162.10.86.196</td>
                </tr>
                <tr>
                    <td>Jeffrey</td>
                    <td>Ford</td>
                    <td>jford14@cnet.com</td>
                    <td>210.216.54.14</td>
                </tr>
                <tr>
                    <td>Andrea</td>
                    <td>Gardner</td>
                    <td>agardnerv@woothemes.com</td>
                    <td>179.91.0.30</td>
                </tr>
                <tr>
                    <td>Deborah</td>
                    <td>George</td>
                    <td>dgeorge6@furl.net</td>
                    <td>201.76.47.162</td>
                </tr>
                <tr>
                    <td>Sean</td>
                    <td>Gibson</td>
                    <td>sgibsony@alexa.com</td>
                    <td>48.114.103.55</td>
                </tr>
                <tr>
                    <td>Virginia</td>
                    <td>Graham</td>
                    <td>vgrahamk@aol.com</td>
                    <td>165.219.171.1</td>
                </tr>
                <tr>
                    <td>Steven</td>
                    <td>Hamilton</td>
                    <td>shamiltonu@state.tx.us</td>
                    <td>38.194.91.201</td>
                </tr>
                <tr>
                    <td>Virginia</td>
                    <td>Hawkins</td>
                    <td>vhawkinsf@ehow.com</td>
                    <td>93.120.46.203</td>
                </tr>
                <tr>
                    <td>Edward</td>
                    <td>Hicks</td>
                    <td>ehicksc@pcworld.com</td>
                    <td>199.153.27.1</td>
                </tr>
                <tr>
                    <td>Mark</td>
                    <td>Johnson</td>
                    <td>mjohnsonj@hostgator.com</td>
                    <td>73.87.135.206</td>
                </tr>
                <tr>
                    <td>Ruth</td>
                    <td>Jordan</td>
                    <td>rjordan1a@smugmug.com</td>
                    <td>193.140.80.64</td>
                </tr>
                <tr>
                    <td>Antonio</td>
                    <td>Kim</td>
                    <td>akim4@odnoklassniki.ru</td>
                    <td>168.244.191.78</td>
                </tr>
                <tr>
                    <td>Jennifer</td>
                    <td>Marshall</td>
                    <td>jmarshallt@gnu.org</td>
                    <td>104.191.49.94</td>
                </tr>
                <tr>
                    <td>Eric</td>
                    <td>Matthews</td>
                    <td>ematthews5@independent.co.uk</td>
                    <td>138.194.30.1</td>
                </tr>
                <tr>
                    <td>Raymond</td>
                    <td>Mcdonald</td>
                    <td>rmcdonald2@ihg.com</td>
                    <td>161.24.42.24</td>
                </tr>
                <tr>
                    <td>Eric</td>
                    <td>Miller</td>
                    <td>emillere@creativecommons.org</td>
                    <td>122.159.17.218</td>
                </tr>
                <tr>
                    <td>Jonathan</td>
                    <td>Morales</td>
                    <td>jmoralesa@ovh.net</td>
                    <td>97.65.110.105</td>
                </tr>
                <tr>
                    <td>Marie</td>
                    <td>Morgan</td>
                    <td>mmorganb@cloudflare.com</td>
                    <td>226.79.152.112</td>
                </tr>
                <tr>
                    <td>Amanda</td>
                    <td>Nelson</td>
                    <td>anelson13@indiatimes.com</td>
                    <td>161.185.121.245</td>
                </tr>
                <tr>
                    <td>Lisa</td>
                    <td>Olson</td>
                    <td>lolsonr@telegraph.co.uk</td>
                    <td>77.245.172.100</td>
                </tr>
                <tr>
                    <td>Alice</td>
                    <td>Ortiz</td>
                    <td>aortizw@histats.com</td>
                    <td>179.52.222.21</td>
                </tr>
                <tr>
                    <td>Peter</td>
                    <td>Phillips</td>
                    <td>pphillipss@1688.com</td>
                    <td>11.158.255.76</td>
                </tr>
                <tr>
                    <td>Matthew</td>
                    <td>Porter</td>
                    <td>mporter9@europa.eu</td>
                    <td>174.81.178.88</td>
                </tr>
                <tr>
                    <td>Tammy</td>
                    <td>Ray</td>
                    <td>trayx@weather.com</td>
                    <td>192.243.38.190</td>
                </tr>
                <tr>
                    <td>Mark</td>
                    <td>Richardson</td>
                    <td>mrichardson1d@ihg.com</td>
                    <td>209.217.14.154</td>
                </tr>
                <tr>
                    <td>Joan</td>
                    <td>Roberts</td>
                    <td>jroberts12@alibaba.com</td>
                    <td>4.91.143.62</td>
                </tr>
                <tr>
                    <td>Kathleen</td>
                    <td>Rose</td>
                    <td>kroseg@pinterest.com</td>
                    <td>222.172.140.56</td>
                </tr>
                <tr>
                    <td>Steve</td>
                    <td>Sanders</td>
                    <td>ssanders1b@wikispaces.com</td>
                    <td>91.61.109.245</td>
                </tr>
                <tr>
                    <td>Shirley</td>
                    <td>Scott</td>
                    <td>sscottm@macromedia.com</td>
                    <td>219.237.108.82</td>
                </tr>
                <tr>
                    <td>Lillian</td>
                    <td>Stephens</td>
                    <td>lstephens19@hugedomains.com</td>
                    <td>89.85.137.204</td>
                </tr>
                <tr>
                    <td>Nicole</td>
                    <td>Thompson</td>
                    <td>nthompson3@admin.ch</td>
                    <td>13.183.208.155</td>
                </tr>
                <tr>
                    <td>Marie</td>
                    <td>Thompson</td>
                    <td>mthompsonz@yelp.com</td>
                    <td>162.164.5.231</td>
                </tr>
                <tr>
                    <td>Alan</td>
                    <td>Vasquez</td>
                    <td>avasquezo@miibeian.gov.cn</td>
                    <td>178.109.86.172</td>
                </tr>
                <tr>
                    <td>Mildred</td>
                    <td>Watkins</td>
                    <td>mwatkins0@miibeian.gov.cn</td>
                    <td>150.67.132.64</td>
                </tr>
                <tr>
                    <td>Eugene</td>
                    <td>Williams</td>
                    <td>ewilliamsi@deliciousdays.com</td>
                    <td>67.208.26.182</td>
                </tr>
                <tr>
                    <td>Catherine</td>
                    <td>Williams</td>
                    <td>cwilliamsl@360.cn</td>
                    <td>154.87.204.51</td>
                </tr>
            </table>

        </section>
        <footer>
          Übung 1 - Jörn Freiheit
        </footer>
    </body>
    </html>
    ```


#### Übung 2

??? question "Übungsaufgabe 2 (CSS)"
    - Erstellen Sie (falls noch nicht geschehen) eine `index.html`-Datei in Ihrem Repository-Ordner (also z.B. `DocumentRoot/Webtech21`) derart, dass diese direkte Links auf Ihre Lösungen der Übungen enthalten (z.B. in einer Tabelle oder einer Liste).
    - Kopieren Sie den Ordner `Uebung1` in den Ordner `Uebung2` (also inkl. Ordner `NN`). Ändern Sie darin die Datei `uebung1.html` zu `uebung2.html` (umbenennen). Ändern Sie entsprechend alle Links innerhalb der Datei, damit Sie z.B. auf den Ordner `Uebung2/NN` zugreifen und nicht mehr auf `Uebung1/NN`.
    - Legen Sie sich im `Uebung2`-Ordner einen Ordner `styles` an. Erstellen Sie in dem `styles`-Ordner eine Datei `mystyles.css`.
    - Fügen Sie im `<head>`-Bereich der `uebung2.html` eine logische Verknüpfung zur `mystyles.css`-Datei ein (`<link href="./styles/mystyles.css" rel="stylesheet">`). 
    - In `mystyles.css` definieren Sie (versuchen Sie mind. 6 der genannten 8 Punkte umzusetzen):
        - Verdana als Schriftart für das ganze Dokument
        - der `<header>` soll das HTW-Grau als Hintergrundfarbe, HTW-Orange als Schriftfarbe und der Text zentriert sein (siehe [**HTW Corporate Design**](http://corporatedesign.htw-berlin.de/schrift-farbe/markenfarben/)).
        - die Tabelle soll ungefähr wie dargestellt aussehen: 
          ![Uebung2](./files/55_uebung2.png) 
        - d.h. mit Rahmen, mit einem Schatten, die Spaltenüberschriften in weiß, mit HTW-grünem Hintergrund.   
        - Das `<nav>`-Feld hat einen Abstand nach oben und nach unten von jeweils `50px`.
        - `<a>`-Elemente in einem `<nav>`-Element haben einen grauen Rand, deren Ecken abgerundet sind. Die Hintergrundfarbe ist HTW-blau. Schriftart ist weiß und bold. `<a>`-Elemente in einem `<nav>`-Element sind nicht unterstrichen!
        - Fährt man mit der Maus über ein `<a>`-Element in einem `<nav>`-Element ändert sich die Hintergrundfarbe in HTW-grau und die Schriftfarbe in HTW-orange. 
            ![Mouseover](./files/56_uebung2_2.png)
        - Die Tabelle hat eine Breite von 80% des `<section>`-Elements. 
        - Der `<footer>` ist in HTW-Orange, die Schrift ist schwarz, der Text ist mittig und die Schrift ist kleiner. Die Höhe des footers entsteht dadurch, dass die Schrift einen Abstand nach oben und nach unten von jeweils `20px` hat.
    - Am Ende soll es *ungefähr* so aussehen:  
      ![Uebung2](./files/57_uebung2_3.png) 


#### Übung 3

??? question "Übungsaufgabe 3 (Grid und Box-Model)"
    - Erstellen Sie einen `Uebung3`-Ordner und darin eine Datei `uebung3.html`. 
    - Laden Sie sich [hier die Datei images.zip](./files/images.zip) herunter, entpacken Sie sie und schieben Sie den `images`-Ordner samt Inhalt in den `Uebung3`-Ordner.
    - Implementieren Sie die `uebung3.html` so, dass *ungefähr* folgendes Aussehen entsteht:
      ![Uebung3](./files/212_uebung3.png) 
    - Sie können die CSS-Eigenschaften innerhalb der `uebung3.html` im `<style>`-Element definieren oder wieder in einer externen Datei. 
    - Ziele der Übung sind die Anwendung von *CSS-Grid* und ein Verständnis vom *Box-Model* sowie die Verwendung von Größen. Lassen Sie Ihrer Kreativität freien Lauf!


#### Übung 4

??? question "Übungsaufgabe 4 (RWD + Bootstrap)"
    - Kopieren Sie `uebung2.html` aus Übung 2 in einen neuen `Uebung4`-Ordner und benennen Sie die Datei in `uebung4.html` um (der `NN`-Ordner muss nicht mehr mitkopiert werden). Achten Sie aber darauf, dass das FIW-Logo noch angezeigt wird
    - Binden Sie in Ihre `uebung4.html` Bootstrap ein (entweder per CDN oder als lokalen Zugriff – siehe [**Bootstrap**](../rwd/#bootstrap))
    - **Header**:
        - der `<header>` enthält das FIW-Logo und die Überschrift `<h1>Teilnehmerinnen WebTech</h1>`
        - verwenden Sie für den `<header>` verschiedene Utilities, so dass Sie ungefähr das Aussehen wie auf dem Bild erreiche [**siehe auch hier**](https://getbootstrap.com/docs/5.0/examples/jumbotron/) zu
        - definieren Sie eine CSS-Eigenschaft so, dass eine `h1`-Überschrift in einem `header` ein Inline-Element ist
        - setzen Sie die Überschrift ungefähr mittig ist (relative Größenangabe - siehe z.B. [**hier**](https://getbootstrap.com/docs/5.0/utilities/spacing/#horizontal-centering))
        - der header soll ungefähr so aussehen (Navigation und Anfang des Hauptteils sind auch schon zu sehen): ![header](./files/66_uebung3_1.png)
    - **Navigation**: 
        - *interne Links* (Links innerhalb der Seite) funktionieren wie folgt: Sie weisen einem Element eine `id` zu, z.B. der Tabellenzeile, die den ersten Nachnamen enthält, der mit "H" beginnt: 
        ```html
            <tr id="H">
                <td>Steven</td>
                <td>Hamilton</td>
                <td>shamiltonu@state.tx.us</td>
                <td>38.194.91.201</td>
            </tr>
        ```
        - Jetzt können Sie in einem internen Link mithilfe des Doppelkreuzes (`#`) und des Bezeichners für die id (`H`) darauf verweisen, z.B.
        ```html 
            <a class="nav-link" href="#H">H-L</a>
        ```
        - Vergeben Sie entsprechend IDs für die entsprechenden Tabellenzeilen (A, H, M, S) und passen Sie Ihre Hyperlinks im Navigationsmenü entsprechend an
        - Weisen Sie Ihrem `<nav>`-Element einen lightgrey-Hintergrund zu
        - Erstellen Sie für die einzelnen Links eine `<ul>`, deren `<li>` jeweils ein `<a>`-Element mit den Referenzen auf die oben beschriebenen IDs enthalten
        - Informieren Sie sich unter [**Navs**](https://getbootstrap.com/docs/5.0/components/navs-tabs/) (oder wo Sie möchten) über „Navs“ und erstellen Sie Ihr Navigationsmenü so, wie oben in der Abbildung (siehe **Header**) gezeigt
        - Ändern Sie aber die Farbe der Links so, dass sie im HTW-Orange (`#FF5F00`) erscheinen und wenn man mit der Maus darüber fährt im HTW-Blau (`#0082D1`) (Definieren Sie sich gerne [**Custom Properties**](../css/#custom-properties) und wenden Sie diese an)
    - **Hauptteil**:
        - der Hauptteil (ein Container) soll aus drei Containern bestehen: einer, der nur das Wort (Überschrift) "links" enthält, einer, der die Tabelle enthält und ein dritter, der nur das Wort (Überschrift) "rechts" enthält
        - Weisen Sie diesem Hauptteil die Klasse `row` zu und gestalten gestalten Sie die drei inneren Container (links, Tabelle, rechts) so, dass
            - sie ab einer Viewportbreite `>= 992px` (`lg`) nebeneinander sind, wobei die Tabelle 4x so breit ist wie die jeweiligen Container an der Seite
            - unterhalb der Viewportbreite von `992px` sollen die drei Teile untereinander sein
            - Abbildung für Breite unter `992px`:  
            ![uebung3](./files/67_uebung3_2.png)
            - Abbildung für Breite oberhalb `992px`:  
            ![uebung3](./files/68_uebung3_3.png)
        -   Mithilfe eigener Media-Queries sollen Sie dafür sorgen, dass die beiden Container links und rechts 
            - einen orangenen Hintergrund und eine Höhe von `100px` haben, wenn der Viewport kleiner als `992px` ist und 
            - einen hellgrauen (`lightgrey`) Hintergrund und eine automatische Höhe (`height: auto;`), wenn der Viewport größer ist
        -   Tabelle: 
            - Erkundigen Sie sich unter [**Tables**](https://getbootstrap.com/docs/5.0/content/tables/) und gestalten Sie die Tabelle so, dass sie ungefähr so aussieht: ![uebung4](./files/69_uebung3_4.png)
            - Sie müssen mit einer eigenen CSS-Definition dafür sorgen, dass die Zeile, in der Sie mit der Maus sind, nicht mehr dunkelgrau, sondern in HTW-Grün erscheint


#### Übung 5
    

??? question "Übungsaufgabe 5 (JavaScript, DOM)"
    - Kopieren Sie den `Uebung4`-Ordner in einen `Uebung5`-Ordner und benennen Sie die `uebung4.html` in `uebung5.html` um
    - Fügen Sie Ihrer Tabelle eine fünfte Spalte hinzu mit leerer Überschrift, also einfach ein weiteres `<th></th>`. Fügen Sie im Table-Body `<tbody>` auch in allen Zeilen ein fünftes `<td></td>` hinzu (nicht händisch! - *Find and Replace* der IDE nutzen!) 
    - Fügen Sie Ihrer Tablle nun in HTML eine weitere Zeile hinzu, die wie folgt aussehen soll:
      ![uebun5](./files/72_uebung4_1.png)
    - Verwenden Sie für den Button das Attribut `onclick` und rufen Sie eine JavaScript-Funktion `checkAndAdd()` auf, die Sie selbst schreiben
    - in der `checkAndAdd()`-Funktion soll folgendes geschehen:
        - sie prüfen, ob in jedem der vier `<input>`-Felder (Vorname, Nachname, E-Mail-Adresse, IP-Adresse) etwas eingegeben wurde
        - wenn ja, dann werden diese Werte für eine neue Tabellenzeile (über der Eingabezeile) verwendet (in der folgenden Abbildung wurde `test1`, `test2`, `test3`, `test4` eingegeben):
        ![uebun4](./files/73_uebung4_2.png)
        - wenn nicht, dann werden die Felder, in denen nichts eingegeben wurde, durch Bootstrap rot umrandet (`is-invalid` - siehe Tipps):
        ![uebun4](./files/74_uebung4_3.png)
    - **Tipps:**
        - am einfachsten ist es sicherlich, wenn Sie für den `<tbody>`, die vier neuen `<input>`-Elemente und auch die Tabellenzeile `<tr>`, in der die `<input>`-Elemente sind, eine `id` vergeben, damit Sie in Ihrer Funktion `checkAndAdd()` jeweils mit `document.getElementById()` direkt darauf zugreifen können (siehe [**lokalisieren**](../javascript/#dom-funktionen-lokalisation-von-elementen))
        - benutzen Sie für Ihre `<input>`-Elemente die Bootstrap-Klasse `form-control`, also z.B. `<input id="i1" type="text" class="form-control" placeholder="Vorname" />` (siehe [**Bootstrap Forms**](https://getbootstrap.com/docs/4.5/components/forms/))
        - haben Sie ein `input`-Objekt lokalisiert, z.B. durch `let i1 = document.getElementById('i1')`, dann können Sie über `i1.value` auf den eingegeben Wert zugreifen (siehe Beispiele in [**HTML-Ereignisse**](../javascript/#html-ereignisse) und [**create**](../javascript/#create))
        - Angenommen, Sie haben den `value` von `i1` in der Variablen `value_i1` gespeichert, dann können Sie mithilfe von `value_i1 === ""` prüfen, ob der eingegebene String leer ist, ob also nichts eingegeben wurde (`===` steht für identisch, d.h. Inhalt und Typ sind gleich - `==` würde auch gehen, dann muss der Typ nicht unbedingt gleich sein, der Inhalt aber schon - siehe z.B. [**Vergleichsoperatoren**](https://developer.mozilla.org/de/docs/Web/JavaScript/Reference/Operators/Vergleichsoperatoren))
        - einem solchen `i1`-Objekt können Sie die CSS-Klasse `is-invalid` mit `i1.classList.add('is-invalid')` hinzufügen und mit `i1.classList.remove('is-invalid')` wieder entfernen (selbst, wenn dem Element die Klasse gar nicht zuegordnet ist, gibt es keinen Fehler - siehe z.B. [**hier**](../javascript/#beispiel-vollstandig-mit-javascript-erzeugt))
        - für die neu entstehende Tabellenzeile müssen Sie fünf neue `td`-Obejkte kreieren und diese an ein neu kreiertes `tr`-Objekt anhängen. Die ersten vier `td`-Obejkte bekommen für ihr `innerHTML` den entsprechenden `value` des `input`-Objektes (siehe [**create**](../javascript/#create))
        - fügen Sie das neue `tr`-Objekt in den `tbody` vor der Tabellenzeile mit den `input`-Feldern ein (siehe [**create**](../javascript/#create))
    - **Zusatz:** sehr beeindruckend wäre es, wenn Sie die neue Zeile nicht immer direkt vor die Eingabezeile einfügen, sondern alphabetisch korrekt nach dem Wert des Nachnamens. Sollte das jemand von Ihnen schaffen, schicken Sie mir bitte einen *Pull-Request*. Das wäre sehr cool!


