* Nextjs는 모든 리액트 프로젝트에서 아주 흔히 계속해서 일어나는 문제점을 해결하기 위한 솔루션을 제공
* nextjs: 프로덕션용 리액트 프레임워크, 풀스택 프레임워크
* 리액트: 사용자 인터페이스 구축을 위한 자바스크립트 라이브러리 => 서드파티 라이브러리
* nextjs는 리액트 상에 구축된 프레임워크
* 프레임워크와 라이브러리의 차이점은 프레임워크 규모가 더욱 크다는, 코드륵 어떻게 작성해야 하는지, 어떻게 파일을 구조화 해야하는지에 대한 거 명확한 규칙과 가이드라인이 있음
* nextjs는 리액트를 강화시키고 대규모 앱 구축을 쉽게해준다
* 가장중요한 기능은 서버 측 렌더링 지원!
* 리액트는 클라이언트 자바스크립트 라이브러리이기 때문에 렌더링이 전부 사용자의 브라우저측에서 렌더링 됨
* 리액트만 사용하면 화면이 깜박거리는 로딩을 보는데 클라이언트 측에서 자바스크립트 코드가 실행된 뒤에 데이터 페칭이 시작되기 때문 => next를 사용하는 깜빡임 현상을 겪지 않아서 로딩경험 개선
* nextjs 를 사용하면 컴포넌트를 서버측에서 미리 렌더링해주기때문에 seo에 적합
* next를 사용하면 클라이언트측 및 서버측의 코드가 융합!
* 파일기반 라우팅: 리액트에는 라우터가 아예없다 리액트는 url을 확인해서 브라우저가 요청을 서버로 보내는 기본동작을 방지하고 대신에 react를 통해 페이지 상에 다른 콘텐츠를 렌더링 리액트 라우터는 별도의 코드를 따로작성해야한다. 그리고 개별 폴더에 페이지로서 작동하는 컴포넌트를 저장하는데 이 컴포넌트가 코드내에서 라우트 설정을 모방한다고 볼수있음 -> 페이지와 코드로 설정된 세개의 페이지가 있다면 페이지 컴포넌트 폴더에 페이지 컴포넌트가 3개 있는것
* next를 사용하면 코드내 라우트 정의를 사용할 필요가 없음, 파일과 폴더에 페이지와 라우트를 정의
* next를 사용하면 개발자들이 리액트 프로젝트에 백엔드 코드ㅡㄹ 추가하는 작업도 수월하게 가능
* next를 사용하면 nodejs 코드를 통해 아주 쉽게 백엔드 api를 리액트 프로젝트에 추가 가능 -> 독립적인 api 프로젝트를 구축할 필요 없이 하나의 프로젝트로 작업가능
* next는 저장하면 페이지를 새로고침하고 업데이트해준다
* 인증을 추가하는 부분에서 리액트 앱보다 더 간편
* next는 코드기반 라우팅이 아닌 파일기반 라우팅
* index.js 를 제외하고 다른 js파일을 통해서 요청의 파일내에 반환된 컴포넌트를 렌더링 하는것으로 추론
*  페이지 만드는법
   *  pages 밑에 .js
   *  pages 밑에 폴더하나만들고 아안에 index.js 만들기 ex) pages -> about폴더 -> index.js => /about 치면 index.js가 나옴
   * /about/list 로 가는법: about 폴더안에 list.js 만들면댐
 
 * 동적 라우팅 하는법: [projectIid].js
 * 동적라우팅은 언제사용하냐
   * 여러종류의 데이터를 불러와야하는 페이지를 생성할때 ex) 온라인 스토어 상품 or 블로그 게시글
   * 프로젝트 여러개를 포트폴리오 페이지에 불러올때
* 사용자가 url에 입력한 구체적인 값에 엑세스 하는법: next/router 라이브러리에 있음 -> useRouter()
* useRouter: 우리에게 유용한 데이터 조각과 메서드 여러개 제공

* 동적 라우팅 다른방법
  
```
pages(폴더)
ㅣ
ㅣ--clients(폴더)
        ㅣ
        ㅣ-[id](폴더)
            ㅣ[asd].js: 동적폴더에 중첩된 동적폴더나 동적 파일을 추가가능
            ㅣindex.js

//결과값이 3000/clients/max/project1
//로그 찍어보면 id: "max", asd: "project1"
```

