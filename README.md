### JSPRO
#### Polyfills
` map `
```js
Array.prototype.myMap = function (cb) {
  let temp = [];
  for (let i = 0; i < this.length; i++) {
    temp.push(cb(this[i], i, this));
  }
  return temp;
};

````

`filter`

````js
// arr.filter((curr,i,arr))
Array.prototype.myFilter = function (cb) {
  let temp = [];
  for (let i = 0; i < this.length; i++) {
  let filterValue = cb(this[i], i, this)
  if(filterValue) temp.push(filterValue);
  }
  return temp;
};

````

`reduce`
> If intialValue provided then iteration start with zero/0
> if initialValue is not provided it will take acc = arr[0] and iteration start from 1
````js
Array.prototype.myReduce = function (cb, initialValue=this[0]) {
  if (this.length == 0) return null;
  let i=1;
if(initialValue !=this[0])  i=0
  let acc = initialValue;
  for (i; i < this.length; i++) {
    acc = cb(acc, this[i], i, this);
  }
  return acc;
};
````