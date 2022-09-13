
# GridLang (built-in)

## static methods

`input() -> str`

`input(prompt: str) -> str`

`input(options: Struct(prompt: str, noEcho: bool)) -> str`

`print(data: Any...) -> True`

`DateTime(day: int, month: int, year: int) -> DateTime`

`DateTime(day: int, month: int, year: int, hour: int, minute: int, second: int, millisecond: int) -> DateTime`

`TimeSpam(milliseconds: int) -> TimeSpan`

`abs(x: float) -> float`

`Integer(x: Any) -> int`: x as integer

`max(x: int...) -> int`: highest value

`min(x: int...) -> int`: lowest value

`random() -> float`: random number `x` such that `0 <= x < 1.0`

`Char(x: Any) -> str`

`String(x: Any) -> str`

`String.find(s: str, x: str) -> str`: Index of `x` in `s` if found, otherwise `-1`

`String.left(s: str, len: int) -> str`

`String.len(s: str) -> int`

`String.mid(s: str, pos: int, len: int) -> str`

`String.right(s: str, len: int) -> str`

`deserialize(data: str) -> Any`

`isa(value: Any, type: Type) -> bool`

`keysof(value: Any) -> Array[String]`

`serialize(value: Any) -> str`

`typeof(value: str) -> Type`

`VMEvalInSandbox(func: Function) -> Any`

`Table(data: struct) -> Table`

## static fields

`System: Struct(apiVersion: int, args: Array[str], programID: str, runID: int, user: Struct, username: str)`


## `Table` members
`filter(by: Function(row: Row)) -> Table`

`getAt(key: str) -> Row`

`getAt(key: str, col: str) -> Any`

`getColumn(col: str) -> Column`

`groupBy(col: str) -> Array[Table]`


# `Code`
`getDocumentation(library: str)`

- `library` values: `*`, `Code`, `Data`, `File`, `Graph`, `GridLang`

`getNodeStatus`

`getUIView`

`getVMInfo`
