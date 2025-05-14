# Finance-Engineering
# 아시안 옵션 공정가치 산출 (분산감소기법 적용)

## 📌 프로젝트 개요
이 프로젝트는 Monte Carlo 시뮬레이션을 기반으로 아시안 옵션(Asian Option)의 공정가치를 평가하고,  
효율적인 평가를 위해 **분산감소기법(Variance Reduction Techniques)** 을 적용한 결과를 비교 분석합니다.

- 옵션 유형: 유럽형 평균결제 아시안 콜옵션
- 평가 방법: Monte Carlo Simulation
- 분산 감소 기법:
  - Antithetic Variates
  - Control Variates (기초자산 종가에 대한 유사 유럽형 옵션 사용)

---

## 💻 사용 기술
- Python (Jupyter Notebook)
- Numpy / Scipy / Matplotlib
- 확률 과정 시뮬레이션 (GBM)
- 통계적 수렴 비교

---

## 📈 주요 결과

| 방법                 | 시뮬레이션 횟수 | 공정가치 추정치 | 표준편차 (추정 오차) |
|----------------------|----------------|----------------|--------------------|
| 일반 MC              | 10,000         | 약 5.23         | 0.082              |
| Antithetic Variates  | 10,000         | 약 5.20         | 0.059              |
| Control Variates     | 10,000         | 약 5.21         | 0.038              |

→ **Control Variates 기법 적용 시 분산이 가장 크게 감소**하며 효율적임을 확인함.

---

## 📚 이론 요약

- 아시안 옵션은 평균가격을 기준으로 결제되기 때문에 일반 유럽형 옵션보다 평가가 복잡함
- Monte Carlo 시뮬레이션을 활용하면 다수의 경로를 통해 평균가격의 분포를 근사할 수 있음
- 그러나 시뮬레이션 오차가 크기 때문에 분산감소기법을 통해 더 정확하고 빠르게 계산 가능함

---

## 📂 파일 설명

| 파일명                   | 설명                                |
|--------------------------|-------------------------------------|
| `AsianOption_MC_VR.ipynb` | 아시안 옵션 공정가치 평가 Jupyter 노트북 |
| `README.md`               | 프로젝트 설명 파일                   |

---

## 🔧 실행 방법
```bash
# 필요한 라이브러리 설치
pip install numpy scipy matplotlib
