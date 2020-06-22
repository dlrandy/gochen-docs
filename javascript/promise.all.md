``` javascript 

"use strict";

Promise.allMe = function (promises) {
  if (!(promises != null && typeof promises[Symbol.iterator] === "function")) {
    throw new Error(`TypeError: ${typeof promises} ${promises} is not iterable (cannot read property Symbol(Symbol.iterator))
          at Function…}`);
  }

  return new Promise(function (resovle, reject) {
    const caches = [];

    for (let p of promises) {
      Promise.resolve(p).then(function (p) {
        caches.push(p);

        if (caches.length === promises.length) {
          return resovle(caches);
        }
      }, function (p) {
        return reject(p);
      });
    }
  });
};

console.log(Promise.allMe([12]).then(e => console.log(e)));
```