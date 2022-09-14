# GridLang (built-in)
## static methods
- `Array(count: int) -> Array`
- `Array.append(array: Array, element: Any) -> int`
- `Array.make(n: int) -> Array`
- `Array.make(n: int, fn: Function(i: int)) -> Array`
- `Array.make(start: int, end: int) -> Array`
- `Array.make(start: int, end: int, step: int) -> Array`
- `Array.make(start: int, end: int, fn: Function(i: int)) -> Array`
- `Array.make(start: int, end: int, step: int, fn: Function(i: int)) -> Array`
- `Array.map(array: Array, fn: Function(element: Any), [options: { ??? }], [progressFn: ???]) -> Mapped array`
- `Array.reduce(array: Array, fn: Function(element: Any), [[initial-value: Any], [options: { ??? }], [progressFn: Function(???)]]) -> Result`
- `Console.clear()`
- `input() -> str`
- `input(prompt: str) -> str`
- `input(options: { prompt: str, noEcho: bool }) -> str`
- `print(data: Any...) -> True`
- `DateTime(day: int, month: int, year: int) -> DateTime`
- `DateTime(day: int, month: int, year: int, hour: int, minute: int, second: int, millisecond: int) -> DateTime`
- `TimeSpam(milliseconds: int) -> TimeSpan`
- `abs(x: float) -> float`
- `Integer(x: Any) -> int`: x as integer
- `max(x: int...) -> int`: highest value
- `min(x: int...) -> int`: lowest value
- `random() -> float`: random number `x` such that `0 <= x < 1.0`
- `Char(x: Any) -> str`
- `String(x: Any) -> str`
- `String.find(s: str, x: str) -> str`: Index of `x` in `s` if found, otherwise `-1`
- `String.left(s: str, len: int) -> str`
- `String.len(s: str) -> int`
- `String.mid(s: str, pos: int, len: int) -> str`
- `String.right(s: str, len: int) -> str`
- `deserialize(data: str) -> Any`
- `isa(value: Any, type: Type) -> bool`
- `keysof(value: Any) -> Array[String]`
- `serialize(value: Any) -> str`
- `typeof(value: str) -> Type`
- `VMEvalInSandbox(func: Function) -> Any`
- `Table(data: struct) -> Table`
- `Table.insert(table: Table, row: Row) -> int`: Returns number of rows
- `Table.insertColumn(table: Table, name: str) -> Column`
- `Table.insertColumns(table: Table, name: str, type) -> Column`
- `Table.insertColumns(table: Table, name: str, values) -> Column`
- `Table.insertColumns(table: Table, name: str, type: Type, values) -> Column`
- `Table.insertColumns(table: Table, name: str, index) -> Column`
- `Table.insertColumns(table: Table, name: str, type, index) -> Column`
- `Table.insertColumns(table: Table, name: str, type, values, index) -> Column`
- `Table.map(table: Table, struct: Struct, options = None, progressFn = None) -> Table`
## constants
- `System: { apiVersion: int, args: Array[str], programID: str, runID: int, user: Struct, username: str }`

## Array class
### instance methods
- `filter(fn: Function(element: Any)) -> Array`

## Table class
### instance methods
- `filter(by: Function(row: Row)) -> Table`
- `getAt(key: str) -> Row`
- `getAt(key: str, col: str) -> Any`
- `getColumn(col: str) -> Column`
- `groupBy(col: str) -> Array[Table]`
- `setAt(key: str, row: Row | partialRow: Row) -> row`

# Code namespace
## static methods
- `Code.getDocumentation(library: str)`
  - `library`: one of `*`, `Code`, `Data`, `File`, `Graph`, `GridLang`
- `Code.getNodeStatus`
- `Code.getUIView`
- `Code.getVMInfo`
# Data namespace
## static methods
- `Data.open(name, dataType, options) -> handle`
- `Data.resolvePath(name, dataType, options) -> gridID`
# File namespace
## static methods
- `File.canAccess(path, accessType) -> true/null`
- `File.directory(path, [options]) -> array of structs`
- `File.read(path, [options]) -> data`
- `File.resolvePath(path) -> pathID`
- `File.write(path, data, [options]) -> data`
# Graph namespace
## static methods
- `Graph.create(type: str, data, options: Array[Series] | { renderType: str, series: Array[Series] | Series }) -> Graph`
  - `type`: one of `line`, `XY`
  - `options.renderType`: one of `graphDesc`
  - `Series: { xAxis: { data: Array }, yAxis: { data: Array }, color: { data: Array }, lineConnection: { lineBy, orderBy, color, size }, style: { data }, size: { data } }`
# HTTP namespace
-`HTTP.get(url, [headers, [options]]) -> data`
-`JSON.read(jsonString) -> value`
-`JSON.write(value) -> jsonString`

