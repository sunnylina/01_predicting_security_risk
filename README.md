### 1. 제출 및 팀 구성
1일 최대 제출 횟수 : 3회
팀 최대 인원 :5명
⠀

2. 모델
패턴 매칭 알고리즘 사용 불가
패턴 매칭 알고리즘이 확인될 경우 수상에서 제외
⠀

3. 평가
평가 산식 : Macro F1
1차 평가(Public Score): 테스트 데이터 중 랜덤 샘플 된 50%로 채점, 대회 기간 중 공개
2차 평가(Private Score): 나머지 50 % 테스트 데이터로 채점, 대회 종료 직후 공개
제출 파일은 2개까지 선택할 수 있으며 최종 순위는 선택된 파일 중에서 채점되므로, 참가자는 제출 창에서 자신이 최종적으로 채점 받고 싶은 파일을 선택해야 함
대회 직후 공개되는 Private Score 랭킹은 최종 순위가 아니며, 코드 검증 후 최종 수상자가 결정됨
`⠀from sklearn import metrics`

`def macro_f1(answer_df, submission_df):`
    `submission_df = submission_df[submission_df['id'].isin(answer_df['id'])]`
    `submission_df.index = range(submission_df.shape[0])`
    
    `true = answer_df['level']`
    `pred = submission_df['level']`
    
    `score = metrics.f1_score(y_true=true, y_pred=pred, average='macro')`
    
    `return score`
4. 코드 평가
다음 조건을 만족하며 제출한 코드로 Private score가 복원된 상위 10팀에게 상금을 수여합니다.
조건 1. Private 순위 공개 후 코드 제출 기간 내 코드를 코드공유 게시판 게시한 팀
⠀ 제목 양식 : 팀이름, Private 순위와 Private 점수, 모델 이름 내 용 : 전처리, 학습, 후처리, 추론 일련의 과정을 담은 코드를 게시 예시) 데이콘팀, Private 1위, Private 점수 :0.76, ResNet

5. 개인 또는 팀 참여 규칙
개인 또는 팀을 이루어 참여할 수 있습니다.
단체 혹은 기관 참여시 별도의 절차가 필요합니다. (More > 공지사항> 게시글 확인)
개인 참가 방법: 팀 신청 없이, 자유롭게 제출 창에서 제출 가능
팀 구성 방법: 팀 페이지(https://www.dacon.io/competitions/official/235717/team/)에서 팀 구성 안내 확인
팀 최대 인원: 5 명
⠀          * 동일인이 개인 또는 복수팀에 중복하여 등록 불가.

6. 외부 데이터 및 사전학습 모델
외부 데이터 및 사전학습 모델 사용 前 대회문의 게시판에 문의 要
⠀

7. 유의사항
1일 최대 제출 횟수: 3회
사용 가능 언어: Python, R
모델 학습에서 검증 혹은 평가 데이터셋 활용시(Data Leakage 등) 실격
validation_sample.csv를 데이터 증강 또는 학습에사용시(Data Leakage) 실격
최종 순위는 선택된 파일 중에서 채점되므로 참가자는 제출 창에서 자신이 최종적으로 채점 받고 싶은 파일을 선택해야 함
대회 직후 공개되는 Private 랭킹은 최종 순위가 아니며 코드 검증 후 수상자가 결정됨
데이콘은 부정 제출 행위를 금지하고 있으며 데이콘 대회 부정 제출 이력이 있는 경우 평가가 제한됩니다. 자세한 사항은 아래의 링크를 참고해 주시기 바랍니다. https://dacon.io/notice/notice/13
