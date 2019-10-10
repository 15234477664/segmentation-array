# segmentation-array（js将一个数组分成多个数组）
# 方法一
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
# 方法二
```js
  data () {
    return {
      tableData: [
        {
          id: '1',
          date: '2016-05-02',
          name: '王小虎1',
          address: '上海市普陀区金沙江路 100 弄'
        },
        {
          id: '2',
          date: '2016-05-04',
          name: '王小虎2',
          address: '上海市普陀区金沙江路 200 弄'
        },
        {
          id: '3',
          date: '2016-05-01',
          name: '王小虎3',
          address: '上海市普陀区金沙江路 300 弄'
        },
        {
          id: '4',
          date: '2016-05-03',
          name: '王小虎4',
          address: '上海市普陀区金沙江路 400 弄'
        },
        {
          id: '5',
          date: '2016-05-02',
          name: '王小虎1',
          address: '上海市普陀区金沙江路 100 弄'
        },
        {
          id: '6',
          date: '2016-05-04',
          name: '王小虎2',
          address: '上海市普陀区金沙江路 200 弄'
        },
        {
          id: '7',
          date: '2016-05-01',
          name: '王小虎3',
          address: '上海市普陀区金沙江路 300 弄'
        },
        {
          id: '8',
          date: '2016-05-03',
          name: '王小虎4',
          address: '上海市普陀区金沙江路 400 弄'
        }
      ],
      tempData: [],
      num: 6 // 每组分为的条数
    }
  },
  methods: {
    init () {
      let length = this.tableData.length
      let tempLength = Math.ceil(length / this.num)
      for (let i = 0; i < tempLength;i++) {
          this.tempData[i] = []
          let start = i * this.num
          let end = start + this.num
          if (end > length) {
              end = length
          }
          for (let j = start; j < end; j++) {
            this.tempData[i].push(this.tableData[j])
          }
      }
      console.log(this.tempData)
    },
  }
  ```
