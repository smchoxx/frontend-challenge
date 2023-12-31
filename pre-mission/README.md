## CSR

### 정의

웹 애플리케이션의 초기 렌더링을 클라이언트 측에서 처리하는 방식을 말합니다.
CSR은 사용자의 요청에 따라 HTML, CSS, JS와 같은 필요한 리소스를 다운로드한 후, 클라이언트에서 동적으로 컨텐츠를 생성하여 화면에 표시합니다.

### 장단점

- **장점**

  1. 사용자 경험 향상  
     CSR을 통해 웹 페이지가 동적으로 빠르게 업데이트되고 사용자 상호작용에 잘 반응 합니다.

  2. 서버 부하 감소  
     클라이언트가 페이지 랜더링 작업을 처리하므로, 서버의 부하가 상대적으로 작아집니다.

  3. 프론트엔드 집중 개발  
     개발자들은 프론트엔드와 백엔드를 명확하게 분리하고, 클라이언트에 대한 개발에 더 집중 할 수 있습니다.

- **단점**

  1. 초기 로딩 속도 지연  
     사용자가 처음 페이지를 방문할 때, 모든 자바스크립트 파일과 리소스를 다운로드해야 하므로 초기 로딩 속도가 느릴 수 있습니다.

  2. SEO 문제  
     검색 엔진의 크롤러가 자바스크립트를 완전히 해석하지 못할 수 있어서 SEO 최적화가 어려울 수 있습니다.

  3. 클라이언트 성능에 의존  
     CSR은 브라우저 성능에 크게 영향을 받습니다. 성능이 좋지 않은 기기에서는 웹 사이트 로딩 및 반응에 민감한 부분이 있을 수 있습니다.

## SSR(Server Side Rendering)

### 정의

웹 애플리케이션의 초기 렌더링을 서버 측에서 처리하여 완성된 HTML을 클라이언트(브라우저)로 전송하는 방식을 말합니다. SSR은 클라이언트가 HTML을 수신할 때 이미 콘텐츠가 존재하기 때문에 초기 로딩 속도가 개선되고 검색 엔진 최적화 (SEO)에 유리한 특징이 있습니다.

### 장단점

- **장점**  
  아래 내용과 동일함.

- **단점**

  1. 서버 리소스 사용 증가  
     SSR은 서버 측에서 렌더링을 처리하므로 서버 리소스가 더 많이 사용됩니다. 많은 요청을 처리하거나 대규모 애플리케이션의 경우 서버의 성능에 영향을 줄 수 있습니다.
  2. 초기 구성 및 개발 복잡성  
     SSR을 구현하려면 서버 사이드 렌더링을 지원하는 프레임워크나 라이브러리를 사용해야 하며, 초기 구성 및 개발 프로세스가 복잡해질 수 있습니다. SSR을 구현하기 위한 추가적인 설정과 배포 과정을 고려해야 합니다.
  3. 네트워크 부하  
     SSR은 초기 로딩 시 서버에서 필요한 리소스를 다운로드해야 하므로 네트워크 부하가 증가할 수 있습니다. 특히 초기 페이지에 필요한 데이터가 많은 경우 추가적인 요청과 데이터 전송이 필요합니다.

## SPA로 구성된 웹 앱에서 SSR이 필요한 이유

1. 검색 엔진 최적화(SEO)  
   검색 엔진 최적화는 모든 웹사이트에게 중요한 요소입니다. 검색 엔진은 보통 서버에서 렌더링된 콘텐츠를 클라이언트 측에서 렌더링된 콘텐츠보다 더 쉽게 크롤링하고 이해할 수 있습니다. 따라서 SPA는 초기에 검색 엔진에 콘텐츠를 제대로 노출시키기 어려울 수 있습니다. Google과 같은 검색 엔진은 자바스크립트를 실행하여 콘텐츠를 인덱싱하지만, 이 과정에서 복잡성이 증가하고 잠재적인 문제가 발생할 수 있습니다.  
   서버에서 렌더링된 페이지를 사용하면, 검색 엔진 크롤러가 웹 페이지의 콘텐츠와 메타 태그를 쉽게 읽을 수 있게 해서, 웹 사이트의 검색 엔진 순위를 향상시킬 수 있습니다.

2. 초기 로딩 속도 개선  
   SPA는 초기에 필요한 자바스크립트 파일을 다운로드하고 실행해야 하므로 초기 로딩 속도가 느릴 수 있습니다. 사용자가 페이지와 상호 작용을 시작하기 전에 전체 애플리케이션이 로딩되어야 하는데, 이로 인해 지연이 발생할 수 있습니다. SSR을 사용하면, 사용자는 서버가 클라이언트에게 완전히 렌더링된 페이지를 전송하기 때문에, 나머지 애플리케이션을 백그라운드에서 로딩하는 동안 페이지를 보고 상호작용을 시작할 수 있습니다. 이는 인터넷이 느린 사용자에게 특히 유익할 수 있습니다.
