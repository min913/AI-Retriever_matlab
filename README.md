# 훼손된 점자 보도 블록 탐지
YOLOV4를 활용하여, 보도 블록을 Real-time 탐지 


## Preprocess
1. <전처리 파일 이름>: json 형식의 폴리건 라벨링을 mat 형식의 바운딩 박스 라벨링으로 변환
2. <전처리 파일 이름>: 경계상자의 값 조정
3. <>내 사용자 지정 함수 preprocessData(data, size): 사진과 바운딩 박스를 모델에 맞는 크기로 변환



## Model Training 
1. trainset과 test set 분할 (비율이 몇이였지)
2. Datastore 함수를 통해 앞서 저장한 image와 라벨링 데이터의 데이터 저장소 형성
3. 이미지와 라벨링 데이터 저장소를 combine 함수를 통합
4. parameter tuning 
5. doTraining을 통해 훈련
   <detection 되는 사진 넣을 예정>


## Model evaluation
매트랩 내장 함수인 evaluateDetectionPrecision을 활용하여 test data set에 대한 정확도 검출
<여기도 precision사진 넣을 예정>


## Real-time Detection with WebCam
1. webcam 툴박스를 활용하여 webcam 실행
2. load 함수를 통해 기존 학습된 모델 detector 변수에 저장
3. webcam 영상을 연속으로 snapshot
4. 사진 detect
5. bbox 및 정확도 표시 


## 활용 방법
<가중치 파일 이름>을 다운 받고, camera 파일을 실행하세요. 실시간으로 보도블록이 바운딩 박스와 함께 표시됩니다.


##Customizing 
-데이터를 바꾸고 싶다면, <전처리 파일 이름>에서 하고 싶은 데이터의 경로로 모두 변경하세요 (라벨링 데이터의 형식에 따라 <전처리 파일 이름>를 수정하셔야 합니다.)
-실시간 인식에서 표시되는 데이터를 다르게 표현하거나 다른 데이터를 가져오고 싶다면, camera 파일을 수정하세요. 현재 camer 파일에서는 score와 bbox가 출력되도록 설정되어 있습니다.
 해당 변수들을 수정하세요.


## WEB Demo
유튜브 링크


## Tools
- Matlab
- Deep Learning Toolbox
- Computer Vision Toolbox Model for YOLO v4 Object Detection
- Computer Vision Toolbox
- Image Processing Toolbox
- MATLAB Support Package for USB Webcams
