# random-unique-subarray
[![https://nodei.co/npm/random-unique-subarray.png?downloads=true&downloadRank=true&stars=true](https://nodei.co/npm/random-unique-subarray.png?downloads=true&downloadRank=true&stars=true)](https://www.npmjs.com/package/random-unique-subarray)               
Get a random subarray of the specified length with unique elements
## Install
`npm install random-unique-subarray`
## Usage
```
const uniqueSubarr = require('random-unique-subarray');

const arr = [1, 2, 3, 4, 5]

console.log(uniqueSubarr(arr, 2))
// => [2, 5]

console.log(uniqueSubarr(arr, 4))
// => [5, 2, 4, 3]
```
## API
### uniqueSubarr(array, number, options?)     
Returns a random subarray of the specified length with unique elements      
      
__array__         
Type: []       
Description: Array of elements from which a subarray will be created      

__number__      
Type: Number      
Description: Length a created subarray      

__options__     
Type: Object      
      
__options.removeDuplicates__    
Type: Boolean   
Default: false    
Description: Flag whether to delete the same elements in __array__      

__options.key__    
Type: String   
Default: undefined    
Description: if __array__ is array of object. We can remove any duplicate values based on this key object.              
More: https://github.com/tjcafferkey/removeduplicates

## Examples
```
const arr = [1, 2, 2]

console.log(uniqueSubarr(arr, 2))
// => [2, 2] or [1, 2]

console.log(uniqueSubarr(arr, 2, {
      removeDuplicates: true
}))
// => [1, 2]
```

```
const arr = [{
    id: 1,
    name: 'Name1'
}, {
    id: 2,
    name: 'Name2'
}, {
    id: 2,
    name: 'Name2'
}]

console.log(uniqueSubarr(arr, 2, {
    removeDuplicates: true,
    key: 'id'
}))
// => [ { id: 2, name: 'Name2' }, { id: 1, name: 'Name1' } ]
```
