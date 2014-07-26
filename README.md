# level-dat

LevelDB storage backend for [Dat](https://github.com/maxogden/dat)

``` js
npm install level-dat
```

## Usage

``` js
var ldat = require('level-dat')

db = ldat(db) // where db is levelup instance
db.on('ready', function() {
  db.createReadStream().on('data', console.log)
})
```

## API

In general the API is the same as the [levelup api](https://github.com/rvagg/node-levelup)

#### `db.put(key, value, [opts], [cb])`

Insert a key and value. Use `opts.version = number` to specify the version.

#### `db.get(key, [opts], cb)`

Get a key and value and version.

#### `db.del(key, [cb])`

Delete a key.

#### `db.count(cb)`

Count all rows in the database.

#### `db.getMeta(key, cb)`

Get a meta key.

#### `db.putMeta(key, value, [opts], [cb])`

Insert a meta key.

#### `db.createReadStream([opts])`

Create a read stream to the database. Data includes the version.

#### `db.createValueStream([opts])`

Only get the values.

#### `db.createKeyStream([opts])`

Only get the keys.

#### `db.createVersionStream(key, [opts])`

Get all stored versions of a key.

#### `db.createWriteStream([opts])`

Stream data into the database. Data can include versions.

#### `db.createChangesReadStream([opts])`

Get a change feed stream from the database. Set `options.change` to only get a partial stream and `options.data` to get the data as well.

#### `db.createChangesWriteStream([opts])`

Pipe a change feed into the change write stream to replicate a database.

# License

MIT
