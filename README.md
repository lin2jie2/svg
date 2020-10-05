# `@reason-react-native/svg`

[![Build Status](https://github.com/reason-react-native/svg/workflows/Build/badge.svg)](https://github.com/reason-react-native/svg/actions)
[![Version](https://img.shields.io/npm/v/@reason-react-native/svg.svg)](https://www.npmjs.com/@reason-react-native/svg)
[![Chat](https://img.shields.io/discord/235176658175262720.svg?logo=discord&colorb=blue)](https://reason-react-native.github.io/discord/)

[ReasonML](https://reasonml.github.io) /
[BuckleScript](https://bucklescript.github.io) bindings for
[`react-native-svg`](https://github.com/react-native-community/react-native-svg).

Exposed as `ReactNativeSvg` module.

`@reason-react-native/svg` X.y._ means it's compatible with `react-native-svg`
X.y._

## Installation

When
[`react-native-svg`](https://github.com/react-native-community/react-native-svg)
is properly installed & configured by following their installation instructions,
you can install the bindings:

```console
npm install @reason-react-native/svg
# or
yarn add @reason-react-native/svg
```

`@reason-react-native/svg` should be added to `bs-dependencies` in your
`bsconfig.json`. Something like

```diff
{
  //...
  "bs-dependencies": [
    "reason-react",
    "reason-react-native",
    // ...
+    "@reason-react-native/svg"
  ],
  //...
}
```

## Usage

Supported :

- SvgXml
- SvgCss
- Svg
- Rect
- Circle
- Ellipse
- Line
- Polygon
- Polyline
- Path
- Text
- TextPath
- Tspan
- Use
- G
- Symbol
- Defs
- Image
- ClipPath
- LinearGradient
- Stop
- RadialGradient
- Mask
- Pattern
- Marker
- ForeignObject

See [definition](.src/ReactNativeSvg.re) for more details.

---

## Demo

```
// src/icons/Star.re

open ReactNative
open ReactNativeSvg;

let radiusOut = 1000.;
let o1x = 1200. +. Js.Math.cos((90. -. 360. /. 5. *. 0.) *. Js.Math._PI /. 180.) *. radiusOut;
let o1y = 1200. -. Js.Math.sin((90. -. 360. /. 5. *. 0.) *. Js.Math._PI /. 180.) *. radiusOut;
let o2x = 1200. +. Js.Math.cos((90. -. 360. /. 5. *. 1.) *. Js.Math._PI /. 180.) *. radiusOut;
let o2y = 1200. -. Js.Math.sin((90. -. 360. /. 5. *. 1.) *. Js.Math._PI /. 180.) *. radiusOut;
let o3x = 1200. +. Js.Math.cos((90. -. 360. /. 5. *. 2.) *. Js.Math._PI /. 180.) *. radiusOut;
let o3y = 1200. -. Js.Math.sin((90. -. 360. /. 5. *. 2.) *. Js.Math._PI /. 180.) *. radiusOut;
let o4x = 1200. +. Js.Math.cos((90. -. 360. /. 5. *. 3.) *. Js.Math._PI /. 180.) *. radiusOut;
let o4y = 1200. -. Js.Math.sin((90. -. 360. /. 5. *. 3.) *. Js.Math._PI /. 180.) *. radiusOut;
let o5x = 1200. +. Js.Math.cos((90. -. 360. /. 5. *. 4.) *. Js.Math._PI /. 180.) *. radiusOut;
let o5y = 1200. -. Js.Math.sin((90. -. 360. /. 5. *. 4.) *. Js.Math._PI /. 180.) *. radiusOut;
let radiusIn = 560.;
let i1x = 1200. +. Js.Math.cos((54. -. 360. /. 5. *. 0.) *. Js.Math._PI /. 180.) *. radiusIn;
let i1y = 1200. -. Js.Math.sin((54. -. 360. /. 5. *. 0.) *. Js.Math._PI /. 180.) *. radiusIn;
let i2x = 1200. +. Js.Math.cos((54. -. 360. /. 5. *. 1.) *. Js.Math._PI /. 180.) *. radiusIn;
let i2y = 1200. -. Js.Math.sin((54. -. 360. /. 5. *. 1.) *. Js.Math._PI /. 180.) *. radiusIn;
let i3x = 1200. +. Js.Math.cos((54. -. 360. /. 5. *. 2.) *. Js.Math._PI /. 180.) *. radiusIn;
let i3y = 1200. -. Js.Math.sin((54. -. 360. /. 5. *. 2.) *. Js.Math._PI /. 180.) *. radiusIn;
let i4x = 1200. +. Js.Math.cos((54. -. 360. /. 5. *. 3.) *. Js.Math._PI /. 180.) *. radiusIn;
let i4y = 1200. -. Js.Math.sin((54. -. 360. /. 5. *. 3.) *. Js.Math._PI /. 180.) *. radiusIn;
let i5x = 1200. +. Js.Math.cos((54. -. 360. /. 5. *. 4.) *. Js.Math._PI /. 180.) *. radiusIn;
let i5y = 1200. -. Js.Math.sin((54. -. 360. /. 5. *. 4.) *. Js.Math._PI /. 180.) *. radiusIn;

[@react.component]
let make = (~color: string, ~fill: bool = false, ~size: float = 24., ~weight: float = 160.) => {
	<Svg width={size -> Style.dp} height={size -> Style.dp} viewBox="0 0 2400 2400">
		<Path
			d={j|M $o1x,$o1y L $i1x,$i1y L $o2x,$o2y L $i2x,$i2y L $o3x,$o3y L $i3x,$i3y L $o4x,$o4y L $i4x,$i4y L $o5x,$o5y L $i5x,$i5y z|j}
			stroke={color}
			strokeWidth={weight -> Style.dp}
			strokeLinejoin=`round
			strokeLinecap=`round
			fill={fill ? color : "none"}
		/>
	</Svg>
}

```

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
