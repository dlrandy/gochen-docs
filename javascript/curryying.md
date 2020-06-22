``` javascript
function currying_sum(x){// accumulator func
    return function (y){//  accumulator func
        return function(z) { // target func
            return x + y + z;
        }
    }
}

function _sum3(x, y, z){
    return x + y + z;
}

function sum3(x) {
    return y => {
        return z => _sum3(x, y, z);
    }
}


function curry(fn) { 
  if (typeof fn !== 'function') { 
    throw new Error('必须函数作为参数！')
  }

  let len = fn.length;
  let nestFn = fn;
  function accumulator(...params) { 
    len -= params.length;
    nestFn = nestFn.bind(null, ...params);
    return len > 0 ? accumulator: nestFn();
  }

  return accumulator;

}



console.log(curry(_sum3)(1,2)(3))
```

``` javascript
function curry(fn) { 
  if (typeof fn !== 'function') { 
    throw new Error('必须函数作为参数！')
  }

  const len = fn.length;
  const cache_params = [];

  function accumulator(...params) { 
    if (len <= cache_params.length) { 
      return fn.apply(null, cache_params);
    }
    cache_params.push(...params);
    return accumulator;
  }

  return accumulator;

}
``