# Dateiupload

Wir wollen hier zeigen, wie man in Angular und mit Node.js

- eine Dateiupload per Drag & Drop gestaltet und
- ein Backend so baut, dass es in einer MongoDB Bilder und andere Dateien speichern und abrufen kann.

Wir erstellen uns dazu eine Angular-Anwendung `fileupload`:

```bash
ng new fileupload
```

Wir fügen [Bootstrap](https://valor-software.com/ngx-bootstrap/#/documentation#getting-started) hinzu und erstellen eine Komponente `drag-drop`:

```bash
cd fileupload
ng add ngx-bootstrap
ng g c drag-drop
```

!!! tip
	Sollte es bei der Installation von Bootstrap Probleme geben, dann bleibt Ihnen immernoch die einfache Variante, Bootstrap über ein CDN direkt in die `index.html` einzubinden, mit z.B. `<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.1.3/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-1BmE4kWBq78iYhFldvKuhfTAU6auU8tT94WrHftjDbrCEXSU1oBoqyl2QvZ6jIW3" crossorigin="anonymous">` (siehe [Bootstrap](https://getbootstrap.com/docs/5.1/getting-started/introduction/))


## Backend

Wir erstellen uns ein Backend für den Dateiupload:

```bash
mkdir backend-fileupload
cd backend-fileupload 
npm init
npm install cors express mongoose multer dotenv
npm install nodemon --save-dev
```

Wir erstellen eine `db.js` und eine `models/file.js`:

=== "db.js"
	```js linenums="1"
	module.exports = {
	    db: 'mongodb://localhost:27017/fileupload'
	}
	```

=== "models/file.js"
	```js linenums="1"
	const mongoose = require('mongoose');
	const Schema = mongoose.Schema;

	// Define Schema
	let userSchema = new Schema({
	    _id: mongoose.Schema.Types.ObjectId,
	    file: {
	        type: Array
	    },
	}, {
	    collection: 'files'
	})

	module.exports = mongoose.model('File', userSchema)
	```

