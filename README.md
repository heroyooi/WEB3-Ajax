# WEB3-Ajax

- 페이지 전체를 리로딩하지 않고, 인터렉션에 따라서 서버와 통신이 이루어지는 것 => Ajax로 가능하다.
- 마이크로소프트와 네스케이프가 경쟁하던 1999년, 마이크로소프트는 Ajax 기술을 IE에 탑재했다.
  그리고 다른 경쟁 브라우저들도 같은 기능을 탑재하였다. 이때만 해도 Ajax 기술은 이름조차 없었다.
- Ajax가 등장하고 5년 후인 2004년, 구글은 Gmail이라는 서비스를 시장에 손보였다.
  마치 데스크탑 애플리케이션 같이 페이지에 리로딩없이 받은 정보함의 정보를 보여주었다. 당시 구글이 선보인 서비스들은 웹에 대한 많은 사람들의 고정관념을 바꾸었고, 세상은 오랫동안 잠자고 있던 Ajax의 가치를 알아보게 되었다.
- **Asynchronous Javascript And Xml : Ajax**라는 이름을 갖게 되었다.
- Ajax를 통해서 필요한 정보만을 부분적으로 정교하게 낚아채는 낚시꾼이 될 수 있다.

- [기초 파일 저장소](https://github.com/web-n/web2_javascript)


## fetch API 사용

```html
<h2>HTML</h2>HTML is ....
```

```js
fetch('html').then(function(response){
  response.text().then(function(text){
    document.querySelector('article').innerHTML = text;
  })
})
```

- client와 server의 통신
  - clent: fetch('javascript') 자바스크립트라는 파일을 서버에게 응답해줘(요청)
  - server: 응답을 해주는데 시간이 걸릴 수 있다. 많이 걸릴 수도 있다. 서버가 응답할 때까지 다른 일을 할 수 있다.

```js
function callbackme() {
  console.log('response end');
}
fetch('html').then(callbackme);
console.log(1);
console.log(2);
/*
1
2
response end
*/
```
- fetch가 비동기로 실행되는 동안, 아래 콘솔 값들이 먼저 동기적으로 실행된다.