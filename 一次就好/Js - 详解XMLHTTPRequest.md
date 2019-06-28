### 原生ajax写法：
```javascript
// post
var request = new XMLHttpRequest()
request.open('POST', '/my/url', true)
request.setRequestHeader(
  'Content-Type',
  'application/x-www-form-urlencoded; charset=UTF-8'
)
request.send(data)

// get
var request = new XMLHttpRequest()
request.open('GET', '/my/url', true)
request.onload = function() {
  if (request.status >= 200 && request.status < 400) {
    // Success!
    var resp = request.responseText
  } else {
    // We reached our target server, but it returned an error
  }
}
request.onerror = function() {
  // There was a connection error of some sort
}
request.send()

// 稍微封装一下
function ajax({ url, method, headers, data, success, error }) {
  headers = headers || 'application/x-www-form-urlencoded; charset=UTF-8'
  let request = new XMLHttpRequest()
  request.open(method, url, true)
  request.setRequestHeader('Content-type', headers)
  request.onload = function(progressEvent) {
    let response = progressEvent.currentTarget
    let { status, statusText, responseText, responseUrl } = response
    if (status > 199 && status < 400) {
      if (success) success(responseText)
    } else {
      if (error) error(statusText)
    }
  }
  request.onerror = function(error) {
    console.error(error)
  }
  request.send(data)
}
```