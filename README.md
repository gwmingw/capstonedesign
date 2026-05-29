# Unsupervised Event Abstraction & Process Mining

## 📌 프로젝트 소개
이 프로젝트는 센서(PLC)에서 수집되는 연속적인 로우 데이터(Raw Data)를 비지도 학습(Unsupervised Learning) 기법으로 분석하여 유의미한 공정 단계(Event)로 추상화하고, 이를 바탕으로 프로세스 마이닝 모델을 도출하는 전체 파이프라인을 구현한 코드입니다.

데이터 생성부터 전처리, 머신러닝 기반 군집화, PM4Py를 활용한 프로세스 맵(DFG) 시각화까지의 전 과정을 담고 있습니다. AI 코딩 어시스턴트(바이브코딩)를 활용해 구현되었으며, 코드 생성에 사용된 프롬프트 로그를 함께 제공합니다.

## 📂 포함된 파일
* **unsupervised_event_abstraction_replication.ipynb**: 데이터 전처리, 클러스터링, 프로세스 맵 도출 파이프라인이 모두 포함된 주피터 노트북 파일
* **PROMPTS.md**: AI 코딩 툴을 활용해 해당 코드를 자동 생성하기 위해 작성한 프롬프트 기록

## 🛠 기술 스택
* **Language**: Python
* **Machine Learning**: scikit-learn (PCA, KMeans, Silhouette Score)
* **Process Mining**: pm4py
* **Data Processing & Visualization**: numpy, pandas, matplotlib

## 🚀 주요 파이프라인 흐름
1. **가상 데이터 생성**: 노이즈가 2% 포함된 4단계 공정의 시계열 PLC 패턴 데이터 생성
2. **슬라이딩 윈도우**: 시계열의 과거 맥락을 모델에 반영하기 위한 윈도우 사이즈 5의 데이터 변환
3. **PCA 차원 축소**: 다차원 데이터를 3차원으로 압축 및 3D 산점도 시각화
4. **K-Means 클러스터링**: 군집 4개로 설정하여 비지도 학습 기반 공정 단계 식별
5. **성능 평가**: 실루엣 계수(Silhouette Coefficient)를 산출하여 군집화 품질 검증
6. **시계열 시각화**: 타임스텝의 흐름에 따른 공정 전환 주기를 계단형 그래프로 확인
7. **이벤트 로그 변환**: pm4py 라이브러리 입력 양식에 맞춘 데이터프레임 포맷팅
8. **프로세스 맵 도출**: Directly-Follows Graph(DFG) 알고리즘을 통한 프로세스 모델 시각화

## 💻 실행 방법

**필수 라이브러리 설치**
아래 명령어를 통해 파이프라인 실행에 필요한 패키지들을 설치합니다.
```bash
pip install numpy pandas matplotlib scikit-learn pm4py
