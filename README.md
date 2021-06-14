# AIFFEL-FREESIA / Model

## 🏁 Task
`Satellite Image Semantic Segmentation`
- LV1 : Budiling, Road 개별 검출
- LV2 : Building + Road 동시 검출


<br>

## 👩‍🔬 프로젝트 참여자
- 이용복([stereo-weld](https://github.com/stereo-weld))
- 정수희([suheeeee](https://github.com/suheeeee))
- 정혜미([JungHam](https://github.com/JungHam))
- 허운정([carrot2orange](https://github.com/carrot2orange))
- 홍세현([hongse0331](https://github.com/hongse0331))

<br>

## 📑 프로젝트 실험 기록

다음 항목들을 포함합니다
- 실험에 사용된 데이터셋 생성
- 실험에 사용된 모델 정의
- 실험 결과 : weight, tensorboard log

| 번호 | 실험 제목 | mIoU, f-score | 실험자 | 단계 |
|:---:|:--------|:--------------|:------|:---:|
| E1  | Unet 빌딩 (256,256) | 0.56464, 0.7194 | 홍세현 | LV1-Building |
| E2  | Unet 도로 (256,256) | 0.56464, 0.7194 | 홍세현 | LV1-Road |
| E3  | Unet(256, 256) crop image | 0.7536, 0.8507 | 정수희 | LV1-Road |
| E4  | Unet 빌딩(256,256)resize | 0.49401, 0.65905 | 허운정 | LV1-Building |
| E5  | Unet(256, 256) crop+resizing image | 유실됨 | 정수희 | LV1-Building |
| E6  | Unet(256, 256) CLAHE_clip_limit | 0.6623, 0.7742 | 홍세현 | LV1-Building |
| E7  | Unet(256, 256) TIFF | 0.6696, 0.6682 | 정수희 | LV1-Building |
| E8  | Unet(256,256) RandomCrop | 0.6916, 0.8091 | 정수희 | LV1-Building |
| E9  | Unet 도로 (256, 256) | 0.3186, 0.4379 | 홍세현| LV1-Road |
| E10 | Unet(256,256) Road | 0.4928, 0.6272 | 정수희 | LV1-Road |
| E11 | Unet(256,256) Road with RGB + OSM Layer | 0.4085, 0.6905 | 정혜미 | LV1-Road |
| E12 | unet(256,256) building, random crop, limited area | 0.8040, 0.8730 | 이용복 | LV1-Building |
| E13 | Unet빌딩(256,256)resize | 0.48927, 0.65467 | 허운정 | LV1-Building |
| E14 | Unet빌딩(256,256)crop | 0.7060, 0.7832 | 허운정 | LV1-Building |
| E15 | E15-one model, unet(256,256),  random crop, limited area |  | 이용복 | LV2 |
| E16 | Unet(256,256) RandomCrop+Threshold | 0.7784, 0.8702 | 정수희 | LV2 |
| E17 | Unet(256,256) Road |  | 허운정 | LV2 |
| E18 | Unet_Multiclass | 0.5655, 0.6922 | 정수희 | LV2 |
| E19 | Unet_Concatenate_Models | 0.5974, 0.7255 | 정수희 | LV2 |

<br>

## ⛰ 프로젝트 실험별 목표
| 번호 | 목표 |
|:---:|:----|
| E1  | (1024x1024x3)->(256x256x3) resizing을 적용한 buildiing segmentation |
| E2  | (1024x1024x3)->(256x256x3) resizing을 적용한 road segmentation |
| E3  | (1024x1024x3)->(25x256x256x3) crop(sliding window)를 적용한 buildiing segmentation,<br>최적 learning rate + opitmizer 탐색 |
| E4  | E1 기반, model(Unet, Linknet, FPN) 별 building segmentation 성능 차이 확인 |
| E5  | (1024x1024x3)->(9x512x512x3)->(9x256x256x3) resizing과 crop을 적용한 buildiing segmentation |
| E6  | CLAHE 적용시 clip_limit에 따른 성능 차이 확인 |
| E7  | E3 기반, TIFF 데이터를 활용한 buildiing segmentation |
| E8  | (1024x1024x3)->(25x256x256x3) random crop을 적용한 buildiing segmentation,<br>최적 learning rate + opitmizer 탐색 |
| E9  | (1024x1024x3)->(25x256x256x3) crop(sliding window)를 적용한 road segmentation |
| E10 | E9 기반, PNG+OSM 데이터를 활용한 road segmentation |
| E11 | road segmentation, 데이터셋 구성(채널:R,G,B,NIR,OMS/threshold)에 따른 성능 차이 확인 |
| E12 | 특이치가 제거된 데이터셋을 활용한 building segmentation |
| E13 | E1 기반, backborn(mobilenet, mobilenet2, efficientnetb3) 별 building segmentation 성능 차이 확인 |
| E14 | E9 기반, model(Unet, Linknet, FPN) 별 building segmentation 성능 차이 확인 |
| E15 |  |
| E16 | E7 기반, 특이치 제거를 위한 필터링 방식에 따른 building segmentation 성능 차이 확인 |
| E17 |  |
| E18 | sementic segmentation multiclass model 테스트 |
| E19 | E16. E11을 합쳐 하나의 multiclass segmentation 모델을 정의, <br>기존에 학습된 weight를 모델에 불러와 inference의 정상 동작 구현 |

