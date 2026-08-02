# 프로젝트 1 | 영어 단어 자동 분류

> 비교 도구: **Make · Zapier**  
> 작성일: 2026-08-02

## 목적

Google Form에 입력한 단어를 암기 점수에 따라 자동 분류하고, 같은 흐름을 두 도구로 비교했다.

## 워크플로우

```text
Google Form 제출
→ Google Sheets 새 행 감지(Trigger)
→ 점수 조건 분기
   ├─ 1~3점 → '복습 필요' 탭에 행 추가(Action 1)
   └─ 4~5점 → '암기 완료' 탭에 행 추가(Action 2)
```

## 요구사항 확인

| 요구사항 | 구현 |
|---|---|
| 도구 2개 | Make, Zapier |
| Trigger | Google Sheets 새 행 감지 |
| 조건 분기 | Make Router/Filter, Zapier Paths |
| Action 2개 | 분기별 Google Sheets 행 추가 |
| 모든 경로 실행 | 두 도구에서 1~3점·4~5점 실행 완료 |

## 구현 방식

| 구분 | Make | Zapier |
|---|---|---|
| Trigger | Watch New Rows | New Spreadsheet Row |
| 분기 | Router + Filter | Paths + Path conditions |
| Action | Add a Row | Create Spreadsheet Row |

## 실행 결과

| 도구 | 테스트 | 결과 |
|---|---|---|
| Make | retrieve · 2점 | 복습 필요 |
| Make | class · 5점 | 암기 완료 |
| Zapier | configure · 3점 | 복습 필요 |
| Zapier | automate · 4점 | 암기 완료 |

## 비교

| 항목 | Make | Zapier |
|---|---|---|
| 화면 | 자유 배치형 | 단계·경로형 |
| 초기 설정 | 모듈별 연결 설정 필요 | 단계별 안내가 쉬움 |
| 조건 분기 | Router와 Filter를 따로 설정 | Paths 안에서 조건 설정 |
| 데이터 매핑 | Bundle 값을 열에 연결 | Trigger 변수를 열에 연결 |
| 테스트 | Run once | Test run·Zap History |
| 실행 로그 | 모듈별 Bundle 확인 | 실행 경로가 색으로 표시됨 |
| 무료 범위 | 무료 플랜으로 구현 | Paths는 Pro 체험·유료 기능 |

## 장단점과 적합한 상황

| 도구 | 장점 | 단점 | 적합한 상황 |
|---|---|---|---|
| Make | 흐름이 한눈에 보이고 분기 구조가 명확함 | 모듈마다 연결·Drive 설정 필요 | 복잡한 흐름을 시각적으로 설계할 때 |
| Zapier | 단계별 설정과 실행 경로 확인이 쉬움 | 무료 플랜은 다단계·Paths 제한 | 빠르게 업무 자동화를 만들 때 |

## 결론

두 도구 모두 같은 결과를 만들었다. **분기 흐름 설명은 Make**, **초기 설정과 실행 확인은 Zapier**가 더 편리했다.

## 제출 증거

- Make: [전체 시나리오](../evidence/project1/make/01-workflow.png) · [복습 필요](../evidence/project1/make/02-review-result.png) · [암기 완료](../evidence/project1/make/03-complete-result.png)
- Zapier: [전체 Zap](../evidence/project1/zapier/01-workflow.png) · [성공 실행](../evidence/project1/zapier/02-success-run.png) · [복습 필요](../evidence/project1/zapier/03-review-result.png) · [암기 완료](../evidence/project1/zapier/04-complete-result.png)

> 캡처에서는 이메일, 연결 계정, URL과 인증정보를 가린다.

## 참고

- [Zapier 무료 플랜](https://help.zapier.com/hc/en-us/articles/32337438839565-What-s-included-in-Zapier-s-Free-plan)
- [Zapier Paths 지원 플랜](https://help.zapier.com/hc/en-us/articles/8496288555917-Add-branching-logic-to-Zap-workflows-with-Paths)
