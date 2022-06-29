# Linux

가상환경 세팅 environment.yml

[Conda 가상환경 그대로 옮기기](https://velog.io/@sheoyonj/Conda-%EA%B0%80%EC%83%81%ED%99%98%EA%B2%BD-%EA%B7%B8%EB%8C%80%EB%A1%9C-%EC%98%AE%EA%B8%B0%EA%B8%B0)

### 가상환경 ymal파일로 만들기

environment.yml 형식은 아래와 같습니다.

```python
name: pytorch-CycleGAN-and-pix2pix
channels:
- pytorch
- defaults
dependencies:
- python=3.6
- pytorch=1.4.0
- scipy
- pip
- pip:
  - dominate==2.4.0
  - torchvision==0.5.0
  - Pillow==6.1.0
  - numpy==1.16.4
  - visdom==0.1.8
```

environment.yml 파일로 가상환경 생성

```python
conda env create --file environment.yml 
```

가상환경 삭제

```python
conda env remove --n 가상환경이름 
```


MobaXterm install

tmux --> 별도로 터미널 관리 --> 컴퓨터가 꺼져도 터미널은 유지됩니다. [[Linux] tmux 사용법](https://velog.io/@ur-luella/tmux-%EC%82%AC%EC%9A%A9%EB%B2%95)

#### Linux 디스크 다 찼을 때 폴더별 용량 확인법

du -h --max-depth=1

#### GPU setting

<img src="https://github.com/hyeseongkim0/Linux/blob/main/images/gpu setting.PNG" width="100%">

#### GPU memory가 꽉 차있을 떄 kill

[리눅스 터미널에서 딥러닝 학습 강제중단했을때 GPU에 남은 메모리 정리하는 방법](https://pulsar-kkaturi.tistory.com/entry/%EB%A6%AC%EB%88%85%EC%8A%A4-%ED%84%B0%EB%AF%B8%EB%84%90%EC%97%90%EC%84%9C-%EB%94%A5%EB%9F%AC%EB%8B%9D-%ED%95%99%EC%8A%B5-%EA%B0%95%EC%A0%9C-%EC%A4%91%EB%8B%A8%ED%96%88%EC%9D%84%EB%95%8C-GPU%EC%97%90-%EB%82%A8%EC%9D%80-%EB%A9%94%EB%AA%A8%EB%A6%AC-%EC%A0%95%EB%A6%AC%ED%95%98%EB%8A%94-%EB%B0%A9%EB%B2%95)

[How to write a bash script](https://www.youtube.com/watch?v=F-gskSl4pwQ)

<img src="https://github.com/hyeseongkim0/Linux/blob/main/images/cyclegan_bashfile.PNG" width="120%">


#### model.sh file?
Check [here](https://github.com/junyanz/pytorch-CycleGAN-and-pix2pix/blob/master/scripts/download_pix2pix_model.sh#L3) for all the available pix2pix models. For example, if you would like to download label2photo model on the Facades dataset,
