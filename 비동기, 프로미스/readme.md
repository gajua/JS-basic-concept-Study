## 동기 프로그래밍
```js
console.log(1)
    function delayTask(){
        // 3초간 대기 가정
     const delayUntil = Date.now() + 3000;
        while(Date.now() < delayUntil) {}
        console.log(2)
    }
delayTask()
console.log(3)
```
========
### 타이머 funtion을 이용한 비동기 프로그래밍
```js
console.log(1)
setTimeout(function(){
    console.log(2)
},3000)
console.log(3)
```
사용자와의 상호작용 및 웹 서버와의 통신에
 Web API(DOM API, Timer function, HTTP Request)를 이용하면
비동기 프로그래밍이 가능하다

========

## callback 함수 기반 웹서버와 비동기 통신
### 웹서버 로그인 처리
```js
function loginUser(id, passwd){
  //웹서버 통신에 2초 소요 가정
setTimeout(()=>{
  //로그인 가정
  if(id ==="sewon" && passwd === 1111){
      console.log(`${id}님 환영합니다.`)
  } else{
      console.log("회원정보를 확인하여주세요.")
  }
}, 2000)
}

loginUser("sewon", 1111)

```
비동기처리에서 callback지옥을 막기위해 생긴것이 promise
> 이 구조의 코딩을 피해 then을 사용해 오류가 난 위치를 찾기 용이하다(가독성이 좋다)


## 정리
 - JS는 싱글스레드 환경에서 작동하지만 비동기처리를 하는 방법은 함수가 선언이 되면 콜스텍(call stack)에 쌓이고, 비동기함수(Ajax, 이벤트리스너, setTime함수 등)는 콜백큐, 혹은 이벤트큐 (Queue)라는 곳에 잠시 대기하다가 콜스텍에 쌓인 함수들이 전부 실행되면(텅 비면) 그 때 하나씩 콜스텍으로 다시 보내져 실행이된다.









