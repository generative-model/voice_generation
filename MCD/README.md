# Mel-Cepstral Distortion
```.wav``` 파일들의 Mel Cepstral Distortion 찾기

## Dependencies

- librosa
- pyworld
- pysptk

## Installation
Tested on a Python version 3.7 in Windows VM environment
```
conda create -n mel-cep-distortion python=3.6
conda install jupyter
conda install -c conda-forge librosa
pip install pyworld=0.2.11
pip install pysptk=0.1.18
```
## Example
- ```.ipynb``` 에서 usage example이 확인 가능합니다.
- 실행 후 다음과 같은 구조가 됩니다.<br/>
	&nbsp;&nbsp;data<br/>
&nbsp;&nbsp;&nbsp;└─wavs<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└─audio_origin<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└─audio_syn<br/>
&nbsp;&nbsp;&nbsp;└─mceps_numpy<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└─audio_origin<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└─audio_syn<br/>
		
 
## From
- https://github.com/SamuelBroughton/Mel-Cepstral-Distortion
