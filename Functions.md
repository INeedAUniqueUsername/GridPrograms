# GridLang (built-in)
## static methods
- `Array(count) -> Array`
- `Array.append(array, element) -> int`
- `Array.make(n: int) -> Array`
- `Array.make(n: int, fn: Function(i: int)) -> Array`
- `Array.make(start: int, end: int) -> Array`
- `Array.make(start: int, end: int, step: int) -> Array`
- `Array.make(start: int, end: int, fn: Function(i: int)) -> Array`
- `Array.make(start: int, end: int, step: int, fn: Function(i: int)) -> Array`
- `Array.map(array, fn, [options], [progressFn: ???) -> Mapped array`
- `Array.reduce(array, fn, [[initial-value], [options], [progressFn]]) -> Result`
- `Console.clear()`
- `input() -> str`
- `input(prompt: str) -> str`
- `input(options: Struct(prompt: str, noEcho: bool)) -> str`
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
## static fields
- `System: Struct(apiVersion: int, args: Array[str], programID: str, runID: int, user: Struct, username: str)`

## Array members
- `filter(fn: Function(element: Any)) -> Array`

## `Table` members
- `filter(by: Function(row: Row)) -> Table`
- `getAt(key: str) -> Row`
- `getAt(key: str, col: str) -> Any`
- `getColumn(col: str) -> Column`
- `groupBy(col: str) -> Array[Table]`
- `setAt(key: str, row: Row | partialRow: Row) -> row`
# Graph
## static methods
- `Graph.create(type: Type, data, options) -> Graph`
# Data
## static methods
- `Data.open(name, dataType, options) -> handle`
- `Data.resolvePath(name, dataType, options) -> gridID`
# File
## static methods
- `File.canAccess(path, accessType) -> true/null`
- `File.directory(path, [options]) -> array of structs`
- `File.read(path, [options]) -> data`
- `File.resolvePath(path) -> pathID`
- `File.write(path, data, [options]) -> data`
# Code
## static methods
- `getDocumentation(library: str)`
  - `library`: one of `*`, `Code`, `Data`, `File`, `Graph`, `GridLang`
- `getNodeStatus`
- `getUIView`
- `getVMInfo`
