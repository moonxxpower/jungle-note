# SSR, CSR

🔎 *참고 자료* <br>
    - [[10분 테코톡] 🎨 신세한탄의 CSR&SSR](https://youtu.be/YuqB8D6eCKE?si=TGWej1kYz79tIDu1) <br>
    - [서버사이드 렌더링 (개발자라면 상식으로 알고 있어야 하는 개념 정리 ⭐️)](https://youtu.be/iZ9csAfU5Os?si=xrh27OBIifoc62DH)
    

1️⃣ **SPA, MPA의 개념**

- **SPA** (Single Page Application)

하나의 페이지로 구성된 웹 어플리케이션

단일 페이지로 구성되어 있어 갱신된 부분에 대해서만 데이터를 요청하여 랜더링한다.

- **MPA** (Multi Page Application)

탭을 이용할 때마다 서버로부터 새로운 HTML을 새로 받아와서 페이지 전체를 새로 랜더링하는 전통적인 웹 페이지 구성

2️⃣ **SSR, CSR의 개념**

- **SSR** (Server Side Rendering)

새로운 요청이 있을 때마다 서버에서 이미 랜더링된 정적 리소스를 받아온다.

→ 사용자가 웹 페이지에 접속하면 브라우저가 해당 URL을 서버에 요청하고, 서버는 이 URL을 기준으로 어떤 페이지를 랜더링할지 결정한다. (각 페이지 URL마다 보여줄 내용이 미리 결정되어 있다.)

보통 MPA에서 랜더링 방식으로 채택한다.

- **CSR** (Client Side Rendering)

웹 어플리케이션에 필요한 정적 리소스를 초반 한 번에 모두 다운로드하고 그 이후 새로운 페이지 요청이 있을 때 페이지 갱신에 필요한 데이터만 전달 받아서 클라이언트에서 페이지를 갱신한다.

→ 사용자가 여러 페이지를 이동하더라도 최초의 서버에서 전송받은 하나의 HTML을 이용해, 컴포넌트만 교체해서 랜더링한다.

보통 SPA에서 랜더링 방식으로 채택한다.

(*) **SSG** (Static Site Generation)

클라이언트에서 필요한 페이지들을 사전에 미리 준비해뒀다가 요청을 받으면 이미 완성된 파일을 단순히 반환한다. 

3️⃣ **SSR, CSR 비교**

![SSR, CSR](https://github.com/moonxxpower/jungle-note/assets/118599217/a94d6eb5-d120-4194-a330-7a95b4443d02)


(*) **SEO** (Search Engine Optimization)

검색 엔진들은 서버에 등록된 웹 사이트를 돌아다니며 웹 사이트의 HTML 문서를 분석하여 우리가 검색할 때 웹 사이트를 빠르게 검색할 수 있게 도와준다.

(*) 

![SSR](https://github.com/moonxxpower/jungle-note/assets/118599217/57e0e916-2d18-43c9-b232-12234e34db0f)

![CSR](https://github.com/moonxxpower/jungle-note/assets/118599217/5f4ed74a-1009-4d56-be35-179e3cfd5015)

4️⃣ **사용 용도**

> **서비스의 특성**에 맞는 랜더링 방식을 채택해야 한다!
> 
- 만약 사용자와의 상호 작용이 많고, 대부분 페이지가 고객의 개인 정보 데이터를 기준으로 구성되는 서비스라면, 검색 엔진에 노출되는 것보다 오히려 고객의 데이터를 보호하는 것이 더 중요할 수 있기 때문에 CSR이 적합하다.
- 만약 회사 홈페이지이기 때문에 상위 노출되어야 하고, 누구에게나 동일한 내용을 노출하고 있으며, 페이지의 데이터가 자주 바뀐다면, SSR이 적합하다.
- 만약 내용 업데이트가 거의 없는 경우, SSG가 적합하다.
- 만약 사용자에 따라 페이지 내용도 달라지고, 빠른 인터렉션도 중요하고, 검색 엔진 최적화도 포기할 수 없다면, CSR과 SSR을 동시에 사용하는 Universal Rendering을 고려해야 한다. Universal Rendering의 경우, 초기 구동 속도가 빠르다는 SSR의 장점과 페이지를 이동할 때 깜빡임이 없다는 CSR의 장점을 적절하게 사용한다.