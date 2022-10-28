# study-webflux
crud webflux로 구현해보기!
<br/></br>

## 목차

1. [파일 구조](#파일-구조)
2. [DataBase](#DataBase)

### 파일 구조

```

		
```

## WebFlux란 무엇일까
Reactive-stack의 웹 프레임워크로 클라이언트와 서버에서 리액티브 애플리케이션 개발을 위한 논블로킹 리액티브 스트림을 지원항한다              

#### 왜 web flux가 등장했을까?
 논블로킹으로 동작하는 웹 스택의 필요성 때문에 등장하게 되었다. 기존 SpringMVC의 Servlet API v3.1 부터 논블로킹 I/O를 위한 API를 제공했었다. 하지만, 이외의 동기적으로 처리하는 모듈과 블로킹 방식의 API들이 완벽한 논블로킹 환경의 개발을 할 수 없었고, 비동기 논블로킹 환경의 서버인 Netty와의 연동을 위해 Spring은 새로운 API가 필요했다. (그래서 웹 플럭스가 두두등장 해버렷다아..)    

#### MVC vs WebFlux      
MVC는 하나의 요청에 대해 하나의 스레드가 쓰인다. 그래서 다수의 요청을 대비하여 미리 스레드 풀을 생성해놓으며, 각 요청마다 스레드를 할당하여 처리한다. 
이 방식은 아래와 같은 문제가 생긴다.
- **블로킹 콜**          
동작중인 스레드가 블로킹 상태가 되면 다른 스레드에서 CPU 사용을 위해 컨텍스트 스위칭이 일어나게 된다. 만약 서버의 대부분이 이렇게 구성되어 있다면, 많은 컨텍스트 스위칭 일어나게 되고, 결국 내부 블로킹 콜이 차지하는 비중만큼 컨텍스트 스위칭의 오버헤드가 발생한다
- **많은 요청량**         
요청량이 증가한다면 스레드 수도 이에 비례하여 증가한다. 스레드 수가 증가한다면 서버가 감당해내지 못할 만큼의 메모리를 먹을 수 있다. 


## 주의 사항


## DataBase
우리가 흔히 사용하는 JPA는 WebFlux에서 보통 사용하지 않는다. R2DBC를 사용한다! (JDBC는 블로킹이고, R2DBC가 논블로킹) JPA와 R2DBC의 성능 차이가 커서 JPA는 권장하지 않는다고 한다.<br/>

Webflux R2DBC vs JPA <br/>  https://technology.amis.nl/software-development/performance-and-tuning/spring-blocking-vs-non-blocking-r2dbc-vs-jdbc-and-webflux-vs-web-mvc/



