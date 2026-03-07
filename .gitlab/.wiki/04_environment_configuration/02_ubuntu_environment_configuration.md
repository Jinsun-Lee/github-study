---
title: 4.2 Ubuntu 환경 세팅
---







# 1. 네트워크 연결
1. 우측 상단의 와이파이 아이콘 클릭
2. 연결할 와이파이 클릭
3. Address(IP), Netmask, Gateway, DNS 정보를 각각 입력 후 저장

<img width="597" height="309" alt="image" src="https://github.com/user-attachments/assets/14fc71e0-321e-4df3-9f34-b97f8eea3bab" />
<img width="598" height="459" alt="image" src="https://github.com/user-attachments/assets/2ee2a92e-33fc-4c01-9537-d81f0fe28640" />

<br><br>

# 2. 한글 입력기 설치
```
sudo apt update
sudo apt install -y ibus-hangul
```

<br>

- **윈도우키 - Settings - Keyboard - Input Sources에서 Korean (Hangul) 추가**
- **그 외 언어 전부 삭제**
- **오른쪽 점 3개 - Preferences**

<img width="1958" height="1312" alt="image" src="https://github.com/user-attachments/assets/75148367-a173-4654-98a7-c6a3d71d8766" />


<br>

- **Remove(R)로 모두 삭제**
- **Add(A) 누르고 한/영 키 누르기**
- **Apply(A) - OK(O)**

<img width="1259" height="1068" alt="image" src="https://github.com/user-attachments/assets/f796af35-c3c0-41e7-819f-74acc40446f9" />


<br><br>

# 3. GPU 설치 방법
```
sudo apt update && sudo apt upgrade -y
ubuntu-drivers devices
```

출력 내용 중 recommended가 표시된 버전을 확인(예: 590-open)      
<img width="1540" height="1162" alt="image" src="https://github.com/user-attachments/assets/287a37f0-70f9-4938-846d-3a04202ddcae" />

```
sudo apt install nvidia-driver-590-open  # 본인의 추천 버전 숫자로 변경
sudo reboot
```

<br>

PyTorch 설치 (CUDA 12.8 대응)    
```
sudo apt install python3 python3-pip
pip3 install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu128
```

<br>

GPU 설치 확인    
터미널에 GPU_TEST를 입력했을 때 아래와 같이 출력되면 성공
```
python3 -c "import torch; print(f\"CUDA available: {torch.cuda.is_available()}\"); print(f\"GPU name: {torch.cuda.get_device_name(0) if torch.cuda.is_available() else None}\")"
```

<img width="1221" height="406" alt="image" src="https://github.com/user-attachments/assets/4e9e81a4-7a75-4385-bc0d-c35acf9093b9" />


<br><br>

# 4. Gitlab 계정 저장
```
git config --global credential.helper store
```
```
git config --global user.name "이름"
git config --global user.email "메일 
```
