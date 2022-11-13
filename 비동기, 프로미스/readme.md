// 동기 프로그래밍
console.log(1)
    function delayTask(){
        // 3초간 대기 가정
     const delayUntil = Date.now() + 3000;
        while(Date.now() < delayUntil) {}
        console.log(2)
    }
delayTask()
console.log(3)

========
// 타이머 funtion을 이용한 비동기 프로그래밍

console.log(1)
setTimeout(function(){
    console.log(2)
},3000)
console.log(3)

사용자와의 상호작용 및 웹 서버와의 통신에
 Web API(DOM API, Timer function, HTTP Request)를 이용하면
비동기 프로그래밍이 가능하다

========

// callback 함수 기반 웹서버와 비동기 통신
// 웹서버 로그인 처리
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


비동기처리에서 callback지옥을 막기위해 생긴것이 promise
> 이 구조의 코딩을 피해 then을 사용해 오류가 난 위치를 찾기 용이하다(가독성이 좋다)












