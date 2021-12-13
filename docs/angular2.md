# JSON und Direktiven

In diesem Kapitel geht es darum, wie wir innerhalb einer Komponente mit TypeScript Daten verwalten und diese Daten im HTML verwenden, um sie entweder anzuzeigen oder die Struktur des HTML-Codes mit diesen Daten zu ändern. Außerdem betrachten wir, wie in TypeScript auf Ereignisse reagieren können, die die Nutzerinnen beim Verwenden der Anwendung auslösen. Um die Verwaltung von Daten zu diskutieren, betrachten wir zunächst, wie Daten in TypeScript/JavaScript notiert werden. 

Für das Beispiel in der Vorlesung wird der Ordner `images` verwendet ([hier zum Download als zip-Datei](./files/images_staedte.zip)) und `stadte.json`.

??? "staedte.json"
    ```json
    {
      "staedte": [
        {
          "jahr": 1237,
          "stadt": "Berlin",
          "link": "http://de.wikipedia.org/wiki/Berlin",
          "bild": "assets/images/berlin.png"
        },
        {
          "jahr": 1624,
          "stadt": "New York",
          "link": "http://de.wikipedia.org/wiki/New_York_City",
          "bild": "assets/images/newyork.png"
        },
        {
          "jahr": 1252,
          "stadt": "Stockholm",
          "link": "http://de.wikipedia.org/wiki/Stockholm",
          "bild": "assets/images/stockholm.png"
        },
        {
          "jahr": 1827,
          "stadt": "Bremerhaven",
          "link": "http://de.wikipedia.org/wiki/Bremerhaven",
          "bild": "assets/images/bremerhaven.png"
        },
        {
          "jahr": 150,
          "stadt": "Bremen",
          "link": "http://de.wikipedia.org/wiki/Bremen",
          "bild": "assets/images/bremen.png"
        },
        {
          "jahr": 1202,
          "stadt": "Bernau",
          "link": "http://de.wikipedia.org/wiki/Bernau_bei_Berlin",
          "bild": "assets/images/bernau.png"
        },
        {
          "jahr": 929,
          "stadt": "Brandenburg",
          "link": "http://de.wikipedia.org/wiki/Brandenburg_an_der_Havel",
          "bild": "assets/images/brandenburg.png"
        },
        {
          "jahr": 805,
          "stadt": "Magdeburg",
          "link": "http://de.wikipedia.org/wiki/Magdeburg",
          "bild": "assets/images/magdeburg.png"
        },
        {
          "jahr": 1222,
          "stadt": "Marburg",
          "link": "http://de.wikipedia.org/wiki/Marburg",
          "bild": "assets/images/marburg.png"
        },
        {
          "jahr": 766,
          "stadt": "Mannheim",
          "link": "http://de.wikipedia.org/wiki/Mannheim",
          "bild": "assets/images/mannheim.png"
        },
        {
          "jahr": 782,
          "stadt": "Mainz",
          "link": "http://de.wikipedia.org/wiki/Mainz",
          "bild": "assets/images/mainz.png"
        }
      ]
    }
    ``` 

??? "Code aus der Vorlesung am 29.11.2021"
    === "app.component.html"
        ```html
        <h1>This is app</h1>
        <app-main></app-main>
        <router-outlet></router-outlet> <!-- diese Zeile kann auch geloescht werden -->
        ```
    === "main.component.html"
        ```html
        <h3>{{ title }}</h3>
        <button (click)="changeStatus()" type=" button ">
        {{ btn_text }}
        </button>
        <!--
        <p>Stadt: {{ staedte_json.staedte[0].stadt }}</p>
        <p *ngFor="let stadt of staedte ">{{ stadt.jahr }}</p>
        -->
        <div *ngIf="!show">Tabelle nicht zu sehen</div>
        <table *ngIf="show" class="table table-striped">
            <thead>
                <tr>
                    <th>Nr</th>
                    <th>Jahr</th>
                    <th>Stadt</th>
                    <th>Bild</th>
                </tr>
            </thead>
            <tbody>
                <tr *ngFor="let s of staedte; let i=index ">
                    <td>{{ i+1 }}</td>
                    <td>{{ s.jahr }}</td>
                    <td>{{ s.stadt }}</td>
                    <td>
                        <a [href]="s.link ">
                            <img [src]="s.bild " [alt]="s.stadt " />
                        </a>
                    </td>
                </tr>
            </tbody>
        </table>
        ```
    === "main.component.ts"
        ```js
        import { Component, OnInit } from '@angular/core';

        @Component({
          selector: 'app-main',
          templateUrl: './main.component.html',
          styleUrls: ['./main.component.css']
        })
        export class MainComponent implements OnInit {
          title = 'Alle Städte';
          staedte_json = {
          "staedte": [
            {
              "jahr": 1237,
              "stadt": "Berlin",
              "link": "http://de.wikipedia.org/wiki/Berlin",
              "bild": "assets/images/berlin.png"
            },
            {
              "jahr": 1624,
              "stadt": "New York",
              "link": "http://de.wikipedia.org/wiki/New_York_City",
              "bild": "assets/images/newyork.png"
            },
            {
              "jahr": 1252,
              "stadt": "Stockholm",
              "link": "http://de.wikipedia.org/wiki/Stockholm",
              "bild": "assets/images/stockholm.png"
            },
            {
              "jahr": 1827,
              "stadt": "Bremerhaven",
              "link": "http://de.wikipedia.org/wiki/Bremerhaven",
              "bild": "assets/images/bremerhaven.png"
            },
            {
              "jahr": 150,
              "stadt": "Bremen",
              "link": "http://de.wikipedia.org/wiki/Bremen",
              "bild": "assets/images/bremen.png"
            },
            {
              "jahr": 1202,
              "stadt": "Bernau",
              "link": "http://de.wikipedia.org/wiki/Bernau_bei_Berlin",
              "bild": "assets/images/bernau.png"
            },
            {
              "jahr": 929,
              "stadt": "Brandenburg",
              "link": "http://de.wikipedia.org/wiki/Brandenburg_an_der_Havel",
              "bild": "assets/images/brandenburg.png"
            },
            {
              "jahr": 805,
              "stadt": "Magdeburg",
              "link": "http://de.wikipedia.org/wiki/Magdeburg",
              "bild": "assets/images/magdeburg.png"
            },
            {
              "jahr": 1222,
              "stadt": "Marburg",
              "link": "http://de.wikipedia.org/wiki/Marburg",
              "bild": "assets/images/marburg.png"
            },
            {
              "jahr": 766,
              "stadt": "Mannheim",
              "link": "http://de.wikipedia.org/wiki/Mannheim",
              "bild": "assets/images/mannheim.png"
            },
            {
              "jahr": 782,
              "stadt": "Mainz",
              "link": "http://de.wikipedia.org/wiki/Mainz",
              "bild": "assets/images/mainz.png"
            }
          ]
        };
        staedte = this.staedte_json.staedte;
        btn_text = 'Klick mich!';
        show = true;

          constructor() { }

          ngOnInit(): void {
            console.log(this.staedte_json);
            console.log(this.staedte_json["staedte"]);
            console.log(this.staedte_json.staedte);
            console.log(this.staedte_json.staedte[0]);
            console.log(this.staedte_json.staedte[0].stadt);
          }

          changeStatus(): void {
            if(this.btn_text === 'Klick mich!'){
              this.btn_text = 'Nochmal';
              this.show = false;
            }
            else{
              this.btn_text = 'Klick mich!';
              this.show = true;
            }
          }

        }
        ```
    === "main.component.css"
        ```css
        td img {
            width: 11%;
        }       
        ```

