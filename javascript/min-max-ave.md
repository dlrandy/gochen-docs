### 平均值
``` javascript
// solution1 
function average(array){
    let sum = 0;
    for (let i = 0; i < array.length; i++>) {

    }
    return sum / array.length;
}
// solution2
 function average(array){
     let sum = 0;
     array.forEach(num =>sum += num);

     return sum / array.length;
}
// solution3 
function average(array){
    if(array.length <= 0 ){
        return 0;
    }
    return array.reduce((acc, next) => acc+ next, 0) / array.length;
}




```
### 求和
``` javascript
const arrSum = arr => arr.reduce((s, i) => s+=i,0)
```

### 求最大值
``` javascript
const arrMax = arr => Math.max(...arr);
```