## ES6 和 jQuery 对 promise 的实现

## ES6 promise
<http://es6.ruanyifeng.com/#docs/promise>

```javascript
    function foo() {
        var promise = new Promise(function (resolve,  reject) {
            if (/* 成功 */) {
                // 成功
                resolve(succData); 
            }
            else {
                // 失败
                reject(errData); 
            }
        });
        return promise;
    }

    foo().then(
        // 成功
        function(succData) {}, 
        // 失败
        function(errData) {} 
    );
```

## jQuery deferred

<http://www.ruanyifeng.com/blog/2011/08/a_detailed_explanation_of_jquery_deferred_object.html>

```javascript
    function foo() {
        var promise = $.Deferred();
        if (/* 成功 */) {
            // 成功
            promise.resolve(succData); 
        }
        else {
            // 失败
            promise.reject(errData); 
        }

        return promise.promise();
    }
    
    $.when(foo()).then(
        // 成功
        function(succData) {}, 
        // 失败
        function(errData) {} 
    );
```
