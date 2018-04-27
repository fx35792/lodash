# lodash
#### 一、lodash中pullAllBy的应用
在前端项目中，经常会遇到处理数组数据的时候，很多时候后端接口返给我们前端的数据不是我们想要的数组数据，所以经常需要我们前端自己对数据进行回炉重造。
而lodash插件则给我们处理数组、对象、字符串等功能，下面则展示一个demo，去除数组当中不符合我们想要数据。
##### 如何得到去除 "confirm_tag"：1数据
元数据
```
 "datas": [{
    "amount": 0,
    "confirm_tag": 2,
    "fee": 54394,
},{
    "amount": 0,
    "confirm_tag": 1,
    "fee": 54394,
},{
    "amount": 0,
    "confirm_tag": 2,
    "fee": 54394,
},]
```
最终数据想要的数据：
```
"datas": [{
    "amount": 0,
    "confirm_tag": 2,
    "fee": 54394,
},{
    "amount": 0,
    "confirm_tag": 2,
    "fee": 54394,
},]
```
1.传统JS做法
```
let newList = [];
let newData = datas;
for (let i = 0; i < newData.length; i++) {
    let newDataObj = {};
    if (newData[i].confirm_tag == 1) {
        newDataObj = newData[i];
        newList.push(newDataObj);
    }
}
console.log(newList)
```
2.lodash做法
```
var newData = datas;
_.pullAllBy(newData, [{ 'confirm_tag': 1 }], 'confirm_tag');
console.log(newData);
```
#### 相关链接

lodash官网: https://lodash.com/

lodash中pullAllBy的应用：https://lodash.com/docs/4.17.10#pullAllBy 





