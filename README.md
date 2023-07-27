# 훼손된 점자 보도 블록 탐지
YOLOV4를 활용하여, 영상 속 보도 블록을 탐지 




## Preprocess
1. preprocessingIm.mlx: json 형식의 폴리건 라벨링을 mat 형식의 바운딩 박스 라벨링으로 변환
2. preprocessingIm.mlx: 경계상자의 값 조정
3. <>내 사용자 지정 함수 preprocessData(data, size): 사진과 바운딩 박스를 모델에 맞는 크기로 변환





## Model Training 
1. trainset과 test set 분할
2. Datastore 함수를 통해 앞서 저장한 image와 라벨링 데이터의 데이터 저장소 형성
3. 이미지와 라벨링 데이터 저장소를 combine 함수를 통합
4. parameter tuning 
5. doTraining을 통해 훈련
   <detection 되는 사진 넣을 예정>




## Model evaluation
매트랩 내장 함수인 evaluateDetectionPrecision을 활용하여 test data set에 대한 정확도 검출
![image](https://github.com/min913/AI-Retriever_matlab/assets/123183864/7aed140d-29a7-4f7d-88d6-ee67673e086b)





## Detection with WebCam
1. webcam 툴박스를 활용하여 저장된 영상 실행 및 편집
2. load 함수를 통해 기존 학습된 모델 detector 변수에 저장
3. 영상 detect
5. bbox 및 정확도 표시 




## 활용 방법
가중치 파일을 저장 하고, video_detect 파일을 실행하세요. 실시간으로 보도블록이 바운딩 박스와 함께 표시됩니다.




## Customizing 
-데이터를 바꾸고 싶다면, preprocessingIm.mlx에서 하고 싶은 데이터의 경로로 모두 변경하세요 (라벨링 데이터의 형식에 따라 preprocessingIm.mlx를 수정하셔야 합니다.)
-실시간 인식에서 표시되는 데이터를 다르게 표현하거나 다른 데이터를 가져오고 싶다면, camera 파일을 수정하세요. 현재 camer 파일에서는 score와 bbox가 출력되도록 설정되어 있습니다.
 해당 변수들을 수정하세요.





## Tools
- Matlab
- Deep Learning Toolbox
- Computer Vision Toolbox Model for YOLO v4 Object Detection
- Computer Vision Toolbox
- Image Processing Toolbox
