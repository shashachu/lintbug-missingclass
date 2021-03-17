Demo project demonstrating how Kotlin custom views defined in the application module trigger false-positive `MissingClass` lint errors.

## Repro

Run `./gradlew lintDebug`

## Expected

No errors

## Actual

```
  Errors found:
  
  /Users/shasha/code/shashachu/lintbug/dynamicfeature/src/main/res/layout/my_layout.xml:6: Error: Class referenced in the layout file, com.pinterest.lintbug.MyKotlinView, was not found in the project or the libraries [MissingClass]
      <com.pinterest.lintbug.MyKotlinView
      ^
```

Note that `MyJavaView` does not trigger any errors.