!!! warning
    Falls `ng add @ng-bootstrap/ng-bootstrap` einen `compatible`-Fehler erzeugt, dann `npm install @ng-bootstrap/ng-bootstrap@bootstrap5` ausprobieren. Stets danach nochmal `npm install` ausführen, damit das Bootstrap-Modul installiert wird. Nach `ng serve` sollten die Änderungen dann wirksam sein. Sollte auch das nicht klappen, können Sie stattdessen auch auch `ng add ngx-bootstrap` probieren (siehe [hier](https://valor-software.com/ngx-bootstrap/#/documentation#getting-started)).

??? "Video aus der Vorlesung am 29.11.2021"
    <iframe src="https://mediathek.htw-berlin.de/media/embed?key=9eefbac7716eb7f0f78853946aaab23e&width=720&height=540&autoplay=false&autolightsoff=false&loop=false&chapters=false&related=false&responsive=false&t=0" data-src="" class="iframeLoaded" width="720" height="540" frameborder="0" allowfullscreen="allowfullscreen" allowtransparency="true" scrolling="no" aria-label="media embed code" style=""></iframe>

## JavaScript Object Notation (JSON)

Eine kurze Einführung zu Objekten in JavaScript haben wir bereits im [**JavaScript-Kapitel**](../javascript/#objekte) gegeben. Dort haben wir auch gesagt, dass wir auf die Notation solcher Objekte in JavaScript nochmal genauer eingehen wollen. Dies geschieht hier. *JavaScript Object Notation (JSON)* ist ein Datenaustauschformat, das einerseits einfach für Menschen zu lesen und zu schreiben ist und andererseits gut von Maschinen *geparst* (analysiert) und erzeugt werden kann. Ein Objekt in JSON beginnt mit einer geschweiften Klammer `{` und endet mit `}`. JSON besteht im wesentlichen aus Schlüssel-Werte-Paaren, die durch Komma getrennt sind. 

```bash
{
	"schlüssel1": wert1,
	"schlüssel2": wert2,
}
```

Die *Schlüssel* sind Strings in doppelten Hochkamma (`""`), dann folgt ein Doppelpunkt `:` und dann folgt der Wert. *Werte* können Strings, Zahlen, Wahrheitswerte, Arrays, Funktionen und Objekte (und `null`) sein. 

Hier ein Beispiel (erweitert [**aus**](https://wiki.selfhtml.org/wiki/JSON)):

```json linenums="1"
{
  "name": "Georg",
  "alter": 47,
  "verheiratet": false,
  "beruf": null,
  "kinder": [
    {
      "name": "Lukas",
      "alter": 19,
      "schulabschluss": "Gymnasium"
    },
    {
      "name": "Lisa",
      "alter": 14,
      "schulabschluss": null
    }
  ],
  "biografie": function() {
            return this.name + " ist " + this.alter + " und hat " + this.kinder.length + " Kinder.";
  },

}
```

- Der Wert zum Schlüssel `"name"` in Zeile `2` ist ein String (`string`). 
- Der Wert zum Schlüssel `"alter"` in Zeile `3` ist eine Zahl (`number`). 
- Der Wert zum Schlüssel `"verheiratet"` in Zeile `4` ist ein Wahrheitswert (`boolean`). 
- Der Wert zum Schlüssel `"kinder"` in Zeilen `6-17` ist Array. 
- Die Elemente in diesem Array sind selbst wieder Objekte in JavaScript Object Notation, bestehend aus jeweils drei Schlüssel-Werte-Paaren.
- Das `"kinder"`ist numerisch indiziert, d.h. wir können über den Index `0` auf das erste Kind (`"Lukas"`) und über den Index `1` auf das zweite Kind (`"Lisa"`) zugreifen

### Zugriff auf ein JSON

Der Zugriff auf die Werte eines JSON erfolgt mittels Punktnotation über den Schlüssel. Wir nehmen obiges Beispiel und speichern es in einer Variablen `georg`:

```javascript linenums="1"
let georg = {
			  "name": "Georg",
			  "alter": 47,
			  "verheiratet": false,
			  "beruf": null,
			  "kinder": [
			    {
			      "name": "Lukas",
			      "alter": 19,
			      "schulabschluss": "Gymnasium"
			    },
			    {
			      "name": "Lisa",
			      "alter": 14,
			      "schulabschluss": null
			    }
			  ],
			  "biografie": function() {
			            return this.name + " ist " + this.alter + " und hat " + this.kinder.length + " Kinder.";
			  },
			};
```

Dann können wir auf die einzelnen Werte wie folgt zugreifen:

```javascript
georg.name 		// "Georg"
georg.alter 	// 47
let kinder = georg.kinder; 	// Array aus 2 Objekten
kinder[0].name		// "Lukas"
kinder[1].name 		// "Lisa"
georg.biografie()	// "Georg ist 47 und hat 2 Kinder."
```

Man kann übrigens auch anstelle der Punktnotation ein JSON wie ein assoziatives Array auffassen und z.B. anstelle von `georg.name` über `georg['name']` auf den Wert `"Georg"` zugreifen. 

Es wäre auch möglich, das "Kinder"-Array in ein weiteres JSON umzuwandeln:

```javascript linenums="1" hl_lines="2 3 8 13 15 16 21 26"
// anstelle von:
  "kinder": [
    {
      "name": "Lukas",
      "alter": 19,
      "schulabschluss": "Gymnasium"
    },
    {
      "name": "Lisa",
      "alter": 14,
      "schulabschluss": null
    }
  ],
// ginge z.B. auch:
  "kinder": {
    "erstesKind" : {
      "name": "Lukas",
      "alter": 19,
      "schulabschluss": "Gymnasium"
    },
    "zweitesKind" : {
      "name": "Lisa",
      "alter": 14,
      "schulabschluss": null
    }
  },
```

Dann ist der Zugriff über den Index (also z.B. `georg.kinder[0]`) nicht mehr möglich. Stattdessen aber:

```javascript
georg.kinder.erstesKind.name
georg.kinder.zweitesKind.alter
```

### Viele Objekte im Array

Wenn Sie viele "gleiche" Objekte speichern, dann in einem Array. Die folgende Datei zeigt viele Objekte in JSON, die in einem Array abgelegt sind:

??? "data/members.json"
    ```json
    {
      "members": [
        {
          "forename": "Catherine",
          "surname": "Williams",
          "email": "cwilliamsl@360.cn"
        },
        {
          "forename": "Adam",
          "surname": "Anderson",
          "email": "aanderson8@google.fr"
        },
        {
          "forename": "Susan",
          "surname": "Andrews",
          "email": "sandrewsn@google.co.jp"
        },
        {
          "forename": "Catherine",
          "surname": "Andrews",
          "email": "candrewsp@noaa.gov"
        },
        {
          "forename": "Alan",
          "surname": "Bradley",
          "email": "abradley1c@globo.com"
        },
        {
          "forename": "Anne",
          "surname": "Brooks",
          "email": "abrooks16@bravesites.com"
        },
        {
          "forename": "Russell",
          "surname": "Brown",
          "email": "rbrownq@nifty.com"
        },
        {
          "forename": "Ryan",
          "surname": "Burton",
          "email": "rburton18@foxnews.com"
        },
        {
          "forename": "Roy",
          "surname": "Campbell",
          "email": "rcampbell1@geocities.com"
        },
        {
          "forename": "Russell",
          "surname": "Campbell",
          "email": "rcampbell17@eventbrite.com"
        },
        {
          "forename": "Bonnie",
          "surname": "Coleman",
          "email": "bcoleman11@fc2.com"
        },
        {
          "forename": "Ernest",
          "surname": "Coleman",
          "email": "ecoleman15@businessweek.com"
        },
        {
          "forename": "Richard",
          "surname": "Cruz",
          "email": "rcruz7@unc.edu"
        },
        {
          "forename": "Sean",
          "surname": "Cruz",
          "email": "scruz10@answers.com"
        },
        {
          "forename": "Rebecca",
          "surname": "Cunningham",
          "email": "rcunninghamd@mac.com"
        },
        {
          "forename": "Margaret",
          "surname": "Evans",
          "email": "mevansh@pcworld.com"
        },
        {
          "forename": "Jeffrey",
          "surname": "Ford",
          "email": "jford14@cnet.com"
        },
        {
          "forename": "Andrea",
          "surname": "Gardner",
          "email": "agardnerv@woothemes.com"
        },
        {
          "forename": "Deborah",
          "surname": "George",
          "email": "dgeorge6@furl.net"
        },
        {
          "forename": "Sean",
          "surname": "Gibson",
          "email": "sgibsony@alexa.com"
        },
        {
          "forename": "Virginia",
          "surname": "Graham",
          "email": "vgrahamk@aol.com"
        },
        {
          "forename": "Steven",
          "surname": "Hamilton",
          "email": "shamiltonu@state.tx.us"
        },
        {
          "forename": "Virginia",
          "surname": "Hawkins",
          "email": "vhawkinsf@ehow.com"
        },
        {
          "forename": "Edward",
          "surname": "Hicks",
          "email": "ehicksc@pcworld.com"
        },
        {
          "forename": "Mark",
          "surname": "Johnson",
          "email": "mjohnsonj@hostgator.com"
        },
        {
          "forename": "Ruth",
          "surname": "Jordan",
          "email": "rjordan1a@smugmug.com"
        },
        {
          "forename": "Antonio",
          "surname": "Kim",
          "email": "akim4@odnoklassniki.ru"
        },
        {
          "forename": "Jennifer",
          "surname": "Marshall",
          "email": "jmarshallt@gnu.org"
        },
        {
          "forename": "Eric",
          "surname": "Matthews",
          "email": "ematthews5@independent.co.uk"
        },
        {
          "forename": "Raymond",
          "surname": "Mcdonald",
          "email": "rmcdonald2@ihg.com"
        },
        {
          "forename": "Eric",
          "surname": "Miller",
          "email": "emillere@creativecommons.org"
        },
        {
          "forename": "Jonathan",
          "surname": "Morales",
          "email": "jmoralesa@ovh.net"
        },
        {
          "forename": "Marie",
          "surname": "Morgan",
          "email": "mmorganb@cloudflare.com"
        },
        {
          "forename": "Amanda",
          "surname": "Nelson",
          "email": "anelson13@indiatimes.com"
        },
        {
          "forename": "Lisa",
          "surname": "Olson",
          "email": "lolsonr@telegraph.co.uk"
        },
        {
          "forename": "Alice",
          "surname": "Ortiz",
          "email": "aortizw@histats.com"
        },
        {
          "forename": "Peter",
          "surname": "Phillips",
          "email": "pphillipss@1688.com"
        },
        {
          "forename": "Matthew",
          "surname": "Porter",
          "email": "mporter9@europa.eu"
        },
        {
          "forename": "Tammy",
          "surname": "Ray",
          "email": "trayx@weather.com"
        },
        {
          "forename": "Mark",
          "surname": "Richardson",
          "email": "mrichardson1d@ihg.com"
        },
        {
          "forename": "Joan",
          "surname": "Roberts",
          "email": "jroberts12@alibaba.com"
        },
        {
          "forename": "Kathleen",
          "surname": "Rose",
          "email": "kroseg@pinterest.com"
        },
        {
          "forename": "Steve",
          "surname": "Sanders",
          "email": "ssanders1b@wikispaces.com"
        },
        {
          "forename": "Shirley",
          "surname": "Scott",
          "email": "sscottm@macromedia.com"
        },
        {
          "forename": "Lillian",
          "surname": "Stephens",
          "email": "lstephens19@hugedomains.com"
        },
        {
          "forename": "Nicole",
          "surname": "Thompson",
          "email": "nthompson3@admin.ch"
        },
        {
          "forename": "Marie",
          "surname": "Thompson",
          "email": "mthompsonz@yelp.com"
        },
        {
          "forename": "Alan",
          "surname": "Vasquez",
          "email": "avasquezo@miibeian.gov.cn"
        },
        {
          "forename": "Mildred",
          "surname": "Watkins",
          "email": "mwatkins0@miibeian.gov.cn"
        },
        {
          "forename": "Eugene",
          "surname": "Williams",
          "email": "ewilliamsi@deliciousdays.com"
        }
      ]
    }
    ```

Ein Array ist stets numerisch indiziert, d.h. Sie können unter Verwendung des Index die einzelnen Objekte auslesen. 

## Bindings und Direktiven

### {{ Interpolation }}

*Interpolation* ist die einfachste Form des *data binding*. Syntaktisch erkennt man Interpolation an den doppelten geschweiften Klammern `{{ Interpolation }}`. 

=== "Beispiel"
``` javascript linenums="1"
import { Component } from '@angular/core';

@Component({
  selector: 'app-lesson',
  template: `
    <h1>{{ headline }}</h1>
    <p>Hier steht {{name}}</p>
  `,
  styleUrls: ['./lesson.component.css']
})
export class LessonComponent {
  headline = 'Mein Titel';
  name = 'mein Name';
}
```

Im obigen Beispiel hat die Komponente `LessonComponent` zwei Eigenschaften: `headline` und `name`. In obiger Komponente wird (zur Anschauung) sogenanntes *inline templating* verwendet, d.h. es gibt keine eigene `lesson.component.html`-Datei, in der der HTML-Code steht, sondern der HTML-Code wird direkt in die `template`-Eigenschaft der Typescript-Datei `lesson.component.ts`eingefügt (siehe Zeilen 5-8 im obigen Beispiel). Der HTML-Code wird in *backticks* eingefasst (` `` `), nicht zu verwechseln mit den einfachen Anführungsstrichen (` '' `).

Damit inline templating möglich ist, wird die Komponente mit dem Flag `-t` erzeugt (`inlineTemplate=true`), d.h. unsere Lesson-Komponente wurde mithilfe der CLI wie folgt erzeugt:

```
ng g c lesson -t
```

Eine Interpolation kann auch Ausdrücke enthalten, die aufgelöst werden, z.B.

``` html
<p>1 + 2 = {{1 + 2}}.</p>
```

Man kann mithilfe einer [Direktive](./#direktiven) durch ein Array laufen und jedes einzelne Element mithilfe von Interpolation ausgeben:

``` javascript
@Component({
  selector: 'app-lesson',
  template: `
    <ol>
      <li *ngFor="let day of weekdays">{{ day }}</li>
    </ol>
  `,
  styleUrls: ['./lesson.component.css']
})
export class LessonComponent {
  weekdays = ['Monday', 'Tuesday', 'Wednesday', 'Thursday', 'Friday', 'Saturday', 'Sunday'];
}
```

Oder es ist möglich, Attributen von HTML-Elementen mithilfe von Interpolation Werte zuzuordnen:

``` javascript
@Component({
  selector: 'app-lesson',
  template: `
    <img src="{{ imgUrl }}" />
  `,
  styleUrls: ['./lesson.component.css']
})
export class LessonComponent {
  imgUrl = 'https://www.dpunkt.de/common/images/cover_masterid/800/12400.jpg';
}
```

Für unser `first`-Beispiel ist ein ganz einfaches Beispiel für die `main`-Komponente gezeigt:

=== "main.component.ts"
    ```js linenums="1" hl_lines="9"
    import { Component, OnInit } from '@angular/core';

    @Component({
      selector: 'htw-main',
      templateUrl: './main.component.html',
      styleUrls: ['./main.component.css']
    })
    export class MainComponent implements OnInit {
      headline = 'This is main';

      constructor() { }

      ngOnInit(): void {
      }

    }
    ```

=== "main.component.html"
    ```html linenums="1" hl_lines="3"
    <div id="main">
      <h3>
          {{ headline }}
      </h3>
      <div id="row">
          <div id="left">
              <htw-left>
              </htw-left>
          </div>
          <div id="right">
              <htw-right>
              </htw-right>
          </div>
      </div>
    </div>
    ```

### #Elementreferenzen

Über eine *Elementreferenz*, die man im HTML-Code mittels des Rautensymbols definiert, kann in Angular sehr einfach auf das Element zugegriffen werden. Das folgende Beispiel zeigt eine solche *Elementreferenz*:

```html
<input #id type="text" value="Elementreferenz" />
{{ id.value }}
```

In dem Beispiel wurde einem Textfeld die Elementreferenz `id` zugewiesen (kann jeder Name sein), erkennbar an `#id`. Über diese Elementreferenz (den Namen) lässt sich nun direkt auf dieses Element zugreifen. Im obigen Beispiel wird die `value`-Eigenschaft ausgelesen, also der Wert, der in das Textfeld eingegeben wird (oder, wie oben, vordefiniert ist). Beachten Sie jedoch, dass der Wert nicht automatisch angepasst wird, sobald eine Eingabe erfolgt. Dies muss durch ein Ereignis (z.B. `change` oder `input`) getriggert werden. 



### [Property Bindings]

Insbesondere, wenn Attributen von HTML-Elementen Werte zugeordnet werden sollen (so wie beim `imgUrl`-Beispiel des Abschnitts [**{{Interpolation}}**](./#interpolation)), spricht man von *property binding*. Property binding spielt eine große Rolle beim Datenfluss von Eltern-Komponenten auf Kind-Komponenten. Die generelle Idee dabei ist, dass mithilfe von *property binding* Werte (Daten) an Attribute von HTML-Elementen bindet. Diese HTML-Elemente können auch Komponenten sein.

Wir betrachten zunächst die unterschiedlichen Arten (Notationen) von property binding:

``` html
<element [property]="ausdruck"></element>
```

D.h. ein *ausdruck* wird übergeben, der zu einem Wert aufgelöst wird und dieser Wert wird dem Attribut `property` übergeben. Betrachten wir nochmals das letzte Beispiel aus dem Abschnitt [**{{Interpolation}}**](./#interpolation)). Bei diesem Beispiel haben wir Interpolation verwendet, um dem Attribut `src` des HTML-Elementes `img` einen Wert zuzuweisen. Das exakt gleiche Verhalten lässt sich auch mittels *property bindings* erzeugen:

``` html
<img [src]="imgUrl" />

<!-- imgUrl = 'https://www.dpunkt.de/common/images/cover_masterid/800/12400.jpg'; -->
```

Das bedeutet für unser `first`-Beispiel, dass die beiden `<img>`-Definitionen gleich sind:


=== "header.component.html"
    ```html linenums="1" hl_lines="2-3"
    <p>header works!
        <img src="{{ imgUrl }}" alt="{{ description }}" width="53px;" />
        <img [src]="imgUrl" [alt]="description" width="53px;" />
    </p>
    ```
 
=== "header.component.ts"
    ```js linenums="1" hl_lines="9-10"
    import { Component, OnInit } from '@angular/core';

    @Component({
      selector: 'htw-header',
      templateUrl: './header.component.html',
      styleUrls: ['./header.component.css']
    })
    export class HeaderComponent implements OnInit {
      imgUrl = '/assets/images/fiw.jpg';
      description = 'FIW Logo';

      constructor() { }

      ngOnInit(): void {
      }

    }
    ```



Neben diesen "allgemeinen" property bindings gibt es auch noch "spezielle" property bindings, nämlich *class bindings* und *style bindings*. Bei *class bindings* wird das Präfix `class` vor die property (die entsprechende CSS-Klasse) gesetzt:

``` html
<element [class.class1]="class1enabled"
         [class.class2]="class2enabled" ... ></element>
```

D.h. die CSS-Klasse `class1`ist genau dann wirksam, wenn der Ausdruck `class1enabled` true ist und `class2`ist genau dann wirksam, wenn der Ausdruck `class2enabled` true ist usw.

Bei den *style bindings* werden jedoch gar keine Ausdrücke, sondern Werte übergeben:

``` html
<element [style.color]
```



### (Event Bindings)

In den *property bindings* haben wir gesehen, wie Werte Attributen (Eigenschaften) von Elementen zugeordnet werden können. Aus JavaScript ist auch bekannt, dass Ereignisse Attribute von Elementen sein können, z.B. `onClick`, `onKeyup`, `onChange` usw. Dabei handelt es sich um sogenannte *native DOM-Ereignisse*. Neben der Möglichkeit, solche nativen DOM-Ereigniss zu behandeln, bietet Angular auch die Möglichkeit, eigene Ereignisse zu definieren und diese zu behandeln. Wir betrachten beide Möglichkeiten und beginnen mit den nativen Ereignissen.

#### Native DOM-Ereignisse

In HTML sieht das unter Aufruf einer JavaScript-Funktion für die Ereignisbahandlung dann typischerweise (hier das Click-Ereignis für einen Button) wie folgt aus:

=== "HTML"
    ``` html
    <button onClick="doSomething()">Click here!</button>
    ```
=== "JavaScript"
    ``` javascript
    function doSomething() 
    {
      // something to do
    }
    ```

In Angular ist das Prinzip das gleiche, nur dass das Ereignis in runden Klammern genannt und an dieses Ereignis die Ereignisbehandlung gebunden wird (*event binding*). Das bedeutet, das Angular-Template für das obige Beispiel sieht wie folgt aus:

=== "Angular-Template"
    ``` html
    <button (click)="doSomething()">Click here!</button>
    ```
=== "Angular-Typescript"
    ``` javascript
    export class EventsComponent {

       doSomething() {
          // something to do
       }
    }
    ```

Dieses Prinzip gilt für alle nativen DOM-Ereignisse. Hier ein kurzer Überblick über die wichtigsten (für eine umfangreichere Liste siehe [hier](https://developer.mozilla.org/en-US/docs/Web/Events#Standard_Events) oder [hier](https://www.w3schools.com/jsref/dom_obj_event.asp)):

| Ereignis        | Beschreibung                                       |
|-----------------|----------------------------------------------------|
| `click`         | Mausklick auf das Element                          |
| `change`        | Der Inhalt/Wert eines Elementes hat sich geändert  |
| `mouseover`     | die Maus wird über das Element bewegt              |
| `mouseout`      | die Maus wird vom Element wegbewegt                |
| `keydown`       | eine Taste der Tastatur wird gedrückt              |
| `keyup`         | Loslassen einer Taste                              |
| `load`          | der Browser hat die Seite vollständig geladen      |
| `focus`         | Fokussieren des Elements (z.B. Anklicken)          |
| `blur`          | Verlieren des Fokus (z.B. Klick außerhalb)         |
| `submit`        | Abschicken eines Formulars                         |
| `copy`, `paste` | Kopieren, Einfügen von Text                        |

Einen kleinen Unterschied gibt es noch bei der Übergabe des Ereignisses an die das Ereignis behandelnde Funktion zu beachten. Während in plain JavaScript das Ereignis mit `event` der Funktion übergeben wird, erfolgt die Übergabe des Ereignisses in Angular mit `$event`. Beispiel:

=== "Angular-Template"
    ``` html
    <input (change)="showPayload($event)" type="text" />
    ```
=== "Angular-Typescript"
    ``` javascript
    export class EventsComponent {

      showPayload(e: Event) {
        console.log(e);
      }
    }
    ```

Alle Events (in TypeScript/Angular) sind vom Typ `Event`. Es gibt noch speziellere Eventtypen, die aber alle auf dem Interface `Event` basieren, z.B. `MouseEvent`, `InputEvent`, `KeyboardEvent`, `UIEvent`, `ClipboardEvent`. Weitere Details siehe [hier](https://developer.mozilla.org/en-US/docs/Web/API/Event).

Die einfache JavaScript-Attributschreibweise kann in Angular nicht verwendet werden, sondern immer nur die *event binding*-Schreibweise von Angular (mit den runden Klammern)!


#### Eigene Ereignisse

Für eine Komponente kann ein eigenes - nicht natives - Ereignis definiert werden. Dies geschieht, indem für eine Komponente eine neue Eigenschaft (z.B. `myEvent`) definiert wird und diese vom Typ `EventEmitter` deklariert wird. Mithilfe von Generics kann der Typ des Events angegeben werden, der ausgelöst werden soll - wenn Sie den Typ nicht genau kennen, verwenden Sie `any`. Soll das Ereignis an die Elternkomponente weitergeleitet werden, was meistens der Fall ist, wird der Decorator `@Output()`verwendet. 
Das Auslösen des Events geschieht dann durch die `emit()`-Methode von `EventEmitter`. Hier ein typisches Beispiel (zunächst die Kindkomponente `EventsComponent` - also `events.component.html` und `events.component.ts`):

=== ".html"
    ``` html
    <button (click)="emitMyEvent()">Click here!</button>
    ```
=== ".ts"    
    ``` javascript linenums="1"
    import {Component, EventEmitter, Output} from '@angular/core';

    @Component({
      selector: 'app-events',
      templateUrl: './events.component.html',
      styleUrls: ['./events.component.css']
    })
    export class EventsComponent {
      @Output() myEvent = new EventEmitter<any>();

      emitMyEvent() {
        this.myEvent.emit();
      }

    }
    ``` 

Die `.html`-Datei definiert einen Button mit dem nativen Ereignis `click`. Dieses wird durch die Methode `emitMyEvent()` behandelt. 

In der `.ts`-Datei ist diese Methode definiert (Zeilen 11-13). Darin wird das eigene Event `myEvent` ausgelöst. Dieses Event ist ein Objekt vom Typ `EventEmitter`, typisiert als `any` (beliebiger Typ). Das Auslösen dieses Events wird an die aufrufende Komponente (die Elternkomponente) ausgegeben (Decorator `@Output()`). Deklaration der Eigenschaft und Dekorieren mit `@Output()` in Zeile 9. Das Auslösen des eigenen Events erfolgt durch den Aufruf der Methode `emit()` aus `EventEmitter` (Zeile 12).

In der Elternkomponente kann dieses Ereignis nun empfangen werden (Beispiel einer Elternkomponente `AppComponent` - also `app.component.html` und `app.component.ts`):

=== ".html"
    ``` html
    <app-events (myEvent)="handleEventFromEventsComponent()"></app-events>
    ```
=== ".ts"    
    ``` javascript linenums="1"
    import { Component } from '@angular/core';

    @Component({
      selector: 'app-root',
      templateUrl: './app.component.html',
      styleUrls: ['./app.component.css']
    })
    export class AppComponent {

      handleEventFromEventsComponent() {
        console.log('myEvent in der Kindkomponente ausgelöst');
      }

    }
    ``` 

In der `AppComponent` (das kann natürlich eine beliebige Komponente sein), wird die `EventsComponent` eingebunden (siehe `<app-events>` im Template der `AppComponent`). Dadurch entsteht die Hierarchie Elternkomponente `AppComponent` --> Kindkomponente `EventsComponent` im DOM. 

Mithilfe von *event binding* wird die Behandlung des Ereignisses `myEvent` an die Methode `handleEventFromEventsComponent()` gebunden. In dieser Methode erfolgt hier einfach nur eine Ausgabe auf die Konsole. 

Interessant ist, dass wir dadurch die Möglichkeit haben, Daten von der Kindkomponente zur Elternkomponente fließen zu lassen. Dazu übergeben wir diese Daten als `payload` des Ereignisses. Dafür typisieren wir `EventEmitter` mit dem Typ, von dem wir Daten übergeben wollen (z.B. `Book` - siehe [Bücher-App](./books/#event-binding)). Die beiden obigen Beispiele sehen dann wie folgt aus (zuerst wieder `EventsComponent`): 

=== ".html"
    ``` html
    <button (click)="emitMyEvent(book)">Click here!</button>
    ```
=== ".ts"    
    ``` javascript linenums="1"
    import {Component, EventEmitter, Output} from '@angular/core';

    @Component({
      selector: 'app-events',
      templateUrl: './events.component.html',
      styleUrls: ['./events.component.css']
    })
    export class EventsComponent {
      @Output() myEvent = new EventEmitter<Book>();

      emitMyEvent(book: Book) {
        this.myEvent.emit(book);
      }

    }
    ``` 

Im Template (HTML) werden die Daten der Ereignisbehandlung übergeben. Das `EventEmitter`-Objekt ist mit dem konkreten Datentyp typisiert. Bei Aufruf der Methode `emit()` werden die Daten an die Elternkomponente übergeben. 

Die Elternkomponente (hier wieder `AppComponent` kann diese Daten, die von der Kindkomponente an die Elternkomponente via Ereignis geflossen sind, nun weiterverarbeiten bzw. darstellen):

=== ".html"
    ``` html
    <app-events (myEvent)="handleEventFromEventsComponent($event)"></app-events>
    ```
=== ".ts"    
    ``` javascript linenums="1"
    import { Component } from '@angular/core';

    @Component({
      selector: 'app-root',
      templateUrl: './app.component.html',
      styleUrls: ['./app.component.css']
    })
    export class AppComponent {

      handleEventFromEventsComponent(book: Book) {
        console.log(book.title);
      }

    }
    ``` 

Wichtig beim *event binding* der Elternkomponente ist, dass der *payload* des Ereignisses mit `$event` übergeben wird (siehe auch [Native DOM-Ereignisse](./#native-dom-ereignisse)). 

!!! success "Zusammenfassung"
    In den letzten drei Abschnitten Interpolation, Property Binding und Event Binding haben wir uns mit Datenfluss beschäftigt. Interpolation wird verwendet, um innerhalb einer Komponente die in der TypeScript-Klasse definierten Daten im Template darzustellen. Mithilfe von Property Binding kann die aufrufende Komponente (Elternkomponente) der aufgerufenen Kopmponente (Kindkomponente) Daten übergeben. Mithilfe von Event Binding kann die Kindkomponente der Elternkomponente mithilfe eines eigenen Ereignisses Daten übergeben.
    Für die Anwendung dieser Konzepte schauen Sie sich [**Bücher-App-->Datenfluss zwischen Komponenten**](./books/#datenfluss-zwischen-komponenten) an. 


### Direktiven

In Angular gibt es 3 Arten sogenannter *Direktiven* (engl. *Directives*):

- Komponentendirektiven (Components—directives) 
- Attributdirektiven (Attribute Directives)
- Strukturdirektiven (Structural-Direktives)

Komponentendirektiven sind die meistverwendete Art und bereits in [**Angular --> Kompnenten**](./#komponenten) betrachtet. Attribut- und Strukturdirektiven können als HTML-Attribute verstanden werden, die dem HTML-Element ein zusätzliches Verhalten hinzufügt. Attributdirektiven wirken sich das innere Verhalten eines HTML-Elementes aus (z.B. können damit CSS-Eigenschaften geändert, hinzugefügt oder gelöscht werden). Mit Strukturdirektiven kann die Struktur des DOMs geändert werden (z.B. können ganze HTML-Elemente dem DOM-Baum hinzugefügt werden).

#### Strukturdirektiven

Strukturdirektiven beginnen immer mit einem Stern `*`. Die bekanntesten Vertreter sind 

- `*ngFor` 
- `*ngIf`
- `*ngSwitch`

Diese sind auch in [angular.io](https://angular.io/guide/structural-directives) erläutert. Wir erläutern die darin aufgeführten Beispiele und beginnen mit `*ngIf`:

```html linenums="1"
<p *ngIf="true">
  Expression is true and ngIf is true.
  This paragraph is in the DOM.
</p>
<p *ngIf="false">
  Expression is false and ngIf is false.
  This paragraph is not in the DOM.
</p>
```

Die Direktive `*ngIf` wird also wie ein Attribut des `<p>`-Elementes behandelt. Das Attribut `*ngIf` hat entweder den Wert `"true"` oder den Wert `"false"`. Ja nach Wert des Attributes wird das jeweilige `<p>`-Element in den DOM-Baum eingebunden. Also entweder das `<p>`-Element aus den Codezeilen `1`-`4` (bei Wert `"true"`) oder das `<p>`-Element aus den Codezeilen `5`-`8` (bei Wert `"false"`). In einer echten Anwendung ergibt sich der Wert des Attributes/der Direktive meistens aus dem Wert einer boole'schen Variablen oder einem anderen boole'schen Ausdruck.

Das nicht dargestellte Element ist auch nicht Teil des DOMs! Es ist also nicht einfach nur auf `hide` gesetzt, sondern es ist gar nicht im DOM vorhanden. 

Intern wird aus der `*ngIf`-Direktive übrigens ein sogenanntes [*Property-Binding*](./#property-bindings):

```html
<ng-template [ngIf]="true">
  <p>
    Expression is true and ngIf is true.
    This paragraph is in the DOM.
  </p>
</ng-template>
<ng-template [ngIf]="false">
  <p>
    Expression is false and ngIf is false.
    This paragraph is not in the DOM.
  </p>
</ng-template>
```

Die `*ngFor`-Direktive ist etwas komplexer als `*ngIf`. Für `*ngFor` benötigen wir mindestens eine Liste (oder ein Array) und eine Laufvariable, die die Werte aus der Liste annehmen kann. Im folgenden Beispiel ist `i` unsere laufvariable und `[1, 2, 3, 4, 5, 6]` unser Array.

``` html
<div *ngFor="let i of [1, 2, 3, 4, 5, 6]">
  {{ i }}
</div>
``` 

Für jeden Wert aus der Liste wird ein eigenes `<div>`- Element erzeugt. Der DOM-Baum sieht für obiges Beispiel also wie folgt aus (Angular-Attribute weggelassen):

``` html
<div> 1 </div>
<div> 2 </div>
<div> 3 </div>
<div> 4 </div>
<div> 5 </div>
<div> 6 </div>
```

Außerdem stellt `*ngFor` noch einige Hilfsvariablen zur Verfügung, die ebenfalls genutzt werden können:

- `index` (Index des aktuellen Elementes `0, 1, 2, ... `)
- `first` (ist `true`, wenn *erstes* Element, sonst `false`)
- `last` (ist `true`, wenn *letztes* Element, sonst `false`)
- `even` (ist `true`, wenn *Index gerade*, sonst `false`)
- `odd` (ist `true`, wenn *Index ungerade*, sonst `false`)

Folgend ein komplexeres Beispiel unter Verwendung einiger Hilfsvariablen:

``` html linenums="1"
<div *ngFor="let value of [1, 2, 3, 4, 5, 6];
                 index as i;
                 first as f;
                 last as l;
                 odd as o;">
  <div *ngIf="f">Start</div>
  <div [style.color]="o ? 'red' : 'blue'">{{ i }} : {{ value }}</div>
  <div *ngIf="l">Ende</div>
</div>
```

In Zeile `1` ist unsere Laufvariable durch das Array nun `value`. Außerdem wird der jeweilige Wert von `index` in der Variablen `i` (Zeilennummer `2`)
gespeichert, der Wert von `first` in der Variablen `f`(Zeilennummer `3`), der Wert von `last` in der Variablen `l`(Zeilennummer `4`) und der Wert von `odd` in der Variablen `o`(Zeilennummer `5`) - die Hilfsvariable `even` betrachten wir hier nicht, da deren Wert genau der Negation von `odd` entspricht. In Zeile `6` wenden wir die `*ngIf`-Direktive an: ein `<div>` mit dem Inhalt `Start` wird vor dem ersten Element aus dem Array ausgegeben. Für jedes weitere Element nicht mehr. In Zeile `7` erfolgt ein *Property Binding*: die `color`-Eigenschaft bekommt einen Wert zugewiesen. Der Wert ist jedoch abhängig davon, ob `o` wahr ist (dann Wert `red`) oder falsch (dann Wert `blue`).   Zeile `7` zeigt außerdem wie mithilfe von *Interpolation* der Wert von `i` und der Wert von `value`, getrennt mit ` : ` ausgegeben werden. Die Ausgabe ist also:

![ngfor](./files/12_ngfor.png)

!!! question "Aufgabe"
    Informieren Sie sich auch über die `*ngSwitch`-Direktive. Implementieren Sie ein Beispiel, in dem Sie die 3 Direktiven `*ngIf`, `*ngFor` und `*ngSwitch` anwenden. 


