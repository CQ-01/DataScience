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
- IOU(intersection over union)
- 
# IV. Annotation Tools
# V. Regions with CNN
# VI. Single Shot Detector
# VII. You Only Look Once
# VIII. Image Segmentation

프로젝트에서 확인 해야할 사항 : local, OD