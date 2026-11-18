# Todo Tutorial

[Claude Code Playbook](https://docs.claude-hunt.com) 강의에서 작은 할 일 앱을 직접 만들어 보며 Claude Code 쓰는 법을 배우는 연습용 저장소입니다.

## 관련 링크

- 강의 본문: https://docs.claude-hunt.com
- 수강생 결과물 공유: https://claude-hunt.com

## 기술 스택

- Next.js 16 (App Router, Turbopack)
- React 19
- Tailwind CSS v4
- shadcn/ui (radix-maia 스타일, taupe 베이스)
- TypeScript / ESLint / Prettier
- 패키지 매니저: bun 1.3.6

## 시작하기

### 1. 준비물

- [Git](https://git-scm.com)
- [Node.js](https://nodejs.org) 20.9 이상 (Next.js 16 요구 사항)
- [bun](https://bun.sh) 1.3 이상 (패키지 매니저 겸 스크립트 실행기)

설치되어 있는지 확인합니다.

```bash
git --version
node -v
bun -v
```

### 2. 내려받기와 설치

```bash
git clone https://github.com/dlwlsk0428/todo-tutorial.git
cd todo-tutorial
bun install
```

의존성은 `bun.lock` 기준으로 설치됩니다. 이 저장소는 bun을 쓰므로 `npm install`로 `package-lock.json`을 만들지 마세요.

### 3. 개발 서버 실행

```bash
bun run dev
```

[http://localhost:3000](http://localhost:3000) 에서 앱이 열립니다. 이미 3000번 포트를 쓰고 있다면 터미널에 표시되는 다른 주소를 확인하세요. 종료는 `Ctrl+C`입니다.

### 4. 잘 설치됐는지 확인

개발 서버를 끈 상태(또는 다른 터미널)에서 실행합니다.

```bash
bun run typecheck  # 타입 검사
bun run lint       # ESLint
bun run test       # 테스트 (Vitest)
```

> `bun test`가 아니라 `bun run test`입니다. `bun test`는 bun 자체 테스트 러너를 실행해 이 프로젝트의 테스트와 맞지 않습니다.

### 자주 쓰는 스크립트

```bash
bun run build       # 프로덕션 빌드
bun run start       # 빌드 결과 실행 (먼저 build 필요)
bun run start -p 3001  # 3000번 포트가 사용 중일 때 (start는 자동으로 다른 포트를 찾지 않음)
bun run lint        # ESLint
bun run typecheck   # tsc --noEmit
bun run test        # 테스트 한 번 실행
bun run test:watch  # 테스트 감시 모드
bun run format      # Prettier 포맷팅
```

## 레슨별 시작 브랜치

레슨마다 시작 시점의 코드를 `lesson/<레슨 이름>` 브랜치로 제공합니다. 레슨 본문이 안내하는 브랜치로 바꾼 뒤 따라가세요.

```shell
git checkout lesson/claude-md
```

## 컴포넌트 추가

shadcn/ui 컴포넌트는 다음과 같이 추가합니다.

```bash
bunx --bun shadcn@latest add button
```

`components/ui` 디렉토리에 컴포넌트가 추가됩니다.

## 컴포넌트 사용

```tsx
import { Button } from "@/components/ui/button";
```
