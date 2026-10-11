# Release Notes

## v1.0.2 – Model List Usability Update

Released: 2026-10-11

License: MIT

### Changes

- Show 25 matching models per page with a count and previous/next controls.
- Keep model selections when changing pages; reset to page one when a search or filter changes.
- Clarify the Google Drive shared-folder URL steps. The folder must allow anyone with the link to view it.

## v1.0.1 – Kaggle Classroom Edition

### 한국어

Google Colab 기반 AUTOMATIC1111 실행 구조를 Kaggle Notebook GPU 환경으로 포팅한 교육용 공개 버전입니다.

### 주요 기능

- Kaggle GPU 및 CUDA 연산 확인
- Python 3.10 환경과 AUTOMATIC1111 자동 설치
- Checkpoint·LoRA·ControlNet·Embedding·VAE 동시 선택
- Google Drive `Auto1111` 폴더 자동 분류
- 첫 화면에서 Google Drive 모델 루트 폴더 지정·변경 및 세션 내 설정 유지
- CivitAI·Hugging Face·Google Drive 모델 등록
- 모델 캐시 및 저장 공간 관리
- Cloudflare Quick Tunnel 기반 WebUI 접속
- 세션별 임시 비밀번호
- 작업 중단, 이미지 ZIP 다운로드 및 WebUI 종료

### 실행 전 확인

- Kaggle Settings에서 GPU를 선택하십시오.
- Internet을 On으로 설정하십시오.
- Checkpoint를 하나 이상 선택하십시오.
- 학생마다 자신의 Kaggle 계정과 Notebook 사본을 사용하십시오.

### English

This is an educational public release of a Google Colab-based AUTOMATIC1111 workflow ported to the Kaggle Notebook GPU environment.

### Main Features

- Kaggle GPU and CUDA computation verification
- Automatic Python 3.10 environment and AUTOMATIC1111 installation
- Simultaneous selection of Checkpoints, LoRAs, ControlNet models, Embeddings, and VAEs
- Automatic classification of the Google Drive `Auto1111` folder
- Google Drive model root folder selection on the first screen, with session persistence
- CivitAI, Hugging Face, and Google Drive model registration
- Model cache and storage management
- WebUI access through a Cloudflare Quick Tunnel
- Session-specific temporary passwords
- Task cancellation, image ZIP download, and WebUI termination

### Before Running

- Select a GPU in Kaggle Settings.
- Set Internet to On.
- Select at least one Checkpoint.
- Use a separate Kaggle account and Notebook copy for each student.

### Known Limitations

Kaggle runtime environments and upstream software can change without notice. Updates to Kaggle, AUTOMATIC1111, PyTorch, Cloudflare, or third-party extensions may affect installation or execution. Cloudflare Quick Tunnel URLs are temporary and change between launches.
