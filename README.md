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


아래부터는 workspace 경로 안에서 실행. 아니면 --workspace path로 지정해줄 수 있음


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

command = python_ncc                                # .py 파일 이름
# Specify a path to trax python wrapper if it is not visible (separate by ; if using multiple paths)
paths = ...\pytracking                              # .py 파일이 있는 경로

# Additional environment paths
env_PATH = ...\anaconda3\envs\pytracking;${PATH}    # 가상환경 경로 (일단 했는데 꼭 해야되는지 모르겠음)
</code>
</pre>


## Pytracking installation (windows 10)

https://github.com/visionml/pytracking


!! pytracking/evaluate/local.py 파일에 경로 \ (역슬래시) -> / (슬래시) 수정

!! pytracking내에 networks 폴더 생성후 pytracking/networks에 pre-trained networks 저장

https://drive.google.com/drive/folders/1WVhJqvdu-_JG1U-V0IqfxTUa1SBPnL0O

