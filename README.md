## 🐛 Bug Report

Flow does not seem to be finding the shipped flow type definitions after upgrading to v6. I can get flow to find the type definitions by running:

```
cp node_modules/immer/dist/{immer,index}.js.flow
```

## Link to repro

https://github.com/esturcke/immer-flow-bug

## To Reproduce

1. Run flow

    ```
    yarn flow
    ```

## Observed behavior

```
Warning ┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈ src/App.js:3:8

Importing from an untyped module makes it any and is not safe! Did you mean to add // @flow to the top of immer?
(untyped-import)

     1│ // @flow
     2│ import React from "react";
     3│ import produce from "immer";
     4│ import logo from "./logo.svg";
     5│ import "./App.css";
     6│



Found 1 warning
✨  Done in 4.57s.
```

## Expected behavior

No flow warnings.

## Environment

- **Immer version: 6.0.2**

