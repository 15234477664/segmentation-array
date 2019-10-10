# segmentation-array（js将一个数组分成多个数组）
## 1,将数组array分成长度为subGroupLength的小数组并返回新数组
```js
function group(array, subGroupLength) {
      let index = 0;
      let newArray = [];
      while(index < array.length) {
          newArray.push(array.slice(index, index += subGroupLength));
      }
      return newArray;
  }
```
## 2,使用方法：例如
```js
 var Array = [1,2,3,4,5,6,7,8,9,10,11,12];;
 var groupedArray = group(Array, 6);
 得到的groupedArray 数组为：
 groupedArray[[1,2,3,4,5,6],[7,8,9,10,11,12]]
 ```
