# @karpo/tsconfig

**Karpo Deepdive** 프로젝트의 모든 패키지와 앱에서 공통으로 사용하는 TypeScript 설정을 관리하는 패키지입니다.

이 패키지는 프레임워크(React, Next.js, NestJS, Express 등)에 종속되지 않는 범용적인 설정을 제공하며, 일관된 코딩 표준을 유지하는 것을 목표로 합니다.

## 파일 설명

### `base.json`
- **목적**: 모든 환경에서 사용할 수 있는 가장 기초적인 TypeScript 설정입니다.
- **의도**:
  - `target`: `es2022`로 설정하여 최신 문법을 지원하면서도 안정성을 확보합니다.
  - `moduleResolution`: `bundler`로 설정하여 최신 번들러 환경(Vite, Webpack 등)에 최적화합니다.
  - `strict`: `true`로 설정하여 타입 안정성을 최우선으로 합니다.
  - 프레임워크 종속적인 설정(예: `jsx` 등)은 최대한 배제하거나 상속받는 곳에서 오버라이딩하도록 설계했습니다.

## Root Configuration

### Root `tsconfig.json`
- **위치**: 프로젝트 최상위 루트 (`/tsconfig.json`)
- **목적**: 모노레포 루트에서 IDE(VS Code 등)가 전체 프로젝트 구조를 인식하고, 루트 레벨의 파일(설정 파일 등)을 린트할 수 있도록 합니다.
- **의도**:
  - IDE가 `packages/**`나 `apps/**` 내부의 파일뿐만 아니라, 루트에 있는 `turbo.json`, `package.json` 등의 파일도 올바르게 인식하게 돕습니다.
  - 일반적으로 빈 파일(`files: []`)에 `references`만 두기도 하지만, 여기서는 루트 파일들의 검사를 위해 기본 설정을 포함하고 있습니다.
