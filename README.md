# measure [![Build Status](https://travis-ci.org/dubbs/measure.png)](https://travis-ci.org/dubbs/measure)

measure is a library for converting between units and unit systems.

It was created out of the need to adjust recipe amounts based on *servings* on the client-side, while also providing various output types.

There are some inconsistencies between US and Imperial systems.  One example would be, a UK "pint" is 568ml, while a US "pint" is 473ml.  There are many more.  Because of this reason, it is important to state the unit system your are starting with when developing a recipe, unless you are using metric.

## Unit Systems

### Customary (US)

To use US customary units (default):

```js
measure('1 teaspoon').milliliters() // 4.93
measure('1 teaspoon', 'US').milliliters() // 4.93
```

### Imperial (UK and CAN)

To use the Imperial units:

```js
measure('1 teaspoon', 'Imperial').milliliters() // 4.74
```

### Volume

```js
// US and Imperial

// long inputs
measure('1 teaspoon').teaspoons() // 1
measure('1 tablespoon').teaspoons() // 3

// abbrev. inputs
measure('1 1/2 tsp.').teaspoons() // 1.5
measure('1 tbsp.').teaspoons() // 3

// multiple inputs
measure('2 cups and 1 pint').quarts() // 1

// Metric

// long inputs
measure('1 milliliter').milliliters() // 1
measure('1 liter').milliliters() // 1000

// abbrev. inputs
measure('1.5 ml').milliliters() // 1.5
measure('1 l').milliliters() // 1000

// multiple inputs
measure('1 liter and 1 centiliter').milliliters() // 1010
```

### Mass

```js
// US and Imperial

// long inputs
measure('1 ounce').ounces() // 1
measure('1 pound').ounces() // 16

// abbrev. inputs
measure('1 1/2 oz.').ounces() // 1.5
measure('1 lbs.').pounds() // 1

// multiple inputs
measure('7 pounds 8 ounces').ounces() // 120

// Metric

// long inputs
measure('1 gram').grams() // 1
measure('1 kilogram').kilograms() // 1

// abbrev. inputs
measure('1 g.').grams() // 1
measure('1 kg.').kilograms() // 1

// multiple inputs
measure('3 kilograms and 2 grams').kilograms() // 3.002
```

## Operations

```js
measure('1 teaspoon').add('1 teaspoon').teaspoons(); // 2
measure('3 1/4 teaspoon').subtract('2 3/4 teaspoon').teaspoons(); // .5
measure('1 1/2 teaspoon').multiply(3).teaspoons(); // 4.5
measure('6 1/2 teaspoon').divide(2).teaspoons(); // 3.25
```

## Contributing

NPM is used for build and tests, JSHint to enforce style.

### Install Dependencies

```
npm install
```

### Run Tests

```
$(npm bin)/jasmine
```

### Build

Build is executed using pre-commit hooks

## Influences

The great moment.js


