# VOT 2021

Preparation history for VOT RGBD-2021 CHALLENGE.


## VOT Toolkit installation

anaconda env

Visual Studio Build Tools 2019: vs_buildtools__942411123.1615829930


<pre>
<code>
pip install git+https://github.com/votchallenge/vot-toolkit-python
</code>
</pre>



## toolkit usage

workspace initialize
<pre>
<code>
vot initialize votrgbd2021 --workspace votrgbd2021
</code>
</pre>


아래부터는 workspace 경로 안에서 실행. 아니면 --workspace workspace_path로 지정해줄 수 있음

tracker test

test는 rgb dummy image에 대해 실행하기 때문에, RGBT 또는 RGBD 트래커는 실행이 안됨. 

test하고싶은 sequence를 지정해주면 가능. --sequence data_path

windows환경에서는 visualize도 안되는것 같음.

<pre>
<code>
vot test tracker-name
</code>
</pre>

tracker evaluate
<pre>
<code>
vot evaluate tracker-name
</code>
</pre>

evaluate result analysis
<pre>
<code>
vot evaluate tracker-name
</code>
</pre>

pack the result

원래 오류가 있었으나, 챌린지 도중 툴킷 새 버전이 나와서 오류 수정됨.

<pre>
<code>
vot pack tracker-name
</code>
</pre>

tracker-name은 trackers.ini파일에서 지정


ex)
<pre>
<code>
[NCC_python]                                        # tracker-name
label=PyNCC                                         # label
protocol=traxpython                                 # vot traxpython protocol. c나 matlab을 쓴다면 바꿔줘야할듯

command = python_ncc                                # py 파일 이름
# Specify a path to trax python wrapper if it is not visible (separate by ; if using multiple paths)
paths = ...\pytracking                              # py 파일이 있는 경로

# Additional environment paths
env_PATH = ...\anaconda3\envs\pytracking;${PATH}    # 가상환경 경로 (일단 했는데 꼭 해야되는지 모르겠음)
</code>
</pre>


## Pytracking installation (windows 10)

https://github.com/visionml/pytracking

### Pytracking

!! pytracking/evaluate/local.py 파일에 경로 \ (역슬래시) -> / (슬래시) 수정

pytracking내에 networks 폴더 생성후 pytracking/networks에 pre-trained networks 저장

https://drive.google.com/drive/folders/1WVhJqvdu-_JG1U-V0IqfxTUa1SBPnL0O

이제 vot toolkit과 연동해서 사용할 수 있음.

### ltr

!! ltr/admin/local.py 파일에 경로 \ (역슬래시) -> / (슬래시) 수정

windows 운영체제에서는 jpeg4py, jpeg-turbo 세팅하기 귀찮아보임. (NOT Recommended!)라고 한 이유를 몸소 겪음

dataset 폴더에 있는 파일에서 image_loader를 opencv_loader로 바꿔줌.


image_loader=opencv_loader

<pre>
<code>
...
def __init__(self, root=None, image_loader=opencv_loader, split=None, seq_ids=None, data_fraction=None):
...
</code>
</pre>
