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