* [...asd].js 사용하면 useRouter 찍을때 배열나옴 ex)20/2022 -> [20, 2022]
* Link 컴포넌트 기능
  * 링크에 마우스를 갖다대자마자 이동하려는 페이지로자동으로 데이터를 미리 페칭
  * replace를 설정하면 새로운 페이지를 또띄우지 않고 현재 페이지를 새 페이지로 변경 -> 뒤로가기 불가
```
// next에서 원하는 특수객체
client.map((client) => {
    <li key = {client.id}>
        <Linkj href = {{
            pathname: '/clients/[id]',
            query: {id: client.id} 
        }}{client.name}</Link>
})

```
* 명령형: 어떻게
* 선언형: 무엇을

* 404.js 만들면 404 뜰때 이페이지로 들어감

* ## index.js 파일은 항상 지정될 폴더의 루트 페이지
* next를 사용하면 pages 폴더를 구성하는 폴더 구조를 통해 애플리케이션에 지원하는 모든 경로를 처리할 수 있다.
* next에 public 폴더: 반드시 있어야함 next에서 특수한 역할을 한다. 이 폴더에 저장되어 있는 이미지나 글꼴 같은 데이터들은 next에서 정적인 데이터로 적용하기 때문에 css나 html 코드에서 참조  할 수 있다.
* public 폴더밖의 파일과 폴더는 next에서 접근하지 못한다 => public 폴더 밖에있는 폴더나 파일에 접근해야 하면 해당 파일을 public로 복사하거나 next 프레임워크의 서버측 코드에서 파일을 읽어와서 처리해야한다
* pages폴더에는 각 페이지에 쓰이는 컴포넌트만 있어야한다 -> 이 폴더에 들어가 있는 파일을 새로운 라우트를 자동으로 생성하기 때문

* Link안에는 앵커태그가 있는데 앵커태그는 링크를 클릭했을때 일어나는 동작을 제어한다
* next는 _app 컴포넌트를 이용해서 페이지 콘텐츠를 전달하고 페이지를 이동할 때 컨텐츠를 표시해준다
* Fragment 컴포넌트: 
  * 불필요한 DOM 노드 생성방지
  * 부요요소없이 여러요소반환
  * div를 사용할수도 있지만 그러면 내생각과는 다르게 css가 들어갈 수 있음
  
* next는 서버사이드에서 페이지를 사전 렌더링 해주는데 이점이 아주중요
* 리액트에서는 컴포넌트가 로딩된후에 데이터를 패칭 -> 즉 클라이언트 사이드에서 데이터를 페칭하고 화면에 렌더링 된후에 서버로 요청을 보낼 수 있다. => 사용자가 처음 페이지를 방문했을 때 서버가 클라이언트에게 재전송하는 페이지는 그 데이터를 포함하고 있지 않다는점이 문제
* next는 사전렌더링 된 페이지를 전송하고 javascript 코드를 재전송  -> 재전송된 자바스크립트 코드는 나중에 사전 렌더링 된 페이지를 대체하고 이에 react가 알맞은 작업을 수행
* next는 라우트에 요청이 전송된 경우 즉 사용자가 해당 페이지를 방문하면 바로 사전 렌더링된 페이지를 반환, 이게 react와의 차이점 react는 빈 html 파일과 모든 javascript 코드가 표시된다
* 즉 사전에 html 페이지를 완성해놓고 완전히 채워진 html 파일을 클라이언트 즉 페이지의 방문자에게 전송 -> seo 관점에서 아주중요
* next는 사전렝더링된 페이지를 재전송하는데 그치지 않고 포함된 자바스크립트 코드를 모두 재전송 -> 재전송된 자바스크립트 코드는 나중에 사전 렌더링된 페이지를 대체하고 이에 react가 알맞는 작업을 수행 -> 이때 처음에 재전송한 사전 렝더링된 페이지에는 주요 콘텐츠가 모두 포함 -> 검색엔진 크롤러도 전체 페이지에  이미 포함된 모든 콘텐츠를 살핀다
* 이런 재전송을 해당페이지에 대해 수화(hydrate: 수분유지) 라고한다
* 사전 렌더링은 오직 최초 로딩할때만 영향을 미친다. -> 첫번째 렌더링이 끝나고 나면 다시 표준 싱글페이지 애플리케이션으로 돌아간다 -> 이때부터 react가 프론트엔드에서 모든처리를 수행
* 페이지가 바뀔때 사전렝더링 하지않고 리액트를 통해 클라이언트 사이드에서 생성 -> 사전렌더링 되는건 최초 접속하는 첫번째 페이지뿐
* next에는 두가지 사전렌더링 양식이 있음
  * 정적생성: 빌드되는 동안 모든 페이지가 사전 생성되는것 -> 프로덕션용 애플리케이션을 구축하면 배포전에 모든페이지가 준비된다는것 -> 일반적으로 권장되는방법 
  * SSR: 배포후 요청이 서버까지 오는 바로 그때 모든페이지가 생성
