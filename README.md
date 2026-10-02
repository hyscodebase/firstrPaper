# RoBERTa NLP 파인튜닝·평가 실험

`FIRSTPAPER.ipynb`에서 RoBERTa 감성 분류 학습과 여러 NLP 작업에 대한 평가 흐름을 실험합니다. 모델·데이터셋을 다운로드하고 학습하는 노트북 형태의 연구 작업 공간입니다.

## 노트북 내용

- `roberta-base`와 SST-2로 문장 감성 분류 학습
- Hugging Face `Trainer` 기반 학습·평가 및 모델 저장
- `ComprehensiveNLPEvaluator`를 통한 감성·아이러니·토큰 분류 평가 구성
- SST-2, TweetEval, CoNLL-2003, Universal Dependencies 데이터셋 로딩 코드

진입점은 [FIRSTPAPER.ipynb](FIRSTPAPER.ipynb)입니다. 저장소에는 독립적인 논문 원고나 재현 완료 보고서가 포함되어 있지 않습니다.

## 실행

Google Colab 또는 Jupyter에서 노트북을 열고 환경 설치 셀부터 실행하세요. 주요 의존성은 `torch`, `transformers`, `datasets`, `evaluate`, `accelerate`, `seqeval`, `scikit-learn`, `pandas`입니다.

GPU 런타임을 사용하면 학습 시간을 줄일 수 있습니다. 코드는 CUDA 가능 여부에 따라 일부 배치 크기를 조정합니다. 데이터셋·모델 다운로드를 위한 인터넷 연결이 필요합니다.

## 설정과 결과

기본 모델은 `roberta-base`, 초기 감성 분류 실험은 3 epoch로 설정되어 있습니다. 로컬 실행 시 `/content/results`, `/content/final_sentiment_model` 등의 Colab 전용 경로를 수정하세요.

데이터셋 로딩 방식과 `Trainer` 인자는 라이브러리 버전의 영향을 받습니다. 노트북의 설치 셀은 업그레이드를 수행하므로, 재현 실험에서는 실제 사용한 패키지 버전·seed·데이터 분할을 별도로 기록하세요. 코드에 평가 흐름이 있다는 사실과 검증된 성능 수치를 구분해야 합니다.
