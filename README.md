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



## Setting up the VOT workspace


<pre>
<code>
vot initialize votrgbd2021 --workspace votrgbd2021
</code>
</pre>

## Pytracking installation (windows 10)

https://github.com/visionml/pytracking


!! pytracking/evaluate/local.py 파일에 경로 \ (역슬래시) -> / (슬래시) 수정

!! pytracking내에 networks 폴더 생성후 pytracking/networks에 pre-trained networks 저장

https://drive.google.com/drive/folders/1WVhJqvdu-_JG1U-V0IqfxTUa1SBPnL0O

