# Generate Ranges

Javascript does not have a native range method. One can use underscore's or lodash's _.range method or one can write one's own. 

ES5

```javascript
function range(i){return i?range(i-1).concat(i):[]}

function range(i){var x=[];var i=1;while(x.push(i++)<i){};return x}
```

ES6

```javascript
const range = (start, end) => Array.apply(null, Array(end - start)).map((_, i) => start + i);

const range = len => Array.apply(null, {length: len}).map(Number.call, Number);

const range = (start, end) => [...Array(end - start)].map((_, i) => start + i);

const range = len => Object.keys(Array.apply(null, Array(len)));

const range = (start, end) => [...Array(end - start)].map((_, i) => start + i);

const range = (start, end) => Array.from(Array(end - start), (_, i) => start + i);

const range = (start, end) => Array.from({length: end - start}).map((_, i) => start + i);

const range = n => Array(n).fill().map((v, i) => i)

const range = (start, end) => Array(end - start).fill().map((v, i) => i + start)
```