# machine_reading_comprehension_kor
klue data mrc

<p align="center">
  <br>
  <img src="https://github.com/leadawon/text_classification_yelp/blob/main/goorm_nlp_8th_group3/project1/img/process.png">
  <br>
  
  [pdf](https://github.com/leadawon/text_classification_yelp/blob/main/goorm_nlp_8th_group3/project1/leadawon/final/%5B2%E1%84%8C%E1%85%A9%5Dproj1_%E1%84%86%E1%85%AE%E1%86%AB%E1%84%8C%E1%85%A1%E1%86%BC%E1%84%87%E1%85%AE%E1%86%AB%E1%84%85%E1%85%B2%E1%84%80%E1%85%B5%E1%84%89%E1%85%A5%E1%86%BC%E1%84%82%E1%85%B3%E1%86%BC%E1%84%80%E1%85%A2%E1%84%89%E1%85%A5%E1%86%AB.pdf) < - PLEASE CLICK THIS TO SEE MORE DETAILS!
  
</p>


## 프로젝트 소개
klue dataset에서 context를 읽고 question에 대한 answer를 출력합니다.

[kaggle](https://www.kaggle.com/competitions/6th-goorm-project-2-korean-mrc) 에서 [Levenshtein Distance](https://en.wikipedia.org/wiki/Levenshtein_distance)를 기준으로 competition을 진행합니다.

최종결과는 levenstrin distance 2.41247로 3등을 차지했습니다.

<p align="center">
<br>
<img src="https://github.com/leadawon/text_classification_yelp/blob/main/goorm_nlp_8th_group3/project1/img/kaggle.png">
<br>
</p>

<p align="justify">

</p>

<p align="center">

</p>

<br>

## 기술 스택

|   Python   |   Pytorch  |  Pandas  | Matplotlib | Wandb | Transformers |

<br>

## 성능을 높이기 위한 방법

### 다양한 사전 학습모델 사용

hugging face 라이브러리에서 

bert ,albert, roberta, electra 를 기반으로 한국어 기반 독해 사전학습 모델을 finetuning

### context slicing

전처리 과정에서 answer가 잘리지 않도록 긴 context문장을 slicing

### hyper parameter tuning

wandb framework : batch_size, learning_rate , the number of epochs

### aihub data

[aihub](https://aihub.or.kr/aihubdata/data/view.do?currMenu=115&topMenu=100&aihubDataSe=realm&dataSetSn=577)에서 뉴스 기사 기계독해 데이터를 학습

<br>

## 배운 점 & 아쉬운 점

레반슈타인 거리를 가지고 점수가 나오기 때문에 무엇보다도 후처리가 중요했다.

1. 경험적으로 특수문자를 없애고 긴 예측 문장을 8글자 이하로 슬라이싱하는 방법이 점수가 잘 나왔다.

2. 앙상블 기법은 아니지만 다양한 모델 중 model의 결과인 logit을 모아서 납득이 가는(길이가 적절한) 정답을 고른다.

hard voting 방법은 성능이 괜찮은 후보 모델이 많았다면 꽤 효과적이었을것이다.

---

전처리 과정에서 context가 너무 길때가 문제였다. kobigbird는 기존 타 모델이 가지고 있었던 한계인 512토큰 길이 이상으로 학습 할 수 없었던 단점을 보완해서 최대 
4096 토큰을 학습할 수 있었다. 하지만 loss가 쉽사리 떨어지지 않았고 기존 모델을 계속 써야 했던 점이 아쉬웠다.

---

후처리 -> 사전학습 모델 > 전처리(학습데이터) -> 하이퍼 파라미터 순서로 모델의 성능을 좌우하는데 중요했다.

다른 조원들은 후처리 단계에서 형태소 분석기를 사용했는데 다음에 mrc task를 할 기회가 생기면 시도해보자!




