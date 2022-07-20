# Linux

```python
sudo apt-get install htop
htop
sudo apt-get install git
git clone https://github.com/facebook/react.git

mkdir why; cd why # 세미콜론을 본 다음에 cd why 명령어가 실행된다.

ls --help | grep sort # 프로그램과 프로그램을 파이프로 연결할 수 있다.

ps aux | grep apache # apache라는 텍스트가 포함되어 있는 것만 화면에 가져온다.

```
### bash
bash는 shell 중에서 shell이라는 카테고리에 속하는 구체적인 제품 중에 하나인 bash라고 하는 프로그램이다.
```python
echo $0
-bash # bash라는 shell이 동작하고 있는 상태이고 내가 입력하고 있는 명령은 bash를 통해서 커널로 전달되고 있고 커널에서 만들어진 결과는 bash를 통해서 우리의 메인화면에 표시되고 있는 것읻.
```

### zsh vs bash
zshell을 통해서 kernel에 접근

bash를 통해서 kernel에 접근

사용자의 편의에 맞게 shell을 선택하여 사용한다.

### Shell Script
순차적으로 실행해야하는 명령들의 스크립트를 미리 저장

Shell Script example

```python
#!/bin/bash
```

명령들이 bin dir의 bash라 프로그램을 통해 실행된다.

cpu를 클릭하면 cpu를 기준으로 정렬됨.

Time은 프로그램이 실행된 시간

Command는 어떤 명령으로 프로그램이 실행되었는가

Mem: 물리적인 메모리의 크기, 프로세스가 물리적으로 얼마나 메모리를 쓰고 있는가에 대한 퍼센트

RES: 실제적인 메모리의 사용량

코어가 4개인 1,2,3,4 각각의 cpu가 얼마나 바쁜지

<img src="https://github.com/sandokim/Linux/blob/main/images/cpu 1234.jpg" width="100%">

필요한 실행파일의 위치를 찾는 방법
```python
echo $PATH
```

어떤 명령어를 실행했을때 그 명령어가 어디에 위치하고 있는가라는 것을 지정해서 여러분이 명령을 실행할 때마다 그 명령에 전체 경로를 적지 않아도 되는 아주 편리한 기능인 $PATH라는 변수 (환경변수)

```python
cd ~  # 홈디렉터리로 change
cd /  # root 디렉터리로 change
cd .. # 상위 디렉터리로 change
./ # 현재 디렉터리
. # 현재 디렉터리
.. # 상위 디렉터리

패키지 설명 출력
man chmod
chmod --help

ls
ls -al # 숨김파일까지 모두 출력, 숨김파일은 .으로 시작한다.
```

### Linux - startup script bashrc
셀에 접속했을 때, 셀이 시작됐을 때 어떤 특정한 명령어가 자동으로 실행되도록 하는 방법

홈디렉터리로 가고 .bashrc라는 파일을 만들면 셸에 접속했을 때, 셸이 실행될 때 셸이라는 프로그램이 .bashrc라고 하는 파일 안에 있는 코드를 실행하도록 약속되어 있다. bash라는 문법에 따라 코드를 작성한다.
```python
cd ~
bash
exit
```
```python
echo $PATH
```
PATH의 값을 변경한다든지, 그런 것들을 스타트업 스크립트 .bashrc라고하는 스크립트 안에다가 PATH와 관련된 코드를 작성하면 셸이 시작될 때 그 부분이 바뀐다.

$표시가 있으면 이 사용자가 현재 일반유저라는 뜻이다.
#표시가 있으면 이 사용자가 현재 슈퍼유저라는 뜻이다.

```python
/root # root사용자의 root 디렉터리
pwd # present working directory
```

permission

<img src="https://github.com/sandokim/Linux/blob/main/images/permission rwx.jpg" width="100%">

bash라는 프로그램을 실행시켜서 그 프로그램에게 hi-machine.sh(.sh파일)를 해석해서 실행하라하면 실행이 된다.

/bin/bash # 어떤 특정 프로그램(해석기, 파서)을 통해서 어떤 특정한 프로그래밍 언어를 실행시키는 것은 아무런 제약이 없다.
 
