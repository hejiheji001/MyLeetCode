# MyLeetCode

## Easy
1. https://leetcode.com/problems/two-sum/description/

### Worst:
```JavaScript

var twoSum = function(nums, target) {
    var dupEntries = getAllIndexes(nums, target / 2);
    if(nums.indexOf(target / 2) > -1 && dupEntries.length == 2){
        return dupEntries;
    }else{
        return nums.filter((n, i) => (nums.indexOf(target - n) >= 0 && target - n != nums[i])).map(n => nums.indexOf(n));
    }
};

var getAllIndexes = function(arr, val) {
    var indexes = [];
    var i = 0;
    for(i = 0; i < arr.length; i++){
        if (arr[i] === val){
            indexes.push(i);
        }
    }
    return indexes;
};

```
### Better:
```JavaScript
var twoSum = function(nums, target) {
    while(nums.length > 0){
        var i1 = nums.length - 1;
        var t = target - nums.pop();
        var i2 = nums.indexOf(t);
        if(i2 > -1){
            return [i2, i1];
        }
    }  
};
```
