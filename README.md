# AUTOMATIC1111 Kaggle Easy

[English README](README_EN.md)

Google Colab 기반 AUTOMATIC1111 실행 구조를 **Kaggle Notebook GPU 환경으로 포팅**한 교육용 노트북입니다.

Checkpoint, LoRA, LyCORIS, ControlNet, Embedding, VAE를 버튼으로 선택하고, Google Drive·CivitAI·Hugging Face에서 필요한 모델만 다운로드할 수 있습니다.

## 주요 기능

- Kaggle GPU 및 CUDA 연산 자동 확인
- Python 3.10 가상환경과 AUTOMATIC1111 자동 설치
- Checkpoint·LoRA·ControlNet·Embedding·VAE 동시 선택
- 모델 이름 검색, 25개씩 페이지 이동, 전체 개수 표시
- Google Drive `Auto1111` 폴더의 모델 목록 자동 분류
- 실행 패널 첫 화면에서 Google Drive 모델 루트 폴더 지정·변경
- CivitAI·Hugging Face·Google Drive 개별 링크 등록
- 필요한 모델만 선택적으로 다운로드
- 모델 캐시 한도, 자동 정리, 보관 고정 및 삭제
- Cloudflare Quick Tunnel 기반 WebUI 접속
- 실행할 때마다 새로운 임시 비밀번호 생성
- 비밀번호 숨김·표시·복사
- 설치·다운로드 작업 중단
- 생성 이미지 ZIP 다운로드
- WebUI 및 터널 종료

## 파일

```text
AUTOMATIC1111_Kaggle.ipynb
```

## 준비 사항

- 개인 Kaggle 계정
- 전화번호 인증이 완료된 계정
- 사용 가능한 Kaggle GPU 할당량
- Kaggle Notebook의 Internet 설정
- Stable Diffusion Checkpoint 1개 이상

학생마다 자신의 Kaggle 계정에서 Notebook을 복사하여 실행해야 합니다. 교수자 계정이나 다른 학생의 세션을 공동으로 사용하지 마십시오.

## 빠른 실행

1. `AUTOMATIC1111_Kaggle.ipynb`를 Kaggle에 업로드하거나 GitHub에서 가져옵니다.
2. **Copy & Edit**를 누릅니다.
3. 오른쪽 **Settings**에서 **Accelerator → GPU**를 선택합니다.
4. **Internet → On**으로 설정합니다.
5. **Run All**을 누릅니다.
6. 실행 패널 맨 위에서 Google Drive 모델 폴더를 지정하고 **폴더 지정·목록 불러오기**를 누릅니다. Drive 모델을 쓰지 않으면 건너뜁니다.
7. Checkpoint를 하나 이상 선택합니다.
8. 이름 검색과 **이전·다음** 버튼으로 필요한 LoRA·ControlNet·Embedding·VAE를 선택합니다. 다른 페이지에서 선택한 모델도 유지됩니다.
9. **선택 모델 적용·WebUI 실행**을 누릅니다.
10. 상태가 `5/5 · 접속 준비 완료`가 되면 **AUTOMATIC1111 WebUI 열기**를 누릅니다.
11. 사용자명 `a1111`과 실행 패널의 임시 비밀번호로 로그인합니다.

설치와 모델 다운로드 중에는 GPU 사용률이 낮거나 0%로 표시될 수 있습니다. GPU는 WebUI에서 이미지를 생성할 때 주로 사용됩니다.

## Google Drive 모델 폴더

루트 폴더의 이름과 Google Drive 내 위치는 자유롭게 지정할 수 있습니다. 예시는 다음과 같습니다.

```text
Auto1111/
├── checkpoints/
├── Lora/
├── LyCORIS/
├── ControlNet/
├── embeddings/
└── VAE/
```

1. 사용할 Google Drive 모델 루트 폴더를 **링크가 있는 모든 사용자 → 뷰어**로 공유합니다.
2. 실행 패널 맨 위의 **Drive 모델 폴더**에 공유 링크를 입력합니다.
3. **폴더 지정·목록 불러오기**를 누릅니다.

다른 루트 폴더로 바꾸려면 첫 화면의 링크를 교체하고 같은 버튼을 다시 누릅니다. 지정한 링크는 같은 Kaggle 세션에서 실행 패널을 다시 열어도 유지됩니다. **Drive 폴더** 탭에서는 특정 모델 하위 폴더를 별도로 추가할 수 있습니다.

목록 불러오기는 파일명과 모델 종류만 확인합니다. 모든 모델을 한꺼번에 다운로드하지 않습니다. **사용** 또는 **다운로드**를 선택한 모델만 Kaggle 작업 공간에 저장됩니다.

모델 목록은 한 페이지에 25개씩 표시됩니다. 검색어와 종류·표시 필터를 바꾸면 첫 페이지부터 다시 표시됩니다.

Google Drive의 원본 파일은 수정하거나 삭제하지 않습니다.

## 개별 모델 링크

다음 주소를 **파일 링크** 탭에 등록할 수 있습니다.

- CivitAI 모델 페이지 또는 직접 다운로드 주소
- Hugging Face `/resolve/` 파일 주소
- Google Drive 개별 파일 공유 주소

Google Drive 개별 파일에는 저장할 파일명을 입력해야 합니다.

비공개 또는 이용 동의가 필요한 모델은 Kaggle Secrets에 다음 값을 저장할 수 있습니다.

```text
CIVITAI_API_TOKEN
HF_TOKEN
```

토큰을 Notebook 코드, GitHub 저장소, URL 또는 실행 결과에 기록하지 마십시오.