./ 현재 디렉터리에서 hi-machine.sh 파일을 실행시키고 싶다면 파일에게 실행권한을 줘야한다. 그때 사용하는 것이 execute.

ls -l 로 owner, group, others의 읽기,쓰기,실행(rwx) 권한을 확인

<img src="https://github.com/sandokim/Linux/blob/main/images/router.jpg" width="100%">

웹브라우저 입장에서 자신이 설치돼 있는 그 컴퓨터에 설치되어 있는 웹 서버에 접속할 때 ip addr 명령어로 ip를 알아낼 수도 있지만 그걸 몰라도 언제나
127.0.0.1 이나 localhost라는 ip, 도메인네임을 쓰게 되면 접속할 수 있다.

<img src="https://github.com/sandokim/Linux/blob/main/images/WB_WS.jpg" width="100%">

SSH

<img src="https://github.com/sandokim/Linux/blob/main/images/SSH.jpg" width="100%">

# 원격 ssh 연결

<img src="https://github.com/sandokim/Linux/blob/main/images/원격ssh config file port.png" width="40%">

# Linux

MobaXterm install

tmux --> 별도로 터미널 관리 --> 컴퓨터가 꺼져도 터미널은 유지됩니다. [[Linux] tmux 사용법](https://velog.io/@ur-luella/tmux-%EC%82%AC%EC%9A%A9%EB%B2%95)

```python
tmux new -s <session_name>
tmux kill-session -t <session_name>
tmux ls
tmux attach -t <session_name or session_number>

Ctrl+b c Create a new window (with shell)
Ctrl+b , Rename the current window
Ctrl+b x Close the current pane

Ctrl+b w Choose window from a list
Ctrl+b 0 Switch to window 0 (by number )
Ctrl+b % Split current pane horizontally into two panes
Ctrl+b " Split current pane vertically into two panes
Ctrl+b o Go to the next pane
Ctrl+b ; Toggle between the current and previous pane
```

#### Linux 디스크 다 찼을 때 폴더별 용량 확인법

du -h --max-depth=1

#### GPU setting

<img src="https://github.com/hyeseongkim0/Linux/blob/main/images/gpu setting.PNG" width="100%">

#### GPU memory가 꽉 차있을 떄 kill

[리눅스 터미널에서 딥러닝 학습 강제중단했을때 GPU에 남은 메모리 정리하는 방법](https://pulsar-kkaturi.tistory.com/entry/%EB%A6%AC%EB%88%85%EC%8A%A4-%ED%84%B0%EB%AF%B8%EB%84%90%EC%97%90%EC%84%9C-%EB%94%A5%EB%9F%AC%EB%8B%9D-%ED%95%99%EC%8A%B5-%EA%B0%95%EC%A0%9C-%EC%A4%91%EB%8B%A8%ED%96%88%EC%9D%84%EB%95%8C-GPU%EC%97%90-%EB%82%A8%EC%9D%80-%EB%A9%94%EB%AA%A8%EB%A6%AC-%EC%A0%95%EB%A6%AC%ED%95%98%EB%8A%94-%EB%B0%A9%EB%B2%95)


### cuda version check

```python
nvcc -v
```

### 가상환경 세팅 environment.yml

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

해보니 문제가 not found source가 제일 처음 문제였고, bash file에서는 source 명령어 대신 .을 써서해야하는 경우가 있다.

아래처럼 따라서 설정하니 문제가 해결되었다.

<img src="https://github.com/hyeseongkim0/Linux/blob/main/images/not found source.PNG" width="60%">

<img src="https://github.com/hyeseongkim0/Linux/blob/main/images/source dot.PNG" width="60%">

<img src="https://github.com/hyeseongkim0/Linux/blob/main/images/source instead dot.PNG" width="80%">

---

[How to write a bash script](https://www.youtube.com/watch?v=F-gskSl4pwQ)

<img src="https://github.com/hyeseongkim0/Linux/blob/main/images/cyclegan_bashfile.PNG" width="120%">


#### model.sh file?
Check [here](https://github.com/junyanz/pytorch-CycleGAN-and-pix2pix/blob/master/scripts/download_pix2pix_model.sh#L3) for all the available pix2pix models. For example, if you would like to download label2photo model on the Facades dataset,