# Image namespace
## static methods
-`Image.mandelbrot(x: float, y: float, pixelSize: float, width: int, height: int, options: { cores: int } = ???, progressFn: Function(progress: { ??? }) = None) -> image`
# Math namespace
## static methods
-`acos(x: float) -> float`
-`asin(x: float) -> float`
-`atan(x: float) -> float`
-`atan(y: float, x: float) -> float`	
-`average(x: float...) -> float	`
-`ceil(x: float) -> float`
-`cos(x: float) -> float`
-`divmod(x: float, y: float) -> [quotient: float, remainder: float]`
-`exp(x: float) -> float`
-`floor(x: float) -> float`
-`log(x: float, base: float = 10) -> float`
-`median(x: float...) -> float`
-`sin(x: float) -> float`
-`sqrt(x: float) -> float`
-`sum(x: float...) -> float`
-`tan(x: float) -> float`
-`Vector() -> Vector`
-`Vector(3) -> Vector`
-`e: float`
-`pi: float`
-`tau: float`

# UI namespace
## static methods
- `Bitmap(width, height, [backgroundColor]) -> bitmap`
- `Canvas(struct) -> canvas`
- `UI.create(class: str, options: { ... } = None) -> control`
  - `class`
    - `"2DGraph" | "button" | "canvas" | "dial" | "edit" | "form" | "image" | "layoutGrid" | "listbox" | "markdown" | "table" | "text"`
  - `options`: Sets the fields on the control
- `UI.addCommand(desc, func) -> command`
- `UI.dialog(desc, initialValues, options) -> exitCode`
- `UI.getDocumentation() -> table`
- `UI.stop(exitCode) -> true/error`
- `UI.run() -> exitCode`
- `UI.setCommands(arrayOfCommands) -> true/null`
- `UI.show(control)`

## Control class
### instance fields
- `border`
  - `"boxed" | "default" | "narrow" | "page" | "raised" | "thinLine" | "thinLineWide" | "wide"`
  - `{ top: str, left: str, right: str, bottom: str }`
- `class: str = "uiControl"`
- `id: int`
## Canvas class
### instance methods
- `arc(x: float, y: float, radius: float, startAngle: float, endAngle: float, counterClockwise: bool = False) -> bool`
- `beginPath() -> bool`
- `circle(x: float, y: float, radius: float) -> bool`
- `clearRect() -> bool`
- `clearRect(x: float, y: float, width: float, height: float) -> bool`
- `closePath() -> bool`
- `createSprite(desc: Image, options: { pos: Vector2, seq: int } = None) -> Sprite`
- `drawImage(image: Image, x: float, y: float) -> bool`
- `fill() -> bool`
- `fillRect(x: float, y: float, width: float, height: float) -> bool`
- `lineTo(x: float, y: float) -> bool`
- `moveTo(x: float, y: float) -> bool`
- `outline() -> bool`
- `rect(x: float, y: float, width: float, height: float) -> bool`
- `setResource(name: str, image: Image) -> bool`
- `sprite_moveTo(spriteID: int, pos: Vector2) -> bool`
- `renderHTMLCanvasCommands() -> bool`
### instance fields
- `fillStyle: Color`
- `length: int = 1`
- `lineStyle: Color`
- `lineWidth: float = 1.0`

- `onclick: Function(x: float, y: float)`
- `onsize: Function(x: float, y: float)`

## Bitmap class
### static methods
- `arc(x: float, y: float, radius: float, startAngle: float, endAngle: float, counterClockwise: bool = False) -> bool`
- `beginPath() -> bool`
- `circle(x: float, y: float, radius: float) -> bool`
- `clearRect() -> bool`
- `clearRect(x: float, y: float, width: float, height: float) -> bool`
- `closePath() -> bool`
- `drawImage(image: Image, x: float, y: float) -> bool`
- `fill() -> bool`
- `fillRect(x: float, y: float, width: float, height: float) -> bool`
- `getScaled(width: float, height: float) -> Image`
- `getSlice(x: float, y: float, width: float, height: float) -> Image`
- `lineTo(x: float, y: float) -> bool`
- `moveTo(x: float, y: float) -> bool`
- `outline() -> bool`
- `rect(x: float, y: float, width: float, height: float) -> bool`
- `setFillStyle(style: str) -> bool`
- `setLineStyle(style: str) -> bool`

### instance fields
- `width: int`
- `height: int`

# User namespace
## static methods
-`User.addToGroup(groupID, userID|groupID) -> bool | Error	`
-`User.createGroup(groupName) -> { ??? }`
-`User.getInfo(userID|groupID) -> { ??? }`
-`User.removeFromGroup(groupID, userID|groupID) -> bool | Error`
