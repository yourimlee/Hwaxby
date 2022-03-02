# __TTS(Text To Speech) Model__

## __Glow-TTS & Hifi-GAN__

### __Glow-TTS__

![glow-tts](https://user-images.githubusercontent.com/59776953/155987243-231892f6-7604-4c8d-a6ad-a7cd150f8ac9.png)

- 텍스트를 Mel Spectrogram으로 변환하는 Encoder, Decoder 과정
- 플로우 기반 생성 모델과 동적 프로그래밍 속성을 활용한 정렬 모델이 필요 없는 빠른 합성
- Tacotron2와 비슷한 품질의 음성을 약 15배 더 빠르게 합성


### Hifi-GAN
![hifi-gan](https://user-images.githubusercontent.com/59776953/155987289-cb628410-ac87-4b1c-a903-23eae8e0c576.jpeg)
- Mel Spectrogram으로부터 음성을 합성하는 Vocoder 과정
- GAN 모델의 경우, 합성한 음성의 품질이 다소 떨어지지만 속도와 파라미터 개수 부분에서 부분적으로 개선
- HiFi-GAN은 높은 MOS값 구현

## Tacotron (attention-based)
<img width="838" alt="tacotron_model" src="https://user-images.githubusercontent.com/59776953/156309033-c82302f9-44dc-4698-b846-8a02be49c1d7.png">

- 문자열을 입력받아서 그에 해당하는 Mel spectrogram을 프레임 단위로 출력하는 Encoder-Decoder 형식의 모델
- audio-text pair만 있으면 학습이 가능한 end-to-end 모델
- auto-regressive한 방식으로 frame별로 생성하기 때문에 느리다는 단점

### Datasets
 - 2시간 30분 분량의 음성 데이터
 - 음성 데이터를 전사한 script

### Prerequisites
- __Glow-tts & Hifi-GAN__
	- [Requirements.txt](https://github.com/sce-tts/TTS/blob/sce-tts/requirements.txt) 
- __Tacotron__
	- docker
	- Tensorflow 1.3
	- Python 3.6+

### Train a model
<img width="773" alt="model-architecture" src="https://user-images.githubusercontent.com/59776953/155987786-bd9f81a1-220f-4fd0-bba0-f021441efa18.png">

### Results
- [synthesize audio](https://github.com/2hwayoung/Hwaxby/blob/main/Model/output.wav)

### References
- [SCE-TTS : 내 목소리로 TTS 만들기](https://github.com/sce-tts/sce-tts.github.io)
- [multi-speaker-tacotron-speaker](https://github.com/carpedm20/multi-Speaker-tacotron-tensorflow)