# I. Computer Vision
## 개요
- 인공지능의 한 분야
- 컴퓨터 시스템을 통해 디지털 이미지, 비디오 및 기타 시각적 입력에서 의미있는 정보를 추출한 다음 이러한 정보를 바탕으로 작업을 실행
- Computer Vision 종류
  - Image Classification
  - Object Localization
  - Object Detection
  - Image Segmentation
## 데이터셋
- PASCAL VOC 2012
  - 패턴 분석, 통계적 모델링, 계산학습
  - http://host.robots.ox.ac.uk/pascal/VOC/voc2012
  - 20 object classes
  - XML Annotation
- MS COCO 2017
  - common objects in context
  - https://cocodataset.org/#home
  - 80 object classes
  - JSON annotation
  
# II. Selective Search
## Sliding window
- 정의된 크기의 window를 왼쪽 상단부터 오른쪽으로 이동
  - 다양한 크기와 모양의 window 적용
  - Image Scale 변경하여 고정된 크기의 window 적용
## Region Proposal
- sliding window와 차별화된 알고리즘 기반
- 이미지 내 다양한 크기의 object들에 대한 over segmentation
  - size, color, texture, shape등을 기준으로 grouping(ROI : Range of Interest)
- grouping을 반복하여 region proposal 수행
## Non-maximum Suppression(NMS)
> 예측 Bounding box 중에서 정확한 Bounding box를 선택하는 기법
- 수행 단계
  1. confidence score가 기준보다 큰 bounding box만 선택
  2. 겹치는 다른 bounding box와의 IOU 계산
  3. 계산된 IOU Threshold 값이 기준보다 큰 bounding box 제거
  4. 다음 confidence score가 기준보다 큰 bounding box로 이동
  5. 2 ~ 4 반복하여 진행
   
# III. Performance Metrics
## Evaluation Metrics
### IOU(intersection over union)
> IoU = $\frac{겹치는 영역}{예측결과와 실제를 합한 영역}$
- 예측결과가 실제와 얼마나 겹치는가를 평가하는 지표
- 개별객체에 대한 탐지 성공 판단 기준
- Confidence Threshold와 함께 사용
### Confidence Threshold
- IOU가 true Positive를 기준으로
  - PASCAL VOC : 0.5
  - COCO Challenge : 0.5 ~ 0.95(0.05 간격)
- Confidence Threshold에 따라 Precision 과 Recall이 변화함
  
||예측결과 Positive|예측결과 Negative|
|--|--|--|
|실제 Positive|True Positive|False Negative|
|실제 Negative|False Positive|True Negative|
### Precision-Recall Curve
> Recall 값의 변화에 따른 Precision 값의 변화를 곡선으로 표현
- Precision(정밀도) : Positive로 예측한 결과 중 실제 Positive의 비율(탐지결과가 실제 객체와 얼마나 일치하는가)
- Recall(재현율) : 실제 Positive중 Positive로 예측한 비율(실제 객체를 놓치지 않고 얼마나 정확하게 탐지하는가)
- Confidence Threshold를 변경하면서 확인
### Average Precision vs mAP
- Average Precision : Precision-Reccall Curve 선 아래쪽 면적
- mAP(Mean Average Precision) : 여러 객체 AP들의 평균
- FPS(Frame Per Second) : 초당 처리 Frame 수

# IV. Annotation Tools
> Annotation : AI에서 이미지 인식등의 작업을 할 때 이미지에 해석 정보를 추가해 지도 학습 데이터를 만드는 작업, 여러 툴이 있다
## labelimg
## Computer Vision Annotaion Tool(CVAT)

# V. Regions with CNN(R-CNN)
## Object Detection
- 2단계의 detector
  - Stage1 : Region Proposal
  - Stage2 : CNN Detector
## R-CNN
## SPP-Net
## Fast R-CNN
## Faster R-CNN

# VI. Single Shot Detector
## SSD

# VII. You Only Look Once
## YOLO

# VIII. Image Segmentation
## Segmentation
## 

프로젝트에서 확인 해야할 사항 : local, OD