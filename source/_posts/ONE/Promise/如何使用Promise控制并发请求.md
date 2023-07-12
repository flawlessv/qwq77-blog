---
title: 如何使用Promise控制并发请求
tags:
  - Promise
---


在现代Web开发中，异步请求已经成为了必不可少的一部分。然而，当我们需要同时处理多个请求时，如何避免请求之间的冲突和混乱呢？这就是今天我们要探讨的话题——如何使用Promise控制并发请求。

在JavaScript中可以通过`Promise.all()`、`Promise.race()`、`async/await`等不同方式来实现对异步并发任务的控制。以下是一种使用`Promise.all()`方法实现并发控制的示例：

### Promise.all()

```
const urls = ["url1", "url2", ... ,"url100"]; 
const maxConcurrentNum = 10; // 最大并发数 
// 数组分块，chunk表示每批次数量，返回数组二维数组 
function chunk(arr, chunk) { 
  let result = []; 
  for (let i = 0, len = arr.length; i < len; i += chunk) { 
    result.push(arr.slice(i, i + chunk)); 
   } 
   return result; 
 }

// 异步请求方法 
function fetchUrl(url) { 
  return new Promise((resolve, reject) => { 
    fetch(url) 
      .then(res => resolve(res)) 
      .catch(err => reject(err)); 
     }); 
   }

// 对url数组进行分块处理
const chunkedUrls = chunk(urls, maxConcurrentNum);

(async function () {
  try {
    for (let urls of chunkedUrls) {
      const promises = urls.map(url => fetchUrl(url));
      // 等待所有promises完成执行，并将结果存入results数组中
      const results = await Promise.all(promises);
      console.log('results:', results);
    }
  } catch (err) {
   console.error(err);
  }
})();


```

以上代码通过将数组分成多个数目相等的小数组，每次最多只开启`maxConcurrentNum`个并发请求，以此来控制并发数量。每当一组请求完成后再发送新的一批请求，可以实现对异步任务的并发控制。

### Promise.race()

以下是使用Promise.race()方法来控制并发的示例代码：

```
const promiselist = [];
for (let i = 0; i < 100; i++) {
  const promise = fetch(`https://example.com/data${i}.json`);
  promiselist.push(promise);
}
Promise.race(promiselist)
  .then(response => {
    // handle the fastest response here
  })
  .catch(error => {
    console.error(error);
  });

```

### async/await

以下是使用async/await方式控制并发请求的示例代码：

```
async function getData() {
  const promiselist = [];
  for (let i = 0; i < 100; i++) {
    const promise = fetch(`https://example.com/data${i}.json`);
    promiselist.push(promise);
  }
  const responses = await Promise.all(promiselist);
  for (const response of responses) {
    // handle each response here 
  }
}

getData().catch(error => {
  console.error(error);
});

```

在上面的代码中，我们首先创建了一个async函数，并在该函数中使用for循环来发送所有的请求，并将每个请求的Promise对象存储在一个数组中。 然后，我们使用await关键字来异步等待所有`Promise对象`都被解决，并将解决值存储在一个数组中。 最后，我们在处理每个响应时对数组进行迭代。

如果我们只需要等待最快的请求，我们可以使用`Promise.race()`方法，并将其包装在一个`async函数`中。 这种方法与使用`Promise.all()`的方式相似，只需使用不同的Promise方法即可。

以下是使用`async/await`方式控制并发请求的示例代码，其中使用`Promise.race()`方法：

```
async function getData() {
  const promiselist = [];
  for (let i = 0; i < 100; i++) {
    const promise = fetch(`https://example.com/data${i}.json`);
    promiselist.push(promise);
  }
  const response = await Promise.race(promiselist);
  // handle the fastest response here
}

getData().catch(error => {
  console.error(error);
});

```

在上述代码中，我们使用`async函数`来生成`Promise对象`，然后使用`Promise.race()`方法等待最快的解决`Promise对象`，并处理其解决值。

除了`Promise.all()`和`Promise.race()`以及`async/await`等方法外，还有其他用于控制并发请求的可行方法，例如：  

1.  手动控制计数器  
    可以使用变量来手动计数，以控制请求并发数。例如，在循环中，当计数器达到最大并发请求数时，将其用于等待请求完成，然后递增计数器以允许下一个请求。  
    以下是手动控制计数器的示例代码：

```
function getData() {
 const limit = 5; // maximum concurrent requests
 const dataUrls = ['https://example.com/data1.json', 
                   'https://example.com/data2.json',
                   'https://example.com/data3.json',
                   'https://example.com/data4.json',
                   'https://example.com/data5.json',
                   'https://example.com/data6.json'];

 let counter = 0;
 const getDataPromise = dataUrl => {
   return new Promise((resolve, reject) => {
     fetch(dataUrl)
       .then(response => {
         counter--;
         resolve(response);
       })
       .catch(error => {
         counter--;
         reject(error);
       });
   });
 };

 const getDataPromises = dataUrls.map(dataUrl => {
   if (counter < limit) {
     counter++;
     return getDataPromise(dataUrl);
   } else {
     return new Promise(resolve => {
       const interval = setInterval(() => {
         if (counter < limit) {
           counter++;
           clearInterval(interval);
           resolve(getDataPromise(dataUrl));
         }
       }, 100);
     });
   }
 });

 Promise.all(getDataPromises)
   .then(responses => {
     for (const response of responses) {
       // handle each response here
     }
   })
   .catch(error => {
     console.error(error);
   });
}

getData();

```

在上面的代码中，我们手动地使用计数器来控制最大并发请求数，然后使用`setInterval函数`来等待可用的请求槽位。

2.  使用第三方库

此外，还有一些第三方库可以使用，例如`async.js`和`p-limit`等。`p-limit`是一个专门用于控制`Promise并发的小型库`。可以在`p-limit`文档中找到更多信息和示例。

总结
--

通过掌握`Promise`的使用，我们可以轻松应对并发请求，让我们的Web应用更加流畅，用户更加满意。所以，别让并发请求成为你的噩梦，让`Promise`来帮你解决吧！
x