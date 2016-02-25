# Generate Ranges

Javascript does not have a native range method. One can use underscore's or lodash's _.range method or one can write one's own. 

ES5

```
function range1(i){return i?range1(i-1).concat(i):[]}

function range2(i){var x=[];var i=1;while(x.push(i++)<i){};return x}
```

ES6

```
const range1 = len => Object.keys(new Int8Array(len)).map(parseFloat);

const range2 = len => Array.apply(null, {length: len}).map(Number.call, Number);

const range3 = (start, end) => Array.apply(null, Array(end - start)).map((_, i) => start + i);

const range4 = (start, end) => [...Array(end - start)].map((_, i) => start + i);

const range5 = len => Object.keys(Array.apply(null, Array(len)));

const range6 = (start, end) => [...Array(end - start)].map((_, i) => start + i);

const range7 = (start, end) => Array.from(Array(end - start), (_, i) => start + i);

const range = (start, end) => Array.from({length: end - start}).map((_, i) => start + i);


const range8 = n => Array(n).fill().map((v, i) => i)

const range9 = (start, end) => Array(end - start).fill().map((v, i) => i + start)
```