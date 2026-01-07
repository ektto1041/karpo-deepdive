# Biome Configuration Guide

이 문서는 프로젝트 루트에 위치한 `biome.json` 설정 파일의 각 항목에 대한 의도와 설명을 담고 있습니다.

## 설정 파일 위치
`vcs` (Version Control System) 설정이 포함되어 있으므로, 데이터베이스 역할을 하는 `.git` 폴더가 있는 프로젝트 루트에 위치하는 것이 가장 적합합니다. 이에 따라 `docs/biome.md`에 문서를 작성하여 관리하기를 권장합니다.

## Configuration Details

### 1. VCS (Version Control System)
```json
"vcs": {
  "enabled": true,
  "clientKind": "git",
  "useIgnoreFile": true
}
```
- **의도**: Biome이 `.gitignore` 파일을 존중하도록 설정합니다.
- **설명**:
  - `enabled`: VCS 통합을 활성화합니다.
  - `clientKind`: Git을 사용함을 명시합니다.
  - `useIgnoreFile`: `.gitignore`에 정의된 파일들을 Biome 실행 대상에서 자동으로 제외합니다 (중복 설정 방지).

### 2. Files
```json
"files": {
  "ignoreUnknown": false,
  "ignore": ["node_modules", ".next", "dist", ".turbo"]
}
```
- **의도**: 불필요한 시스템 디렉토리나 빌드 산출물을 검사 대상에서 제외합니다.
- **설명**:
  - `ignore`: `.gitignore` 외에도 Biome이 명시적으로 무시해야 할 폴더들을 지정합니다.

### 3. Formatter
```json
"formatter": {
  "enabled": true,
  "indentStyle": "space",
  "indentWidth": 2
}
```
- **의도**: 일관된 코드 스타일을 강제합니다.
- **설명**:
  - `indentStyle`: 탭 대신 **스페이스**를 사용합니다 (다양한 환경에서의 가독성 확보).
  - `indentWidth`: 들여쓰기 크기를 **2**로 설정합니다 (가장 일반적인 JS/TS 컨벤션).

### 4. Linter
```json
"linter": {
  "enabled": true,
  "rules": {
    "recommended": true
  }
}
```
- **의도**: 코드 품질을 유지하고 잠재적인 버그를 사전에 방지합니다.
- **설명**:
  - `recommended`: Biome팀이 권장하는 모범 사례 규칙 세트를 활성화합니다. 필요한 경우 추후에 특정 규칙만 override 할 수 있습니다.

### 5. JavaScript / TypeScript Specifics
```json
"javascript": {
  "formatter": {
    "quoteStyle": "double"
  }
}
```
- **의도**: 문자열 표기 방식을 통일합니다.
- **설명**:
  - `quoteStyle`: **큰따옴표(")**를 기본으로 사용합니다. 이는 JSON 포맷과의 일관성을 유지하거나, 많은 모던 프론트엔드 프로젝트의 관례를 따릅니다.
