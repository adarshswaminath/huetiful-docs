---
title: Color temperature
date: '2023-09-29'
draft: false
summary: Utilities for retrieving color temperature related meta.
layout: PostSimple
canonicalUrl: https://prjctimg.github.io/huetiful/api/color-temperature
---

Colors can be classified into warm and cool colors which in turn have ranges(in Kelvins). For example blue is a cool color and the blue hue is found within a certain numerical range (degrees if we are looking at the _hue_ channel). Using assumptions such as these allows us to determine which colors we want in our designs.

We can use _isWarm_ and _isCool_ to determine if a color is approximately warm or cool. The utilities rely on _hue_ ranges to determine the temperature of the color.

#### isWarm

**Parameters:**
`(color: Color):boolean`
_color_ The color to check the temperature.

**Returns:**
True or false

**Description:**
Checks if a color can be roughly classified as a warm color. Returns true if color is a warm color else false.

```javascript

import { isWarm } from 'huetiful-js'

let sample = [
  "#00ffdc",
  "#00ff78",
  "#00c000",
  "#007e00",
  "#164100",
  "#ffff00",
  "#310000",
  "#3e0000",
  "#4e0000",
  "#600000",
  "#720000",
];



console.log(isWarm(sample[7]));
//true

console.log(map(sample, isWarm));


// [
  false, true,  false,
  false, false, false,
  true,  true,  true,
  true,  true
]

```

#### isCool

**Parameters:**
`(color: Color):boolean`
_color_ The color to check the temperature.

**Returns:**
True or false

**Description:**
Checks if a color can be roughly classified as a cool color. Returns true if color is a warm color else false.

```javascript
import { isCool } from 'huetiful-js'

let sample = [
  "#00ffdc",
  "#00ff78",
  "#00c000",
  "#007e00",
  "#164100",
  "#ffff00",
  "#310000",
  "#3e0000",
  "#4e0000",
  "#600000",
  "#720000",
];


console.log(isCool(sample[7]));
// false

console.log(map(sample, isCool));

// [
  true,  false, true,
  true,  true,  true,
  false, false, false,
  false, false
]




```

#### minTemp

**Parameters:**
`(color: Color): number`
_color_ The color to check its minimum temperature.

**Returns**
The minimum temperature in Kelvins.

**Description:**
Checks the approximate minimum temperature that a color can have without losing its original hue. Does not take into account overtones (for now)

**Example:**

```javascript

```

#### maxTemp

**Parameters:**
`(color: Color): number`
_color_ The color to check its minimum temperature.

**Returns**
The minimum temperature in Kelvins.

**Description:**
Checks the approximate minimum temperature that a color can have without losing its original hue. Does not take into account overtones (for now)

**Example:**

```javascript

```

> Please note that precision of the utilities is limited and improvement suggestions are welcome. Feel free to open an issue for suggestions.
