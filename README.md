# setTimeoutpromise1async1
setTimeout promise async区别

// 例子1
console.log('script start')
setTimeout(function(){
    console.log('settimeout')
})

let promise1 = new Promise(function (resolve) {
    console.log('promise1')
    resolve()
    console.log('promise1 end')
}).then(function () {
    console.log('promise2')
})
async function async1(){
    console.log('async1 start');
    await async2();
    console.log('async1 end')
}
async function async2(){
    console.log('async2')
}
async1();
console.log('script end')

输出： script start
      promise1
      promise1 end
      async1 start
      async2
      script end
      promise2
      async1 end
      settimeout
