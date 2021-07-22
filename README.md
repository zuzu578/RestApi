# RestApi
# RestApi 란 무엇일까?
  - Rest 아키텍쳐 스타일을 따르는 API 
  - 그렇다면 Rest 아키텍쳐는 분산 하이퍼미디어 시스템 ( 웹 ) 을 위한 아키텍쳐 스타일 
  - 아키텍쳐 스타일은 제약조건의 집합 이다.
  - 즉 , rest api 라는 것은 rest 제약조건 즉 rest 아키텍쳐를 따르는 api 라는것이다.
# REST 를 구성하는 스타일 
  = client-server 
  - stateless
  - cache 
  - uniform interface 
  - layered system
  - code-on-demand ( 서버에서 코드를 클라이언트에 보내서 실행해야한다 ex): javascript )
# Uniform Interface 의 제약조건 
  -identification of resources => 리소스가 uri로 식별되면 된다 
  -manipulation of resources through representations => representation 전송을 통해 리소스를 조작해야한다 (crud 할때 메시지에 표현을 담아 전송을 해야한다)
  -self-descriptive messages => 
  -hypermedia as the engine of application stats(HATEOAS) =>
# Self-descriptive message 
  =메시지는 스스로를 설명해야한다 는 의미 
  :ex) GET / HTTP/1.1 
  HOST : www.xxx.co.kr 
  => 목적지를 추가했으므로 self-descriptive 메시지이다.
  
  :ex) HTTP/1.1 200 ok 
  Content-Type : application / json 
  [{"op" : "remove" , "path":"/a/b/c"}]
  => 컨텐츠 타입이 무엇인지 명시를 해주어 클라이언트가 해당데이터를 이애할수있기때문에 self-descriptive 메시지이다 
  
  self-descriptive message ===> 결국 , 클라이언트가 api 통신을 하고나서 , 나오는 메시지가 스스로를 설명해야한다 
  ===> ex) 어떤 데이터를 주고받았는지 , 어떤방식으로 데이터를 주고받았는지 , 어떻게 어디로 데이터를 전달하고 전송을 받았는지 이러한 정보들을 담는 메시지와 , client 가 그 메시지를 이해할수 있게 해야한다.
  
  # HATEOAS
  = 애플리케이션의 상태는 Hyperlink를 이용해 전이되어야한다. 
  ex) html 의 a tag 를 통해 그다음 상태로 전이된다.
  
  # Uniform interface의 필요성 
  - 독립적인 진화를 위함
  # 독립적인 진화?
  서버와 클라이언트가 각각 독립적으로 진화한다
  서버의 기능이 변경되어도 클라이언트를 업데이트할 필요가 없다.
  rest 를 만들게된계기 ==> 독립적인 진화를 달성하기 위함 
  결국 uniform interface를 갖추지 못하면 rest api 라고 부르기 어렵다.
  
  # WEB
  - 웹은 rest 아키텍쳐 스타일을 잘 따르고 있다
  - 웹페이지를 변경했다고 웹브라우저를 업데이트할필요는 없다.
  - 웹브라우저를 업데이트 했다고 웹페이지를 변경할 필요도 없다.
  - Http 명세가 변경되어도 웹은 잘 동작한다.
  - Html 명세가 변경되어도 웹은 잘 동작한다. 
  
  # 웹의 상호운용성 (interoperability)에 대한 집착
  - Referer 오타지만 안고침 => 고치는 순간 웹이 깨짐 
  - charset 은 잘못지은 이름이지만 안고침 => 인코딩이란 개념도 없었고 , 게다가 이렇게 고쳐버리면 상호운용성이 깨짐
  - Http 상태코드 416 포기 (Im a teapot) => 만우절때만든 416상태 코드를 http 상태코드로 구현을 해버림 , 잘못 만들어진 존재도 상호운용성을 인정해주어야 하기때문.
  - HTTP/0.9 를 아직도 지원한다 (크롬, 파이어폭스) => 지원을 종료할시 , 웹이 깨지는 (상호 운용성이) 깨짐
  
  
  
