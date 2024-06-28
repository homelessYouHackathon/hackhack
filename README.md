# 📸객체 및 텍스트 탐지 AI를 사용하여 SNS 상 개인정보 노출로 인한 피해 방지 웹사이트 SAVE, YOU

![image](https://github.com/homelessYouHackathon/hackhack/assets/125464850/6eda703b-1781-41f8-98b7-49a0089fe837)

<br>

## 프로젝트 소개

- SAVE, YOU는 표지판의 글씨나, 건물의 외관 등을 살짝 변형함으로써 개인정보 노출로 인한 피해를 방지하는 웹사이트입니다.
- SNS에 단순히 올린 사진의 배경의 건물 특성, 표지판 정보 등에서 개인정보가 노출될 가능성이 있습니다. 이는 타인이 악용하여 추가적인 범죄를 일으킬 수 있다는 점에서 심각성이 크다고 생각하여 해당 프로젝트를 고안하게되었습니다.
- 해당 웹사이트는 사용자가 이미지 처리 대상 항목을 선택하고, SNS에 올리려는 사진을 Click To Upload Image에 넣어주면 자동으로 민감한 정보를 삭제해줍니다.

<br>

## 기술 스택

|   Django   |   HTML5   |   CSS    |  JavaScript   |
| :--------: | :-------: | :------: | :-----------: |
|   <img src="https://img.shields.io/badge/django-092E20?style=for-the-badge&logo=django&logoColor=white">    |  <img src="https://img.shields.io/badge/html5-E34F26?style=for-the-badge&logo=html5&logoColor=white">  |  <img src="https://img.shields.io/badge/css-1572B6?style=for-the-badge&logo=css3&logoColor=white">  |    <img src="https://img.shields.io/badge/javascript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black">      |

### 개발환경
- **AI 모델**
  - 모델: YOLOv8
  - 라이브러리: OpenCV, Tesseract(OCR)

- **기타 도구**
  - 버전 관리: Git, GitHub
  - 통합 개발 환경 (IDE): Visual Studio Code
  - GPU: Google Colab
  - 라벨링 도구 : LabelImg
  - 협업 툴 : Notion, Github Wiki, Canva
  - 서비스 배포 환경 : Cloudtype
<br>

## 구현 기능

### 특수한 공간의 위치 탐지 방지
- YOLOv8 객체탐지를 통해 표지판과 건물을 탐지하고 Bounding Box 내의 이미지를 삭제하여 Inpainting으로 주변 배경으로 빈공간을 채워준다.

### 민감한 정보 삭제
- 주민번호, 전화번호, 도로명 등과 같이 개인정보가 포함된 숫자들을 Tesseract를 이용하여 탐지하여 Opencv로 삭제후 주변 배경색으로 덮어준다.

### SAVE, YOU 웹사이트
1. 주소, 건물 등 같은 처리하고 싶은 항목을 선택한다.
2. SNS에 올리려는 사진을 Click To Upload Image에 사진을 드래그드랍하고 Upload버튼을 누른다.
3. 민감한 정보를 삭제하여 처리한 이미지 결과가 Processed Image에 생성된다.

<br>

## 프로젝트 구조

```
┣ README.md
┗ image_p
   ┣ core
   ┃ ┣ migrations
   ┃ ┃ ┣ __pycache__
   ┃ ┃ ┃ ┣ __init__.cpython-310.pyc
   ┃ ┃ ┃ ┗ __init__.cpython-312.pyc
   ┃ ┃ ┗ __init__.py
   ┃ ┣ static
   ┃ ┃ ┣ css
   ┃ ┃ ┃ ┣ main.css
   ┃ ┃ ┃ ┗ service.css
   ┃ ┃ ┣ image
   ┃ ┃ ┃ ┣ click.jpg
   ┃ ┃ ┃ ┣ new_logo.png
   ┃ ┃ ┃ ┗ save_you_logo.png
   ┃ ┃ ┗ runs
   ┃ ┃ ┃ ┣ best.pt
   ┃ ┃ ┃ ┗ best_sign.pt
   ┃ ┣ templates
   ┃ ┃ ┗ myapp
   ┃ ┃ ┃ ┣ main.html
   ┃ ┃ ┃ ┣ more_info.html
   ┃ ┃ ┃ ┗ service.html
   ┃ ┣ __pycache__
   ┃ ┃ ┣ admin.cpython-310.pyc
   ┃ ┃ ┣ admin.cpython-312.pyc
   ┃ ┃ ┣ apps.cpython-310.pyc
   ┃ ┃ ┣ apps.cpython-312.pyc
   ┃ ┃ ┣ models.cpython-310.pyc
   ┃ ┃ ┣ models.cpython-312.pyc
   ┃ ┃ ┣ urls.cpython-310.pyc
   ┃ ┃ ┣ urls.cpython-312.pyc
   ┃ ┃ ┣ views.cpython-310.pyc
   ┃ ┃ ┣ views.cpython-312.pyc
   ┃ ┃ ┣ __init__.cpython-310.pyc
   ┃ ┃ ┗ __init__.cpython-312.pyc
   ┃ ┣ admin.py
   ┃ ┣ apps.py
   ┃ ┣ models.py
   ┃ ┣ tests.py
   ┃ ┣ urls.py
   ┃ ┣ views.py
   ┃ ┗ __init__.py
   ┣ image_p
   ┃ ┣ __pycache__
   ┃ ┃ ┣ settings.cpython-310.pyc
   ┃ ┃ ┣ settings.cpython-312.pyc
   ┃ ┃ ┣ urls.cpython-310.pyc
   ┃ ┃ ┣ urls.cpython-312.pyc
   ┃ ┃ ┣ wsgi.cpython-310.pyc
   ┃ ┃ ┣ wsgi.cpython-312.pyc
   ┃ ┃ ┣ __init__.cpython-310.pyc
   ┃ ┃ ┗ __init__.cpython-312.pyc
   ┃ ┣ asgi.py
   ┃ ┣ settings.py
   ┃ ┣ urls.py
   ┃ ┣ wsgi.py
   ┃ ┗ __init__.py
   ┣ db.sqlite3
   ┣ manage.py
   ┣ Procfile
   ┣ requirements.txt
   ┗ runtime.txt
```

<br>

## 프로젝트 결과물

<div align="center">
  
<img src="https://github.com/homelessYouHackathon/hackhack/assets/125464850/9107e034-d2f4-4da4-b87c-f900168a146d" height=200 width=200>
<img src="https://github.com/homelessYouHackathon/hackhack/assets/125464850/9269e0e5-5645-4b07-9cf6-361eae44605d" height=200 width=200>

건물 탐지 정확도 | 표지판 탐지 정확도

![image](https://github.com/homelessYouHackathon/hackhack/assets/125464850/d3cd2115-d4f2-4f4b-8b57-a6fc1eedaa66)

웹 사이트 시현 결과

</div>

<br>

## 팀원 구성

<div align="center">

| **이정연** | **이유진** | **백세희** |
| :--------: |  :--------: | :--------: |
| ![image](https://github.com/homelessYouHackathon/hackhack/assets/125464850/e6773656-8aea-4a77-bc7e-3da289ce316a) | ![image](https://github.com/homelessYouHackathon/hackhack/assets/125464850/f266a5b3-47b5-49fc-8bbc-849927524979) | ![image](https://github.com/homelessYouHackathon/hackhack/assets/125464850/0bfbe2e5-10d4-4b22-a310-22f96e69ebbf) |

</div>

<br>

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details
