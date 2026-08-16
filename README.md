# Ruby Silver Drill

Ruby Association Certified Ruby Programmer **Silver v3** 대비 200문항 드릴.
문제는 실제 시험과 같은 일본어, 해설은 한국어. 아이폰에서 바로 쓰도록 만든 단일 파일 웹앱.

## GitHub Pages 배포 (5분)

1. GitHub에서 새 저장소 생성 — 이름 예: `ruby-silver`, **Public**
2. `index.html`, `sw.js`, `manifest.webmanifest` 세 파일을 업로드 후 커밋
3. 저장소 → **Settings → Pages**
4. Source = `Deploy from a branch`, Branch = `main` / `/(root)` → **Save**
5. 1~2분 뒤 `https://<아이디>.github.io/ruby-silver/` 로 접속

## 아이폰 세팅

Safari로 위 주소 접속 → 공유 버튼 → **홈 화면에 추가**.
주소창 없는 앱처럼 뜨고, 한 번 열어두면 오프라인(지하철 등)에서도 동작합니다.

## 사용법

- 보기를 체크하면 **해설 보기** 버튼이 열립니다
- 해설을 누르는 순간 기록이 남습니다 (되돌릴 수 없음 — 실전처럼 신중하게)
- **기록** 탭: 문제별 시도 횟수 / 일시 / 그때 체크한 보기 / 정오
- **통계** 탭: 분야별 정답률. 합격선 75%
- 필터: `안 푼 것` → 진도용, `오답` → 복습용

기록은 브라우저 localStorage에 저장됩니다. 기기·브라우저마다 별개이고,
Safari 데이터를 지우면 함께 사라지므로 가끔 **기록 내보내기**(CSV)를 눌러 두세요.

## 문항 추가

`index.html` 아래쪽 `window.QUESTIONS = [...]` 배열에 같은 형식으로 추가합니다.

```js
{"i":201,"c":"String","q":"問題文","code":"p 1","o":["A","B"],"a":[0],"e":"해설 HTML"}
```

`i`=번호(중복 금지), `c`=분야, `code`=없으면 `null`, `a`=정답 인덱스 배열(0부터).
`a`에 2개 이상 넣으면 복수정답 문제가 됩니다.

## 출제 범위 (200문항)

| 분야 | 문항 |
|---|---|
| オブジェクト指向 (클래스·모듈·Mixin) | 34 |
| String | 23 |
| Array | 22 |
| 例外処理 | 12 |
| ブロック・Proc・lambda | 12 |
| Hash | 12 |
| Kernel・組み込み関数 | 11 |
| 文法 (메서드·변수·연산자·반복·조건·리터럴) | 43 |
| 数値・Range / Enumerable | 17 |
| 正規表現 / File・IO / Time | 14 |

모든 문항의 정답은 Ruby 3.2로 실제 실행해 검증했습니다.
