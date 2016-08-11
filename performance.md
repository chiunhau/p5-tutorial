# 進階使用
## 提高整體效能的方法
### 盡量使用原生 js function

雖然 p5 提供許多更為便捷的函式，以數學運算為例，`random()` 擴充了原生 js 裡 `Math.random()` 的不足：

```js
// p5.js
random() //returns between 0 to 1
random(10) //returns between 0 to 10
random(-10, 10) //returns between -10 to 10
random(['apple', 'orange', 'banana']) //returns one of the elements

//native js
Math.random() // returns between 0 to 1
// Nothing else...
```

看起來非常方便，但其實 p5 默默在背後做了大量的工作，可想而知會造成許多效能上的負擔。實際測試後可得，執行一次 `random()` 約花了 0.1 ms，而執行 `Math.random()` 只需約 0.03 ms。因此，若您需要在效能上做優化，則最立竿見影的方式，就是多花點筆墨，乖乖使用、自行擴充原生 js function。

