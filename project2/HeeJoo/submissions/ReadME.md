# 최종 csv 파일들 Levenshtein Distance 정리

## 기준 : klue.csv

- roberta_large_acc.csv -> 2.51 (nlpotato/roberta_large_origin_added_korquad)
- nlp04org_and_korquad.csv -> 2.55 (nlp04/org_and_korquad)
- lmqgmbart-large-cc25-koquad-qg.csv -> 3.32 (Facebook dataset)
- koelectra -> 3.19 (monologg/koelectra-base-v3-finetuned-korquad)
- baseline -> 128.3
- bertbase -> 3.85 (sangrimlee/bert-base-multilingual-cased-korquad) -> 후처리로 긴 거 자른 후
- bertbase11 -> 21.2 (sangrimlee/bert-base-multilingual-cased-korquad) -> 후처리로 긴 거 자르기 전
- albert -> 5.39 (kykim/albert-kor-base)
- blank -> 5.10
- kobert_morp_korquad -> 6.16 (jack-oh/korbert_morp_korquad)
- roberta_origin_added -> 2.62 (nlpotato/roberta_large-ssm_wiki_e2-origin_added_korquad_e5)
- xlm-roberta-large -> 3.03 (hanmaroo/xlm_roberta_large_korquad_v2)


### nlpotato/roberta_large_origin_added_korquad 모델로 학습하고, 코드만 수정해서 돌린 파일들
- roberta_acc_logit -> 2.54 (nlpotato/roberta_large_origin_added_korquad) -> 전처리로 context 자르고, 후처리로 logit 선택 및 긴 거 자르기 작업
- roberta_accumulation -> 4.09 (nlpotato/roberta_large_origin_added_korquad) -> 다원님 후처리 시도
- roberta_finetuned -> 2.63 (nlpotato/roberta_large_origin_added_korquad)
- roberta_large_origin -> 2.60 (nlpotato/roberta_large_origin_added_korquad) -> 아무것도 수정 안 하고 모델만 바꾸고 돌린 파일
- roberta_preprocess -> 3.67 (nlpotato/roberta_large_origin_added_korquad) -> 다원님 후처리 시도
