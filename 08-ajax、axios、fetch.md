Ajax、axios、fetch的区别
Differences among Ajax, axios, and fetch
（1）AJAX
Ajax 即“Asynchronous JavaScript and XML”，是指一种创建交互式网页应用的网页开发技术。它是一种在无需重新加载整个网页的情况下，能够更新部分网页的技术。通过在后台与服务器进行少量数据交换，Ajax 可以使网页实现异步更新。这意味着可以在不重新加载整个网页的情况下，对网页的某部分进行更新。传统的网页（不使用 Ajax）如果需要更新内容，必须重载整个网页页面。其缺点如下：
Ajax stands for "Asynchronous JavaScript and XML." It's a way to make web pages interactive without reloading the whole page. Ajax updates parts of a page by fetching a bit of data from the server behind the scenes. This means updates can happen without a full page refresh. Traditional web pages without Ajax need a full reload to update. However, Ajax is not perfect:
● 本身是针对MVC编程，不符合前端MVVM的浪潮
It's more suited for MVC programming, not quite in line with the front-end MVVM trend.
● 基于原生XHR开发，XHR本身的架构不清晰
Built on the not-so-clear architecture of native XHR.
● 不符合关注分离（Separation of Concerns）的原则
Doesn't quite stick to the Separation of Concerns principle.
● 配置和调用方式非常混乱，而且基于事件的异步模型不友好。
Setup and calling methods can be a bit messy, and its event-based async model isn't friendly.
（2）Fetch
Fetch号称是AJAX的替代品，是在ES6出现的，使用了ES6中的promise对象。Fetch是基于promise设计的。Fetch的代码结构比起ajax简单多。fetch不是ajax的进一步封装，而是原生js，没有使用XMLHttpRequest对象。
Fetch is often seen as AJAX's replacement, coming into play with ES6 and using its promise objects. It's all about promises, making its code structure way simpler than Ajax. Fetch isn't just a rewrap of Ajax; it's native JavaScript and does not use XMLHttpRequest objects.
Fetch的优点：
The cool things about fetch:
● 语法简洁，更加语义化
Straightforward syntax, more semantic.
● 基于标准 Promise 实现，支持 async/await
Built on the standard Promise, supports async/await.
● 更加底层，提供的API丰富（request, response）
More fundamental, comes with a rich set of APIs (request, response).
● 脱离了XHR，是ES规范里新的实现方式
Moves away from XHR, offering a new approach in ES standards.
Fetch的缺点：
The not-so-cool things about fetch:
It only throws errors for network issues, treating 400s and 500s as successes. It won't reject for these server errors unless it's a network problem.
By default, fetch won't carry cookies. You need to tweak it with: fetch(url, {credentials: 'include'}).
Lacks support for aborting requests or controlling timeouts. Workarounds like setTimeout and Promise.reject can't stop the ongoing background process, wasting data.
Can't natively track the progress of requests, unlike XHR.
（3）Axios
Axios 是一种基于Promise封装的HTTP客户端，其特点如下：
Axios is a Promise-based HTTP client. It's features are as follows:
Launches XMLHttpRequests from browsers.
Handles HTTP requests in Node.js.
Supports the Promise API.
Tracks requests and responses.
Transforms requests and responses.
Can cancel requests.
Automatically handles JSON data.
The client side supports to guard against XSRF attacks.




