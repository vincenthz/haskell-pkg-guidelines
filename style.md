
This is just a guideline: think of this as a general rule of thumb, not something to just do regardless of contextes.

It's a much trimmed version of [tibbe's haskell-style](https://github.com/tibbe/haskell-style-guide/blob/master/haskell-style.md),
which some similar key points and an emphasis on just being a rule of thumb, and not emitting a good/bad judgement value on differing
styles.

## General idea

* General indent with 4 spaces
* Indent `where` with 2 spaces
* List/Fields commas on beginning of line
* Keep line length to a reasonable value; anything above 120 chars should be multi-lined.
* Align Fields and values on multi lined statements.


## Examples

Where indentation:

```
function a = something
  where
    something = ..
```

Commas:

```
myList =
    [ largeValue1
    , largeValue2
    , largeValue3
    ]
  
StructConstructor
    { a = 1
    , b = "b-value"
    , c = 1.34
    }
```

Alignment:

```
data Struct = Struct
    { field1          :: Char
    , superFieldName2 :: String
    , something       :: Int
    }

myCallToFunction parameter1 parameter2
                 anotherLongParameter3
                 anotherVeryLongParameter
                 (nestedValue 123
                              "abc"
                              12.435)
```


