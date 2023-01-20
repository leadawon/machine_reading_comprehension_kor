# LEADAWON

가장 최신 코드는 
<https://github.com/leadawon/goorm_nlp_8th_group3/blob/master/project2/leadawon/nlp04%20org_and_korquad.ipynb>
입니다!!


-----------------

### NOW UPDATED

한번 코드를 실행시키면 pickle이 두개 만들어집니다.

하나는 context slicing없이 문장을 예측합니다.

다른 하나는 context가 길때 앞부분을 자르고 문장을 예측합니다.

-------------------------------------------------------------------


### HISTORY

voting 코드 추가했습니다.

voting 폴더에 있습니다.








효택님의 logit_prediction 코드 적용

test 단계에서 context slicing 할때 

범위를 완화해서 더 자연스러운 문장을 학습하도록 코드를 수정했습니다.

후처리 단계에서 특수문자를 없애는 remove_post가 모든 특수문자를 없애도록 원상복구했습니다.





전처리 과정과 비슷하게 testing 단계에서 context가 길때 발생하는 문제를 해결하였습니다.

context가 800글자보다 길면 800글자 이후의 context로 답을 예측합니다.

start logit, end logit의 합이 더 큰 pred 값을 선택합니다.





전처리 과정 추가했습니다.

(answer_start가 1200 이상일때 1000이상일때 800이상일때 나눠서 context를 적당히 자릅니다.

물론 answer_start도 그만큼 보정을 받습니다.)



후처리 과정이 생겼습니다.



특수문자 및 공백을 제거합니다.



wandb 돌려본 결과 32 batch_size가 성능이 제일 좋았습니다! (64는 OOM)



validation code가 있습니다.



postprocess로 정답 문장을 [:5] 앞부터 최대 5글자만 나오도록 슬라이싱 했습니다!




