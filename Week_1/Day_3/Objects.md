most things in JS are objects inlcuding arrays and functions

keys are always strings

when accessing a key by brackets, must call as a string:

```javascript
object["key"];
```

can use a `for...in` loop to loop through the key value pairs of an object

```javascript
const planetMoons = {
  mercury: 0,
  venus: 0,
  earth: 1,
  mars: 2,
  jupiter: 67,
  saturn: 62,
  uranus: 27,
  neptune: 14
};

for (planet in planetMoons) { 
  let numberOfMoons = planetMoons[planet];
  console.log(`Planet: ${planet} planet, # of moons ${numberOfMoons}`);
};
```
loops through each palnet and logs the planet key and planet key value (moon #).

`for...in` can inherit peroperties from it's prototype chain or method names so you may need ot use `.hasOwnProperty()`