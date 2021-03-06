# AIFFEL-FREESIA / Model

## π Task
`Satellite Image Semantic Segmentation`
- LV1 : Budiling, Road κ°λ³ κ²μΆ
- LV2 : Building + Road λμ κ²μΆ


<br>

## π©βπ¬ νλ‘μ νΈ μ°Έμ¬μ
- μ΄μ©λ³΅([stereo-weld](https://github.com/stereo-weld))
- μ μν¬([suheeeee](https://github.com/suheeeee))
- μ νλ―Έ([JungHam](https://github.com/JungHam))
- νμ΄μ ([carrot2orange](https://github.com/carrot2orange))
- νμΈν([hongse0331](https://github.com/hongse0331))

<br>

## π νλ‘μ νΈ μ€ν κΈ°λ‘

λ€μ ν­λͺ©λ€μ ν¬ν¨ν©λλ€
- μ€νμ μ¬μ©λ λ°μ΄ν°μ μμ±
- μ€νμ μ¬μ©λ λͺ¨λΈ μ μ
- μ€ν κ²°κ³Ό : weight, tensorboard log

| λ²νΈ | μ€ν μ λͺ© | mIoU, f-score | μ€νμ | λ¨κ³ |
|:---:|:--------|:--------------|:------|:---:|
| E1  | Unet λΉλ© (256,256) | 0.56464, 0.7194 | νμΈν | LV1-Building |
| E2  | Unet λλ‘ (256,256) | 0.56464, 0.7194 | νμΈν | LV1-Road |
| E3  | Unet(256, 256) crop image | 0.7536, 0.8507 | μ μν¬ | LV1-Road |
| E4  | Unet λΉλ©(256,256)resize | 0.49401, 0.65905 | νμ΄μ  | LV1-Building |
| E5  | Unet(256, 256) crop+resizing image | μ μ€λ¨ | μ μν¬ | LV1-Building |
| E6  | Unet(256, 256) CLAHE_clip_limit | 0.6623, 0.7742 | νμΈν | LV1-Building |
| E7  | Unet(256, 256) TIFF | 0.6696, 0.6682 | μ μν¬ | LV1-Building |
| E8  | Unet(256,256) RandomCrop | 0.6916, 0.8091 | μ μν¬ | LV1-Building |
| E9  | Unet λλ‘ (256, 256) | 0.3186, 0.4379 | νμΈν| LV1-Road |
| E10 | Unet(256,256) Road | 0.4928, 0.6272 | μ μν¬ | LV1-Road |
| E11 | Unet(256,256) Road with RGB + OSM Layer | 0.4085, 0.6905 | μ νλ―Έ | LV1-Road |
| E12 | unet(256,256) building, random crop, limited area | 0.8040, 0.8730 | μ΄μ©λ³΅ | LV1-Building |
| E13 | UnetλΉλ©(256,256)resize | 0.48927, 0.65467 | νμ΄μ  | LV1-Building |
| E14 | UnetλΉλ©(256,256)crop | 0.7060, 0.7832 | νμ΄μ  | LV1-Building |
| E15 | E15-one model, unet(256,256),  random crop, limited area |  | μ΄μ©λ³΅ | LV2 |
| E16 | Unet(256,256) RandomCrop+Threshold | 0.7784, 0.8702 | μ μν¬ | LV2 |
| E17 | Unet(256,256) Road | 0.4969, 0.6407 | νμ΄μ  | LV1-Road |
| E18 | Unet_Multiclass | 0.5655, 0.6922 | μ μν¬ | LV2 |
| E19 | Unet_Concatenate_Models | 0.5974, 0.7255 | μ μν¬ | LV2 |
| E23 | E1 μ¬μ€ν | 0.6375 , 0.7761 | μ μν¬ | LV1-Building |
| E24 | E2 μ¬μ€ν | 0.5022, 0.6657 | μ μν¬ | LV1-Road |

<br>

## β° νλ‘μ νΈ μ€νλ³ λͺ©ν
| λ²νΈ | λͺ©ν |
|:---:|:----|
| E1  | (1024x1024x3)->(256x256x3) resizingμ μ μ©ν buildiing segmentation |
| E2  | (1024x1024x3)->(256x256x3) resizingμ μ μ©ν road segmentation |
| E3  | (1024x1024x3)->(25x256x256x3) crop(sliding window)λ₯Ό μ μ©ν buildiing segmentation,<br>μ΅μ  learning rate + opitmizer νμ |
| E4  | E1 κΈ°λ°, model(Unet, Linknet, FPN) λ³ building segmentation μ±λ₯ μ°¨μ΄ νμΈ |
| E5  | (1024x1024x3)->(9x512x512x3)->(9x256x256x3) resizingκ³Ό cropμ μ μ©ν buildiing segmentation |
| E6  | CLAHE μ μ©μ clip_limitμ λ°λ₯Έ μ±λ₯ μ°¨μ΄ νμΈ |
| E7  | E3 κΈ°λ°, TIFF λ°μ΄ν°λ₯Ό νμ©ν buildiing segmentation |
| E8  | (1024x1024x3)->(25x256x256x3) random cropμ μ μ©ν buildiing segmentation,<br>μ΅μ  learning rate + opitmizer νμ |
| E9  | (1024x1024x3)->(25x256x256x3) crop(sliding window)λ₯Ό μ μ©ν road segmentation |
| E10 | E9 κΈ°λ°, PNG+OSM λ°μ΄ν°λ₯Ό νμ©ν road segmentation |
| E11 | road segmentation, λ°μ΄ν°μ κ΅¬μ±(μ±λ:R,G,B,NIR,OMS/threshold)μ λ°λ₯Έ μ±λ₯ μ°¨μ΄ νμΈ |
| E12 | νΉμ΄μΉκ° μ κ±°λ λ°μ΄ν°μμ νμ©ν building segmentation |
| E13 | E1 κΈ°λ°, backborn(mobilenet, mobilenet2, efficientnetb3) λ³ building segmentation μ±λ₯ μ°¨μ΄ νμΈ |
| E14 | E9 κΈ°λ°, model(Unet, Linknet, FPN) λ³ building segmentation μ±λ₯ μ°¨μ΄ νμΈ |
| E15 |  |
| E16 | E7 κΈ°λ°, νΉμ΄μΉ μ κ±°λ₯Ό μν νν°λ§ λ°©μμ λ°λ₯Έ building segmentation μ±λ₯ μ°¨μ΄ νμΈ |
| E17 |  road segmentation, λ°μ΄ν°μ κ΅¬μ±(μ±λ:R,G,B,NIR,OMS/threshold)μ λ°λ₯Έ μ±λ₯ μ°¨μ΄ νμΈ|
| E18 | sementic segmentation multiclass model νμ€νΈ |
| E19 | E16. E11μ ν©μ³ νλμ multiclass segmentation λͺ¨λΈμ μ μ, <br>κΈ°μ‘΄μ νμ΅λ weightλ₯Ό λͺ¨λΈμ λΆλ¬μ inferenceμ μ μ λμ κ΅¬ν |
| E23 | E1 μ¬μ€ν | 
| E24 | E2 μ¬μ€ν |
