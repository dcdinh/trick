# Function array in js
## find function
#### The _find_ keyword allows you to grab the first instance of an element from an array that matches your search criteria. Let's look at a simple example. Create find.ts and add the following code:
 ```js
const items = [
    { name: 'jon', age: 20 },
    {name: 'linda', age: 22 },
    {name: 'jon', age: 40}
]
const jon = items.find((item) =>{
    // your other condition here
    return item.name === 'jon'
});
console.log(jon) // jon = {name: 'jon', age: 40}
```
## filter function
#### _filter_ is similar to find except it returns all items that match a search criterion. Let'screate a new file called filter.ts and add the following code:
```js
const filterItems = [
    { name: 'jon', age: 20 },
    {name: 'linda', age: 25 },
    {name: 'jon', age: 40}
]
const results = filterItems.filter(
    (item, index) => {
        // your other condition here
        return item.age > 20;
    }
); // return array includes item have age greater 25
console.log(results); 
// results = [ { name: 'linda', age: 25 }, { name: 'jon', age: 40 } ]
```
## map function
#### The _map_ function is one of the more important array functions to know about for ES6 style coding. It appears frequently in React component creation in order to create a collection of component elements from an array of data. _map_ will return new array with item after run code in callback function
```js
const items = [
    { name: 'jon', age: 20 },
    {name: 'linda', age: 25 },
    {name: 'jon', age: 40}
]
const results = items.map(
    (item) => {
    item.age+=10;
    /// your logic code here
    return item
    }
); // return array of item with age increment 10 from origin array
/* results = [
  { name: 'jon', age: 30 },
  { name: 'linda', age: 35 },
  { name: 'jon', age: 50 }
]
*/
```
## reduce function
#### The _reduce_ function is an aggregator that takes each element in an array and, based on custom logic, creates a **single final value**.
```js
const items = [ 2,5,7,10 ]
const initialValue = 0;
// output: calculator sum of item in items array
// FIRST way
const sumOfItemsFirst = items.reduce((initialValue, currentValue) => {
  // initialValue +=  currentValue;
  // your logic code here
  return initialValue+currentValue;
});
// SECOND way
initialValue = 0;
const sumOfItemsSecond = items.reduce((totalValue, currentValue) => {
  totalValue += currentValue;
  // your logic code here
  return totalValue;
}, initialValue);
console.log(sumOfItemsSecond);
```
## some and every function
#### These functions are designed to test for certain criteria. So, they only return true or false . some tests to see whether any element in an array meets certain criteria and every tests whether all elements meet a certain criteria.
```js
const widgets = [
{id: 1, color: 'blue' },
{id: 2, color: 'yellow' },
{id: 3, color: 'orange' },
{id: 4, color: 'blue' }
]
console.log('some are blue', widgets.some(item => {
  return item.color === 'blue';
})); // true
console.log('every one is blue', widgets.every(item => {
return item.color === 'blue';})); // false
```
