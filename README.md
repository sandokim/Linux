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

# bash

bash script 에서 다른 script 의 변수, 함수 등을 이용하기 위해서는 source 명령을 사용하게 됩니다.

여러 개의 script 에서 동일한 값을 참조하기 위해서 효율적으로 사용할 수 있습니다.

그러나 script 에서 이유를 알 수 없게 source가 되지 않는 경우가 있습니다.

그 이유는 script 의 첫 줄이 #!/bin/bash 로 되어 있지 않기 때문일 수 있습니다.

<img src="https://github.com/hyeseongkim0/Linux/blob/main/images/bash.PNG" width="100%">

### bash 파일에서 conda activate 가상환경 실행 오류 

<img src="https://github.com/hyeseongkim0/Linux/blob/main/images/sh file.PNG" width="100%">

source: not found 이므로 source를 재설정해야만 가상환경 activate가 제대로 될 것 같다.

<img src="https://github.com/hyeseongkim0/Linux/blob/main/images/source.PNG" width="100%">

해결 방법은 profile 변경 값을 conda shell script 파일에 적용하는 방법이 있다.

```python
source ~/anaconda3/etc/profile.d/conda.sh
```

VScode에서 F1을 누르고 anaconda3/etc/profile.d/conda.sh로 경로를 설정한다.

<img src="https://github.com/hyeseongkim0/Linux/blob/main/images/conda_sh.PNG" width="100%">

이어서 bash파일에서 source와 conda activate(가상환경 실행) 부분도 이에 맞게 수정한다.

<img src="https://github.com/hyeseongkim0/Linux/blob/main/images/conda actiave and source.PNG" width="100%">

source를 bash파일에서 수정했으면 다시 터미널에서 sh 파일이름.sh 명령어로 실행해보자.

---

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
