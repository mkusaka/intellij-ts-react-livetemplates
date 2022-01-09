# IntelliJ Live Templates for Typescript and React

[![Download](https://img.shields.io/badge/Get-from%20Jetbrains%20Marketplace-brightgreen)](https://plugins.jetbrains.com/plugin/16796-live-templates-for-typescript-and-react)
[![Build and verify](https://github.com/lukasbach/intellij-ts-react-livetemplates/actions/workflows/verify.yml/badge.svg)](https://github.com/lukasbach/intellij-ts-react-livetemplates/actions/workflows/verify.yml)
[![Deploy](https://github.com/lukasbach/intellij-ts-react-livetemplates/actions/workflows/deploy.yml/badge.svg)](https://github.com/lukasbach/intellij-ts-react-livetemplates/actions/workflows/deploy.yml)
![JetBrains plugins](https://img.shields.io/jetbrains/plugin/d/16796)
![JetBrains Plugins](https://img.shields.io/jetbrains/plugin/r/rating/16796)

Live templates for Typescript and typed React code, for IntelliJ Idea,
Webstorm, PHPStorm and other Jetbrains IDEs. With sensible variable
expressions and useful skeleton templates.

Supported templates:

- `uses`: _React.useState()_
- `usee`: _React.useEffect()_
- `useh`: _React use Hook_
- `rfc`: _React Functional Component_
- `rfct`: _React typed Functional Component_
- `rfr`: _React forward Ref_
- `int`: _Typescript Interface_
- `type`: _Typescript Type_
- `arr`: _Anonymous arrow function_
- `el`: _JSX element_
- `rcctx`: _React create new Context with type, hook and provider_
- `ifs`: _import fs_
- `ipath`: _import path_
- `funarr`: _Arrow function variable_
- `fun`: _Function_
- `asyncarr`: _Async anonymous arrow function_
- `prom`: _New Promise_
- `timeout`: _setTimeout_
- `interval`: _setInterval_
- `usem`: _React.useMemo()_
- `usec`: _React.useCallback()_


## Template code


### React.useState()

Invoked via `uses`.

```
const [$VAR$, set$VAR_SET$] = useState($DEFAULT_VAL$);$END$
```
Variables:

|Name|Expression|Default Value|Skip if defined|
|----|----------|-------------|---------------|
|`VAR`|`-`||false|
|`VAR_SET`|`capitalize(VAR)`||false|
|`DEFAULT_VAL`|`-`||false|

### React.useEffect()

Invoked via `usee`.

```
useEffect(() => {
    $END$
}, [$1$]);
```
Variables:

|Name|Expression|Default Value|Skip if defined|
|----|----------|-------------|---------------|
|`1`|`-`||false|

### React use Hook

Invoked via `useh`.

```
const $3$ = use$1$($2$);$END$
```
Variables:

|Name|Expression|Default Value|Skip if defined|
|----|----------|-------------|---------------|
|`1`|`completeSmart()`||false|
|`2`|`completeSmart()`|{}|false|
|`3`|`-`||false|

### React Functional Component

Invoked via `rfc`.

```
export const $1$: React.FC<{$2$}> = props => {
    return (
        <$3$>
            $END$
        </$3$>
    );
};
```
Variables:

|Name|Expression|Default Value|Skip if defined|
|----|----------|-------------|---------------|
|`1`|`-`||false|
|`2`|`-`||false|
|`3`|`-`||false|

### React typed Functional Component

Invoked via `rfct`.

```
export const $1$ = <$2$>(props: PropsWithChildren<$3$>) => {
    return (
        <$4$>
            $END$
        </$4$>
    );
};
```
Variables:

|Name|Expression|Default Value|Skip if defined|
|----|----------|-------------|---------------|
|`1`|`-`||false|
|`2`|`-`||false|
|`3`|`-`||false|
|`4`|`-`||false|

### React forward Ref

Invoked via `rfr`.

```
export const $COMP$ = React.forwardRef<HTML$ELEMENT_TYPE$ | null, $PROPS$>((props, ref) => {
    const elementRef = useRef<HTML$ELEMENT_TYPE$>(null);
    useImperativeHandle<HTML$ELEMENT_TYPE$ | null, HTML$ELEMENT_TYPE$ | null>(
        ref,
        () => elementRef.current && {
            ...elementRef.current,
        },
    );
    $END$
    return (
        <$INNER_COMP$ ref={elementRef} />
    );
});
```
Variables:

|Name|Expression|Default Value|Skip if defined|
|----|----------|-------------|---------------|
|`COMP`|`-`||false|
|`ELEMENT_TYPE`|`completeSmart()`||false|
|`PROPS`|`-`|{}|false|
|`INNER_COMP`|`completeSmart()`||false|

### Typescript Interface

Invoked via `int`.

```
export interface $1$ {
    $END$
}
```
Variables:

|Name|Expression|Default Value|Skip if defined|
|----|----------|-------------|---------------|
|`1`|`-`||false|

### Typescript Type

Invoked via `type`.

```
export type $1$ = {
    $END$
}
```
Variables:

|Name|Expression|Default Value|Skip if defined|
|----|----------|-------------|---------------|
|`1`|`-`||false|

### Anonymous arrow function

Invoked via `arr`.

```
($1$) => $2$
```
Variables:

|Name|Expression|Default Value|Skip if defined|
|----|----------|-------------|---------------|
|`1`|`-`||false|
|`2`|`-`||false|

### JSX element

Invoked via `el`.

```
<$ELEMENT$PROPS$>
    $END$
</$ELEMENT$>
```
Variables:

|Name|Expression|Default Value|Skip if defined|
|----|----------|-------------|---------------|
|`ELEMENT`|`-`|div|false|
|`PROPS`|`-`||false|

### React create new Context with type, hook and provider

Invoked via `rcctx`.

```
type $CONTEXT_NAME_TYPE$ContextType = {
    $END$
};

const $CONTEXT_NAME$Context = React.createContext<$CONTEXT_NAME$ContextType>($DEFAULT_VALUE$);
export const use$CONTEXT_NAME_HOOK$ = () => React.useContext($CONTEXT_NAME$Context);

export const $CONTEXT_NAME_PROVIDER$Provider: React.FC = props => {
    return (
        <$CONTEXT_NAME$Context.Provider value={$VAL$}>
            {props.children}
        </$CONTEXT_NAME$Context.Provider>
    );
};
```
Variables:

|Name|Expression|Default Value|Skip if defined|
|----|----------|-------------|---------------|
|`CONTEXT_NAME`|`-`||false|
|`CONTEXT_NAME_TYPE`|`CONTEXT_NAME`||false|
|`DEFAULT_VALUE`|`-`|{}|false|
|`CONTEXT_NAME_HOOK`|`capitalize(CONTEXT_NAME)`||false|
|`CONTEXT_NAME_PROVIDER`|`capitalize(CONTEXT_NAME)`||false|
|`VAL`|`-`|{}|false|

### import fs

Invoked via `ifs`.

```
import fs from 'fs';
```

### import path

Invoked via `ipath`.

```
import path from 'path';
```

### Arrow function variable

Invoked via `funarr`.

```
const $VAR_NAME$ = ($PARAM$) => $END$;
```
Variables:

|Name|Expression|Default Value|Skip if defined|
|----|----------|-------------|---------------|
|`VAR_NAME`|`jsSuggestVariableName()`||false|
|`PARAM`|`-`||false|

### Function

Invoked via `fun`.

```
function $FUNCTION_NAME$($PARAM$) {
    $END$
}
```
Variables:

|Name|Expression|Default Value|Skip if defined|
|----|----------|-------------|---------------|
|`FUNCTION_NAME`|`-`||false|
|`PARAM`|`-`||false|

### Async anonymous arrow function

Invoked via `asyncarr`.

```
async ($1$) => $2$
```
Variables:

|Name|Expression|Default Value|Skip if defined|
|----|----------|-------------|---------------|
|`1`|`-`||false|
|`2`|`-`||false|

### New Promise

Invoked via `prom`.

```
new Promise<$TYPE$((res, rej) => {
    $END$
});
```
Variables:

|Name|Expression|Default Value|Skip if defined|
|----|----------|-------------|---------------|
|`TYPE`|`-`|void|false|

### setTimeout

Invoked via `timeout`.

```
setTimeout(() => $END$, $TIME$);
```
Variables:

|Name|Expression|Default Value|Skip if defined|
|----|----------|-------------|---------------|
|`TIME`|`completeSmart()`||false|

### setInterval

Invoked via `interval`.

```
setInterval(() => $END$, $TIME$);
```
Variables:

|Name|Expression|Default Value|Skip if defined|
|----|----------|-------------|---------------|
|`TIME`|`completeSmart()`||false|

### React.useMemo()

Invoked via `usem`.

```
const $VAR$ = useMemo(() => $RETURN$, [$DEP$]);
```
Variables:

|Name|Expression|Default Value|Skip if defined|
|----|----------|-------------|---------------|
|`RETURN`|`completeSmart()`||false|
|`DEP`|`completeSmart()`||false|
|`VAR`|`-`||false|

### React.useCallback()

Invoked via `usec`.

```
const $VAR$ = useCallback(() => $RETURN$, [$DEP$]);
```
Variables:

|Name|Expression|Default Value|Skip if defined|
|----|----------|-------------|---------------|
|`RETURN`|`completeSmart()`||false|
|`DEP`|`completeSmart()`||false|
|`VAR`|`-`||false|

# Golang code templates
Useful live templates and code completion for Goland IDE.

Install `settings.zip`: https://www.jetbrains.com/help/go/sharing-live-templates.html#import

## Golang
### if err not nil return
Checks that err is not nil and writes return statement with default return values, except last - error. It would be wrapped with [errors.Wrap](https://godoc.org/github.com/pkg/errors#Wrap).
`errors.Wrap` can be easily replaced with fmt.Errorf or any other function

Abbreviation:
```
errr
```
Template text:
```go
if $ERR$ != nil {
 return $RETURN$errors.Wrap($ERR$, "$TEXT$")$END$
}
```
Applicable in Go: statement

| Name     | Expression                                               | Default value | Skip if defined |
|----------|----------------------------------------------------------|---------------|-----------------|
| $ERR$    | `errorVariable()`                                        | "err"         |                 |
| $RETURN$ | `regularExpression(defaultReturnValues, "([^,]*$)", "")` |               |                 |
| $TEXT$   | `errorVariable()`                                        |               |                 |


### errors.Wrap
Abbreviation:
```
wrap
```
Template text:
```go
$END$ errors.Wrap($ERR$, "$TEXT$")
```
Applicable in Go: expression, statement

| Name     | Expression                                                     | Default value | Skip if defined |
|----------|----------------------------------------------------------------|---------------|-----------------|
| $ERR$    | `errorVariable()`                                              | "err"         |                 |
| $TEXT$   | `errorVariable()`                                              |               |                 |

### Variadic slice declaration
Creates shortcut for in-place slice declarations. Compiler should inline function call, so this function free to use.
Was created as a replacement for constructions like `[]string{}` -> `ss()`, `[]int{}` -> `is()`, etc.

Abbreviation:
```
ss
```
Template text:
```go
func $NAME$$END$(slice ...$TYPE$) []$TYPE$ { return slice }
```
Applicable in Go: file

| Name     | Expression                                                     | Default value | Skip if defined |
|----------|----------------------------------------------------------------|---------------|-----------------|
| $TYPE$   |                                                                | "string"      |                 |
| $NAME$   |                                                                | "ss"          |                 |

### Json field names in camelCase
Sometimes we need to declare json fields not in snake_case format (goland used it by default), but in camelCase.
This pattern also can be applied to any other tags, like `sql`, `pg`, `csv`.

Abbreviation:
```
jsonc
```
Template text:
```go
json:"$FIELD_NAME$"
```
Applicable in Go: tag literal

| Name         | Expression                                                     | Default value | Skip if defined |
|--------------|----------------------------------------------------------------|---------------|-----------------|
| $FIELD_NAME$ | camelCase(fieldName())                                         |               |                 |

### Sort
Generate sort interface for your type. When go core team would add generics you may delete this.

Abbreviation:
```
sort
```
Template text:
```go
type $SLICE$ []$TYPE$
func ($REC$ $SLICE$) Len() int           { return len($REC$) }
func ($REC$ $SLICE$) Swap(i, j int)      { $REC$[i], $REC$[j] = $REC$[j], $REC$[i] }
func ($REC$ $SLICE$) Less(i, j int) bool {
    panic("implement me")$END$
}
```
Applicable in Go: file

| Name     | Expression                                                     | Default value | Skip if defined |
|----------|----------------------------------------------------------------|---------------|-----------------|
| $TYPE$   | complete()                                                     | "Some"        |                 |
| $SLICE$  |                                                                | "SomeSlice"   |                 |
| $REC$    |                                                                | "ss"          |                 |

### In
Checks that value is in slice of some type. In easy way.

Abbreviation:
```
in
```

Template text:
```go
func isIn$Type$Slice(v $type$, values ...$type$) bool {
	for i := range values {
		if values[i] == v {
			return true
		}
	}
	return false
}
```

Applicable in Go: file

| Name     | Expression                                                     | Default value | Skip if defined |
|----------|----------------------------------------------------------------|---------------|-----------------|
| $type$   |                                                                | "string"      |                 |
| $Type$   |                                                                | "String"      |                 |

### Safe getter
Generates getter for struct field in protoc-gen-go style.
Why do you need it?
It allows access to nested fields without worrying about nil pointers.

```go
type Value struct {
    Field1 *Struct1
}
type Struct1 struct {
    Field2 *Struct2
}
type Struct2 struct {
    UsefulString *string
}

var value *Value
var _ = value.SafeField1().SafeField2().SafeUsefulString()

func (v *Value) SafeField1() *Struct1 {
	if v == nil {
		return nil
	}
	return v.Field1
}
func (s *Struct1) SafeField2() *Struct2 {
	if s == nil {
		return nil
	}
	return s.Field2
}
func (s *Struct2) SafeUsefulString() *string {
	if s == nil {
		return nil
	}
	return s.UsefulString
}
```

Abbreviation:
```
getter
```

Template text:
```go
func ($RECEIVER$ *$TYPE_1$) Safe$NAME$() $TYPE_2$ {
	if $RECEIVER$ == nil {
		return $RESULT$$END$
	}
	return $RECEIVER$.$NAME$
}
```

## Contributions

Feel free to contribute to existing or new templates with issues or pull requests.

To test if your changes are working, clone the repo and run the gradle script `runIde`.

Do not update the documentation in the readme.md or plugin.xml files, they are updated
automatically.

## comand

build
```sh
$ ./gradlew build
```

install
cmd + , > plugin > install from Disk... > open ./build/distributions/ts_react_livetemplates_with_goland-1.0.3.zip
