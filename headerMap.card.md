```py
filter lang:js
import wires.xxx-js # listIndex, mapIdx
```

# headerMap

Turn tabular data and a header into a list of dictionaries `{head => value}`.

Type of `d`

```purescript
d.headers : List String
d.rows : List List Number
```

Usage

```js
headerMap(d.headers, d.rows)
```

#### Example(s)
###### Input `d`

```js
{ headers: ['x', 'y', 'name']
, rows: [
    [1, 2, 'a'],
    [3, 4, 'b']
  ]
}
```

###### Output

```js
[
  { x: 1, y: 2, name: 'a' },
  { x: 3, y: 4, name: 'b' }
]
```

## Sourcecode `js`


```js
var headerMap = R.compose(R.fromPairs, mapIdx((key, idx) => [key, d[idx]]))
```

## Dependencies`js`

```js
var listIndex = R.uncurryN(2, R.pipe(R.lensIndex, R.view)
var mapIdx = R.addIndex(R.map)
```
