# `@reason-react-native/async-storage`

[![Build Status](https://github.com/reason-react-native/async-storage/workflows/Build/badge.svg)](https://github.com/reason-react-native/async-storage/actions)
[![Version](https://img.shields.io/npm/v/@reason-react-native/async-storage.svg)](https://www.npmjs.com/@reason-react-native/async-storage)
[![Chat](https://img.shields.io/discord/235176658175262720.svg?logo=discord&colorb=blue)](https://reason-react-native.github.io/discord/)

[ReScript](https://rescript-lang.org) / [Reason](https://reasonml.github.io) bindings for
[`@react-native-community/async-storage`](https://github.com/react-native-community/async-storage).

Exposed as `ReactNativeAsyncStorage` module.

`@reason-react-native/async-storage` X.y.\* means it's compatible with
`@react-native-community/async-storage` X.y.\*

## Installation

When
[`@react-native-community/async-storage`](https://github.com/react-native-community/async-storage)
is properly installed & configured by following their installation instructions,
you can install the bindings:

```console
npm install @reason-react-native/async-storage
# or
yarn add @reason-react-native/async-storage
```

`@reason-react-native/async-storage` should be added to `bs-dependencies` in
your `bsconfig.json`:

```diff
{
  //...
  "bs-dependencies": [
    "reason-react",
    "reason-react-native",
    // ...
+    "@reason-react-native/async-storage"
  ],
  //...
}
```

## Usage

### Types

#### `ReactNativeAsyncStorage.asyncStorageState`

```reason
{
  .
  [@bs.meth] "getItem": unit => Js.Promise.t(Js.Null.t(string)),
  [@bs.meth] "setItem": string => Js.Promise.t(unit),
  [@bs.meth] "mergeItem": string => Js.Promise.t(unit),
  [@bs.meth] "removeItem": unit => Js.Promise.t(unit),
}
```

### Methods

#### `ReactNativeAsyncStorage.getItem`

```reason
string => Js.Promise.t(Js.Null.t(string))
```

#### `ReactNativeAsyncStorage.setItem`

```reason
(string, string) => Js.Promise.t(unit)
```

#### `ReactNativeAsyncStorage.removeItem`

```reason
string => Js.Promise.t(unit)
```

#### `ReactNativeAsyncStorage.mergeItem`

```reason
(string, string) => Js.Promise.t(unit)
```

#### `ReactNativeAsyncStorage.clear`

```reason
unit => Js.Promise.t(unit)
```

#### `ReactNativeAsyncStorage.getAllKeys`

```reason
unit => Js.Promise.t(Js.Null.t(array(string)))
```

#### `ReactNativeAsyncStorage.multiGet`

```reason
array(string) => Js.Promise.t(array((string, Js.Null.t(string))))
```

#### `ReactNativeAsyncStorage.multiSet`

```reason
array((string, string)) => Js.Promise.t(unit)
```

#### `ReactNativeAsyncStorage.multiMerge`

```reason
array((string, string)) => Js.Promise.t(unit)
```

#### `ReactNativeAsyncStorage.multiRemove`

```reason
array(string) => Js.Promise.t(unit)
```

#### `ReactNativeAsyncStorage.flushGetRequests`

```reason
unit => unit
```

#### `ReactNativeAsyncStorage.useAsyncStorage`

```reason
string => asyncStorageState
```

---

## Changelog

Check the [changelog](./CHANGELOG.md) for more informations about recent
releases.

---

## Contribute

Read the
[contribution guidelines](https://github.com/reason-react-native/.github/blob/master/CONTRIBUTING.md)
before contributing.

## Code of Conduct

We want this community to be friendly and respectful to each other. Please read
[our full code of conduct](https://github.com/reason-react-native/.github/blob/master/CODE_OF_CONDUCT.md)
so that you can understand what actions will and will not be tolerated.
