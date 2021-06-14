# AIFFEL-FREESIA / Model

### 👩‍🔬 프로젝트 실험 참여자
- 이용복([stereo-weld](https://github.com/stereo-weld))
- 정수희([suheeeee](https://github.com/suheeeee))
- 정혜미([JungHam](https://github.com/JungHam))
- 허운정([carrot2orange](https://github.com/carrot2orange))
- 홍세현([hongse0331](https://github.com/hongse0331))

### 📑 프로젝트 실험 기록

다음 항목들을 포함합니다
- 실험에 사용된 데이터셋 생성
- 실험에 사용된 모델 정의
- 실험 결과 : weight, tensorboard log

| 번호 | 실험 제목 | mIoU, f-score | 실험자 | 실험 날짜 | 단계 |
|:---:|:--------|:--------------|:------|:--------|:---:|
| E1  | Unet 빌딩 (256,256) | 0.56464, 0.7194 | 홍세현 | 2021-05-21 | LV1-Building |
| E2  | Unet 도로 (256,256) | 0.56464, 0.7194 | 홍세현 | 2021-05-21 | LV1-Road |
| E3  | Unet(256, 256) crop image | 0.7536, 0.8507 | 정수희 | 2021-05-24 | LV1-Road |
| E4  | Unet 빌딩(256,256)resize | 0.49401, 0.65905 | 허운정 | 2021-05-25 | LV1-Building |
| E5  | Unet(256, 256) crop+resizing image | 유실됨 | 정수희 | 2021-06-03 | LV1-Building |
| E6  | Unet(256, 256) CLAHE_clip_limit | 0.6623, 0.7742 | 홍세현 | - | LV1-Building |
| E7  | Unet(256, 256) TIFF | 0.6696, 0.6682 | 정수희 | 2021-06-08 | LV1-Building |
| E8  | Unet(256,256) RandomCrop | 0.6916, 0.8091 | 정수희 | 2021-06-04 | LV1-Building |
| E9  | Unet 도로 (256, 256) | 0.3186, 0.4379 | 홍세현| 2021-06-04 | LV1-Road |
| E10 | Unet(256,256) Road | 0.4928, 0.6272 | 정수희 | 2021-06-06 | LV1-Road |
| E11 | Unet(256,256) Road with RGB + OSM Layer | 0.4085, 0.6905 | 정혜미 | 2021-06-07 | LV1-Road |
| E12 | unet(256,256) building, random crop, limited area | 0.8040, 0.8730 | 이용복 | 2021-06-08 | LV1-Building |
| E13 | Unet빌딩(256,256)resize | 0.48927, 0.65467 | 허운정 | 2021-06-03 | LV1-Building |
| E14 | Unet빌딩(256,256)crop | 0.7060, 0.7832 | 허운정 | 2021-06-10 | LV1-Building |
| E15 | E15-one model, unet(256,256),  random crop, limited area |  | 이용복 | 2021-06-11 | LV2 |
| E16 | Unet(256,256) RandomCrop+Threshold | 0.7784, 0.8702 | 정수희 | 2021-06-11 | LV2 |
| E17 | Unet(256,256) Road |  | 허운정 | 2021-06-14 | LV2 |
| E18 | Unet_Multiclass | 0.5655, 0.6922 | 정수희 | 2021-06-14 | LV2 |
| E19 | Unet_Concatenate_Models | 0.5974, 0.7255 | 정수희 | 2021-06-14 | LV2 |