* 정적생성: 배포되고 나면 구축된 페이지는 서버나 앱을 실행시키는 CDN을 통해 캐시로 저장
* 정적생성을 하려면 React 컴포넌트가 아닌 pages 폴더의 component 파일 내부에 특수한 비동기함수인 getStaticProps를 가져와야한다
* getStaticProps 함수는 보통 서버사이드에서만 실행되는 모든 코드도 실행 가능 -> 특정 클라이언트 사이드 api에 엑세스가 없거나 윈도우 객체에 대한 엑세스가 없는 일반적으로는 서버사이드에서만 가능한 모든 코드도 실행가능
* getStaticProps 내에 작성한 코드는 클라이언트에게 재전송되는 코드로 포함하지 않는다 -> 해당 함수내에 포함하는 코드는 클라이언트는 볼수 없다 -> 노출하고 싶지 않는 코드를 여기에 작성하면 된다.
* next는 동적 데이터가 없는 모든페이지를 사전 렌더링한다
```
//두번째 실행
function HomePage(props) {
  return (
    <ul>
      <li>props.products[0].id</li>
      <li>b</li>
      <li>c</li>
    </ul>
  );
}

//첫번째 실행
export async function getStaticProps(context) { //컴포넌트에 대한 프로퍼티를 준비 즉 이 props 객체를 준비

if(!data) {
  return {
    redirect: {
      destination: '/no-data'
    }
  };
}

if (data.products.length === 0) {
  return { notFound: true};
}
  return {
    props: {
        products: [{id: 'p1', title: 'asd'}]
      },
      revalidate: 60
    };
  }

export default HomePage;
```
* next는 getStaticProps 에 쓰이는 임포트를 확인하고 클라이언트 사이드 코드 번들에서는 이 이폼트를 제거
* 프로덕션 빌드하려면 num run build ("build": "next build") 하고 npm start("start": "next start")
* ISR(증분 정적 생성): 페이지를 빌드할때 정적으로 한번만 생성하는것이 아니라 배포후에도 재배포 없이 계속 업데이트되는것, 초 설정해놓으면 ex 60초 설정해서 60초가 지나지 않았으면 기존 페이지가 방문자에게 제공된다는 뜻
* ISR 설정 하려면 getStaticProps에 return 두번째 인자에 revalidate에 설정해주면된다 -> 새로고침했을때 60초가 안지났으면 원래 데이터 보여준다
* getStaticProps(context) context 매개변수: next로 실행될때 페이지에 대한 추가 정보를 가진 매개변수
* notFound: true로 해놓으면 404 오류 페이지를 렌더링, 이 키를 사용하는 이유는 데이터를 페치하는 이 코드가 어떤 이유로든 페칭에 실패하면 그 작업을 할 수있는데 ex 작품이 없을 땐 getStatucProps() 안에 객체를 반환 하는데 notFound를 true로 설정해서 404 페이지를 보여주고 페치된 데이터가  한개라도 있으면 일반 페이지를 반환
* redirect: 사용자를 리디렉션 가능 -> 페이지 콘텐츠나 컴포넌트 콘텐츠를 렌더링하지 않고 다른페이지, 즉 다른 라우트로 리디렉션 하는것 -> 역시 데이터 페칭에 실패할 경우 필요한 설정
* next는 기본적으로 페이지를 사전생성하는데 동적페이지는 그렇지 않음 -> next가 사전에 동적페이지를 위해서 얼마나 많은 페이지르 미리 생성해야 하는지 알지못하기때문
* 동적 페이지에서 getStaticProps를 사용하면 오류를만날 확률이 높음
* 동적페이지에는 getStaticPaths() 를 사용하는데 getStaticProps처럼 page 컴포넌트파일에만 추가할수 있는 함수 next가 임지하도록 함수를 export 해야함
* getStaticPaths: 동적 페이지의 어떤 인스턴스를 생성할지 next에 알리는것 -> getStaticPaths 를사용한 페이지에 들어가면 다른페이지로 가는 데이터를을 사전에 페칭해준다. 미리페칭된 데이터를 우리대신 로딩하고 읽는데 그러면 우리가 페이지로 이동한후 데이터를 페칭할 필요가 없다. -> ex) product1 페이지로 이동하기도 전에 product1 페이지를 보여주기위한 데이터는 이미 훨신 존재하기 때문에 훨씬 빠르다
```
export async function getStaticPaths() {
  return {
    apths: [
      { params: {pid: 'p1'}},
      <!-- { params: {pid: 'p2'}}, -->
      { params: {pid: 'p3'}},
    ],
    fallback: false
  } //동적페이지가 세번 사전생성되어야 하며 세가지 값을 가진다는 사실을 next에 알린다
}
```
* fallback: 상품이 수백만개 인 웹사이트는 사전생성을 하기가 매우어려움 true로 설정하면 사용자에게 자주 보여지는 화면만 사전 생성 가능
* fallback를 사용하지 않은 페이지 p2 페이지를 사전렌더링하지 않으면 링크클릭해서 들어갈 수는 있지만 url에 직접 쳐서들어가면 에러가남
* 그러면 props 에서 !loadedProduct === false 면 리턴을 해주면된다
* fallback: 'blocking': 컴포넌트에서 폴백 확인할 필요가 없음 -> 페이지가 서비스를 제공하기전에 서버에 완전히 사전 생성되도록 next가 기다린다 -> 페이지 방문자가 응답받는 시간은 길어지지만 수신된 응답은 종료된다 -> 다시 새로고침해도 시간이 걸릴 뿐 잘 작동한다
* blocking을 쓰는 경우는 방문자에게 불완전한 페이지를 보고싶지 않은경우 사용
* fallback을 true을 설정하면 파일에서 찾을 수 없는 id에 대해서도 페이지를 렌더링 할 수 있다 -> props.loadedProduce 사용 후 데이터를 로드해도 데이터가 안들어오면 또 에러가남 -> getStaticProps 에  return { notFound: true}; 사용하면된다
* getStaticProps, getStaticPaths 는 정적생성
* 정적생성만으로 충분하지 않을때가 있는데 이때 실제로 서버사이드렌더링이 필요
* getServiceSideProps 서버사이드 렌더링에 사용하는 함수, 유입되는 모든요청에 대해서만 재실행 getStaticProps와 충돌하기떄문에 둘중 하나만 사용해야함 둘다 컴포넌트의 프로퍼티를 가져오는함수로 next가 해당 컴포넌트를 렌더링 할 수 있지만 실행되는 시점에는 차이가 있음
* getServiceSideProps는 getStaticProps와 같은 포맷 으로 설정 -> 객체반환하는부분이 똑같음
* getServiceSideProps는 모든 요청에  대해서 페이지를 즉시 서버에 사전렌더링한다
``
function UserProfilePAge(props) {
  return <h1>props.username</h1>
}

export default UserProfilePage;

export async function getServerSideProps(context) { // 배포된 서버와 개발서버에서만 실행된다는점, 사전에 생성된 정적함수는 아님
  return {
    props: {
      username: 'Max'
    }
  }
}
```
* SWR훅: next팀에서 개발한 리애그 훅, next가 아닌 프로젝트에서도 사용가능, http요청, 캐싱 및 자동 유효성 재검사, 에러시 요청재시도( 리액트쿼리랑 같은듯?)
* swr보다는 서버사이드 렌더링을 사용하면 리액트쿼리를 사용하는게 훨씬 좋을듯
* getStatic 이나 getservervice 에서는 리액트훅 사용불가 -> 리액트 컴포넌트가 아니기 때문
* fetch는 사용가능
* npm run build -> npm start -> 프로덕션 준비 번들이 포함된 프로덕션 서버 시작
* 파일기반의 라우팅은 이미 훌륭한 기능이지만 사전 페칭과 사전 렌더링이야말로 next를 대단히 강력하게 만드는 기능 -> 페이지를 쉽게 검색엔진 최적화를 할수있고 사용자에게 처음부터 데이터를 표시할수있고 react와 관련된 모든것을 적용가능하다
* 