## 모델 관리 버튼

| 버튼 | 기능 |
|---|---|
| 사용 | 다음 WebUI 실행에 연결할 모델 선택 |
| 다운로드 | 해당 모델만 Kaggle 작업 공간에 다운로드 |
| 보관 고정 | 자동 캐시 정리에서 제외 |
| 삭제 | Kaggle에 받은 복사본만 삭제 |
| 작업 중단 | 설치 또는 다운로드 작업 중단 |
| 선택 모델 적용·WebUI 실행 | 선택한 모델을 연결하고 WebUI 시작 |
| WebUI 종료 | AUTOMATIC1111과 터널 종료 |
| 이미지 ZIP | 생성 이미지를 ZIP으로 다운로드 |

Checkpoint는 반드시 하나 이상 선택해야 합니다. SD 1.5와 SDXL용 Checkpoint·LoRA·ControlNet·VAE가 서로 호환되는지 확인하십시오.

## 모델 캐시

기본 모델 캐시 한도는 20 GiB이며 실행 설정에서 변경할 수 있습니다. 한도를 초과하면 선택한 정책에 따라 오래 사용하지 않은 모델을 정리합니다.

다음 모델은 자동 정리에서 보호됩니다.

- 현재 선택한 모델
- 실행 중인 WebUI에 연결된 모델
- 보관 고정한 모델

Kaggle 작업 공간은 영구 저장소가 아닙니다. 세션이 종료되면 모델과 생성 이미지가 사라질 수 있습니다.

## WebUI 로그인

- 사용자명: `a1111`
- 비밀번호: 실행할 때마다 새로 생성되는 임시 비밀번호
- 접속 주소: 실행할 때마다 생성되는 임시 `trycloudflare.com` 주소

WebUI 로그인 정보는 Kaggle 계정 ID나 비밀번호가 아닙니다. 비밀번호는 기본적으로 가려지며 **비밀번호 복사** 버튼으로 복사할 수 있습니다.

Cloudflare 계정은 필요하지 않습니다. 임시 접속 주소와 비밀번호를 외부에 공개하지 마십시오.

## 생성 이미지와 세션 종료

생성 이미지는 다음 위치에 저장됩니다.

```text
/kaggle/working/downloads/generated
```

실습 종료 순서:

1. **이미지 ZIP**으로 결과를 내려받습니다.
2. **WebUI 종료**를 누릅니다.
3. Kaggle 오른쪽 위 세션 메뉴에서 **Stop Session**을 선택합니다.

브라우저 탭만 닫으면 Kaggle GPU 세션이 계속 실행될 수 있습니다.

## 공개 저장소 보안

다음 항목은 GitHub에 올리지 마십시오.

- CivitAI·Hugging Face 인증 토큰
- Kaggle API 키와 `kaggle.json`
- WebUI 임시 비밀번호와 접속 주소
- 유료 또는 재배포가 제한된 모델 파일
- 개인정보가 포함된 생성 이미지
- 인증 정보가 남은 실행 로그

공개 저장소에 커밋하기 전에 Notebook의 실행 결과를 모두 지우는 것을 권장합니다.

## 버전 정보

- Notebook 배포판: `v1.0.2`
- AUTOMATIC1111: `v1.10.1`
- Python 가상환경: `3.10`
- PyTorch: `2.1.2`
- Torchvision: `0.16.2`
- PyTorch CUDA 빌드: `cu121`

Kaggle 실행 이미지, CUDA 드라이버, 네트워크 정책 및 외부 프로젝트가 변경되면 Notebook 업데이트가 필요할 수 있습니다.

## 라이선스와 이용 조건

이 저장소에서 직접 작성한 Notebook 코드와 문서는 [MIT License](LICENSE)로 공개합니다. 누구나 교육·연구·개인·상업적 목적으로 사용하고 복제·수정·재배포할 수 있습니다. 재배포할 때는 원래의 저작권 고지와 MIT License 고지를 유지해야 합니다.

AUTOMATIC1111, 확장 프로그램 및 모델은 각각의 라이선스와 이용 조건을 따릅니다. 이 저장소의 MIT License가 외부 프로젝트나 모델 파일의 라이선스를 변경하지는 않습니다. 재배포 권한이 확인되지 않은 모델 파일은 저장소에 포함하지 마십시오.

생성 이미지의 저작권, 초상권, 개인정보, 허위정보, 편향 및 유해 콘텐츠 문제는 사용자가 확인해야 합니다.

## 참고 자료

- [Kaggle Notebooks](https://www.kaggle.com/docs/notebooks)
- [Kaggle Efficient GPU Usage](https://www.kaggle.com/docs/efficient-gpu-usage)
- [AUTOMATIC1111 Stable Diffusion WebUI](https://github.com/AUTOMATIC1111/stable-diffusion-webui)
- [Cloudflare Quick Tunnels](https://developers.cloudflare.com/cloudflare-one/connections/connect-networks/do-more-with-tunnels/trycloudflare/)
- [gdown](https://github.com/wkentaro/gdown)
- [CivitAI](https://civitai.com/)
- [Hugging Face Models](https://huggingface.co/models)
- [ControlNet WebUI Extension](https://github.com/Mikubill/sd-webui-controlnet)

## 오류 제보

오류가 발생한 단계, Kaggle GPU 종류, Checkpoint 계열, 오류 메시지, 재현 방법과 관련 로그의 마지막 부분을 제출해 주십시오. 토큰, 임시 비밀번호, 비공개 모델 링크는 포함하지 마십시오.
