`Node.js` accepts CLI arguments via `process.argv` by default.

the `processargv.js` file we created for use with `node` allows us to view what arguments we are receiving. it loops through the array when we enter it.

```
node processargv.js jack tom 43
```

provides us with 

```
0 -> /home/vagrant/.nvm/versions/node/v8.9.4/bin/node
1 -> /vagrant/w1/d1-focal/processargv.js
2 -> tom
3 -> jack
4 -> 43
```
first index is the node path
second index is the scipt we are running's path
subsequent indecies are arguements we have passed.

we can log the arguements passed in any scipt we run by adding he following;
```javascript
const args = process.argv;
console.log(args);
```
passing somehting like
```
node sum.js 10 25
```

outputs us with a readable array of the arguements;

``` 
[ '/home/vagrant/.nvm/versions/node/v8.9.4/bin/node',
  '/vagrant/w1/d1-focal/sum.js',
  '10',
  '25' ]
```
you can use the `.slice()` method to remove elements we don't need to reference if we want.

`process.argv.slice(2, 4)` would give us

```
[ '10', '25' ]
```

We can sum the two numbers using process.argv with the following;

```javascript
//assigning command line arguments to a variable and logging them. slciing out pathname indecies
const args = process.argv.slice(2,4);
console.log(args);

//summing the remaining two numbers
console.log(Number(process.argv[2]) + Number(process.argv[3]));
```
this slices the two remaingin arguements for display and sums the two of them. the 
```javascript
Number
```
wrapper converts the array entries we're using back into a number. otherwise we would see the arguements concatenated to

```
1025
```
instead of summed

```
35
```

as we intended.