3. 소셜 미리보기  
   소셜 미디어 플랫폼에서 링크를 공유할 때 해당 페이지의 제목, 설명, 이미지 등을 미리보기로 표시하기 위해 서버에서 제공하는 메타 데이터가 필요합니다. SSR은 서버 측에서 적절한 메타 데이터를 포함한 페이지를 생성하여 소셜 미리보기를 개선할 수 있습니다.
4. 성능 개선을 위한 초기 데이터 로딩  
   일부 SPA에서는 초기에 필요한 데이터를 서버 측에서 렌더링할 때 함께 전달하는 것이 유리한 경우가 있습니다. SSR은 초기 데이터를 서버에서 가져와서 페이지 렌더링 시에 함께 전달할 수 있으므로, 초기 데이터 로딩을 효율적으로 처리하여 사용자 경험을 개선할 수 있습니다.

SSR은 SPA에서 SEO, 초기 로딩 속도, 소셜 미리보기 등의 문제를 해결하고 성능을 개선할 수 있는 방법 중 하나입니다. 그러나 SSR은 서버 측에서 렌더링을 처리하므로 서버 리소스가 더 많이 사용되고 초기 구성과 개발 프로세스가 복잡해질 수 있다는 단점도 있습니다. 프로젝트의 요구 사항과 목표에 따라 SSR을 사용할지 여부를 결정하는 것이 중요합니다.

## Next.js 프로젝트에서 `yarn start(or npm run start)` 스크립트를 실행했을 때 실행되는 코드를 Next.js Github 레포지토리에서 찾은 뒤, 해당 파일에 대한 간단한 설명을 첨부해주세요.

```typescript
const validArgs: arg.Spec = {
  // Types
  '--help': Boolean,
  '--port': Number,
  '--hostname': String,
  '--keepAliveTimeout': Number,

  // Aliases
  '-h': '--help',
  '-p': '--port',
  '-H': '--hostname',
};
let args: arg.Result<arg.Spec>;
try {
  args = arg(validArgs, { argv });
} catch (error) {
  if (isError(error) && error.code === 'ARG_UNKNOWN_OPTION') {
    return printAndExit(error.message, 1);
  }
  throw error;
}
```

next start의 옵션으로 올 수 있는 값을 명시합니다.
명시한 옵션 이외에 값이 들어오면 에러를 프린트하고 실행을 멈춥니다.

```typescript
if (args['--help']) {
  console.log(`
   Description
      Starts the application in production mode.
      The application should be compiled with \`next build\` first.

   Usage
      $ next start <dir> -p <port>

   <dir> represents the directory of the Next.js application.
   If no directory is provided, the current directory will be used.

   Options
      --port, -p          A port number on which to start the application
      --hostname, -H      Hostname on which to start the application (default: 0.0.0.0)
      --keepAliveTimeout  Max milliseconds to wait before closing inactive connections
      --help, -h          Displays this message
   `);
  process.exit(0);
}
```

옵션으로 `--help`가 들어오면 console.log로 설명을 프린트하고 실행을 종료합니다.

```typescript
const dir = getProjectDir(args._[0]);
const host = args['--hostname'];
const port = getPort(args);

const keepAliveTimeoutArg: number | undefined = args['--keepAliveTimeout'];
if (
  typeof keepAliveTimeoutArg !== 'undefined' &&
  (Number.isNaN(keepAliveTimeoutArg) ||
    !Number.isFinite(keepAliveTimeoutArg) ||
    keepAliveTimeoutArg < 0)
) {
  printAndExit(
    `Invalid --keepAliveTimeout, expected a non negative number but received "${keepAliveTimeoutArg}"`,
    1,
  );
}

const keepAliveTimeout = keepAliveTimeoutArg
  ? Math.ceil(keepAliveTimeoutArg)
  : undefined;
```

서버 실행에 필요한 dir, host, port 등을 입력받은 값 또는 기본 값으로 선언, 초기화한다.
이때 --keepAliveTimeout의 값이 유효하지 않을 경우에는 에러를 프린트하고 실행을 종료합니다.

```typescript
await startServer({
  dir,
  isDev: false,
  hostname: host,
  port,
  keepAliveTimeout,
  useWorkers: !!config.experimental.appDir,
});
```

startServer 함수를 통해 서버를 실행한다.
