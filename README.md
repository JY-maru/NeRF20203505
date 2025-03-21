# 📌 NeRF (Neural Radiance Fields)




## 🚀 Introduction
**NeRF (Neural Radiance Fields)** 는 신경망을 사용하여 3D 장면을 **볼륨 렌더링** 방식으로 학습하고 새로운 시점에서 이미지를 합성하는 기술입니다.  
이를 통해 **소수의 2D 이미지**만으로도 3D 모델을 생성할 수 있습니다.

🔹 논문: [NeRF: Representing Scenes as Neural Radiance Fields for View Synthesis](https://arxiv.org/abs/2003.08934)  
🔹 주요 응용 분야:
- 📷 **3D 장면 재구성**
- 🎮 **게임 및 AR/VR**
- 🎥 **영화 및 특수 효과**
- 🏗️ **건축 및 시뮬레이션**

---

## ⚙️ Installation (설치 방법)
NeRF를 실행하려면 Python 환경과 몇 가지 필수 라이브러리가 필요합니다.

### 1️⃣ **Python 환경 설정**
NeRF는 Python 3.8 이상에서 동작합니다.  
가상 환경을 생성한 후 설치를 진행하는 것을 추천합니다.

```sh
# 가상 환경 생성
python -m venv nerf_env
source nerf_env/bin/activate  # (Windows: nerf_env\Scripts\activate)
```

### 2️⃣ **필수 라이브러리 설치**
```sh
pip install torch torchvision torchaudio
pip install numpy matplotlib tqdm
pip install imageio imageio-ffmpeg
pip install lpips
```

또는 `requirements.txt`가 있는 경우:
```sh
pip install -r requirements.txt
```

---

## 📂 Project Structure (프로젝트 구조)
```plaintext
NeRF_Project/
│── data/                    # 훈련용 데이터셋 (이미지, 카메라 매트릭스)
│── models/                  # NeRF 모델 정의
│── scripts/                 # 훈련 및 테스트 스크립트
│── outputs/                 # 결과 이미지 및 모델 체크포인트 저장
│── nerf.py                  # NeRF 모델 학습 및 추론 코드
│── train.py                 # 학습 코드
│── render.py                # 이미지 생성 코드
│── requirements.txt         # 필요 패키지 목록
│── README.md                # 프로젝트 설명
```

---

## 🔥 Quick Start (빠른 실행)
NeRF 모델을 훈련하고 결과를 생성하는 기본적인 실행 방법입니다.

### **1️⃣ 데이터 준비**
데이터셋(`data/`) 폴더에 2D 이미지 및 카메라 매트릭스를 준비합니다.

### **2️⃣ 모델 학습**
```sh
python train.py --config configs/nerf_config.json
```

### **3️⃣ 학습된 모델로 렌더링**
```sh
python render.py --model-checkpoint outputs/model_latest.pth
```

### **4️⃣ 결과 확인**
생성된 3D 장면 이미지는 `outputs/` 폴더에서 확인할 수 있습니다.

---

## 🛠️ Training Configuration (훈련 설정)
훈련 과정에서 다양한 하이퍼파라미터를 조정할 수 있습니다.  
기본 설정 파일 (`configs/nerf_config.json`) 예제:

```json
{
    "learning_rate": 5e-4,
    "batch_size": 1024,
    "num_epochs": 10000,
    "image_resolution": [400, 400],
    "num_samples_per_ray": 64,
    "use_coarse_fine": true
}
```

---

## 📚 References (참고 자료)
- 📄 논문: [NeRF: Representing Scenes as Neural Radiance Fields](https://arxiv.org/abs/2003.08934)
- 📦 PyTorch NeRF 구현:
  - [github.com/bmild/nerf](https://github.com/bmild/nerf) 
  - 참고 : https://github.com/yenchenlin/nerf-pytorch/blob/master/README.md
- 📖 관련 강의: [3D Deep Learning & NeRF](https://www.mit.edu/~3ddeeplearning/)
- 📹 NeRF 소개 영상: [YouTube](https://www.youtube.com/watch?v=JuH79E8rdKc)
- 🪛 NeRF 단점 및 후속 연구 : https://modulabs.co.kr/blog/nerf-followup/
- 📝 이론 :https://kyujinpy.tistory.com/16

> **paper review**
 - https://woochan-autobiography.tistory.com/933#3.1.%20Ray
 - pipeline : https://woochan-autobiography.tistory.com/957

---

## 🤝 Contributing (기여 방법)
이 프로젝트에 기여하고 싶다면, 다음과 같이 진행해주세요:
1. 이 저장소를 포크(fork)합니다.
2. 새 브랜치를 생성합니다. (`git checkout -b feature-new`)
3. 코드를 수정하고 커밋합니다. (`git commit -m "Add new feature"`)
4. 푸시 후 PR(Pull Request)을 생성합니다.

---

## 📜 License
이 프로젝트는 MIT 라이선스를 따릅니다.  
자세한 사항은 [`LICENSE`](LICENSE) 파일을 확인하세요.

---

## 🎯 Contact (문의)
- 📧 이메일: jeongyeon2134@gmail.com
