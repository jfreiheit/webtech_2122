# Routing

## Single- vs. Multi-Page-Applikationen

Wenn wir durch z.B. dieses Skript hangeln oder Wikipedia, dann stellen wir fest, dass sich nach jedem Klick auf einen Link eine neue HTML-Seite öffnet. Das wird insbesondere deutlich wenn die Entwicklungstools geöffnet sind. Jeder Klick auf einen Hyperlink erwirkt eine neue Anfrage an einen Webserver mit dem Request, eine neue HTML-Seite von diesem Webserver zu laden und im Browser zu öffnen. Es handelt sich dabei also um eine Webanwendung mit vielen (Unter-)Seiten, eine sogenannte *Multi-Page-Applikation (MPA)*. 

Wenn wir stattdessen z.B. die Angular-Seite `https://angular.io` öffnen und uns die Developertools anschauen, dann stellen wir fest, dass kaum HTML-Code im `<body>`-Element enthalten ist. Stattdessen wird der gesamte HTML-Code per JavaScript im Browser eingebunden. Damit werden Inhalte in die Seite immer genau dann eingebunden, wenn sie angezeigt werden sollen. Um zwischen einzelnen Ansichten der Webanwendung zu wechseln, wird keine neue Webseite vom Webserver geholt. Stattdessen bleiben wir stets in derselben HTML-Seite (*Single-Page-Applikation (SPA)*), was sehr gut sichtbar wird, wenn wir die Developertools eingeschaltet lassen und innerhalb der Webanwendung umhernavigieren. Stattdessen werden nur Inhalte (über eine REST-API) vom Server geladen. 

Das Hyperlink-Konzept bei Single-Page-Applikationen ist also ein anderes, als bei Multi-Page-Applikationen. Während in MPAs Hyperlinks verwendet werden, sprechen wir bei SPAs von *Routen*. Das dazugehörige Konzept heißt *Routing*. 

## Aktivieren von Routing

Die einfachste Methode, das Routing für ein Angular-Projekt zu aktivieren, besteht darin, das Projekt mithilfe von 

```bash
ng new projektName
```

zu erzeugen und auf die Frage:

```bash
? Would you like to add Angular routing? (y/N)
```

durch die Eingabe eines `y` zu antworten. Sie müssen expliziz `y` eingeben, da die Standardantwort `N`, also `no` ist. Wenn Sie die Frage mit `yes` beantwortet haben, dann wird das neue Projekt mit der Datei `app-routing.module.ts` im Ordner `src/app` erzeugt. Sollte Ihnen diese Datei fehlen, dann können Sie nachträglich das Routing zu einem existierenden Projekt hinzufügen. 