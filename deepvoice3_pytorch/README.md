# Deepvoice3 (pytorch)

## Pretrained Model
- [deepvoice3_850k_step](https://drive.google.com/file/d/1pld6kbZQFRqfXeymD0DA4H71cjPv8WtC/view?usp=sharing)


## Requirements
- python >= 3.5
- CUDA >= 8.0
- PyTorch >= v1.0.0
- [nnmnkwii](https://github.com/r9y9/nnmnkwii) >= v0.0.11

## 환경설정
```
git clone https://github.com/r9y9/deepvoice3_pytorch && cd deepvoice3_pytorch
pip install -e ".[bin]"
```
## Preset parameters
### --preset=<json>
- presets/deepvoice3_ljspeech.json : ljspeech dataset에 맞는 하이퍼파라미터가 세팅되어있습니다.

## Preprocess
### Dataset
- LJSpeech (en): https://keithito.com/LJ-Speech-Dataset/

### preprocessing
- 다음을 실행하면 data/ljspeech 폴더가 생성되고 npy 파일과 그에 해당하는 텍스트 정보를 담은 train.txt 파일이 생성됩니다.
```
python preprocess.py --preset=presets/deepvoice3_ljspeech.json ljspeech ~/data/LJSpeech-1.1/ ./data/ljspeech
python preprocess.py ${dataset_name} ${dataset_path} ${out_dir} --preset=<json>
```
위의 dataset 전처리를 통해 train  준비가 되었습니다.

## Training
### train
```
python train.py --preset=presets/deepvoice3_ljspeech.json --data-root=./data/ljspeech/
python train.py --data-root=${data-root} --preset=<json> --hparams="parameters you may want to override"
```
- checkpoint step 마다 savefile(checkpoint_step000000000.pth) 이 checkpoints/ 폴더에 생성됩니다.
- 학습을 중간에 종료하려면 ctrl + c 로 빠져나올 수 있습니다. 진행상황은 checkpoints 폴더에 저장됩니다.

- 학습을 이어서 진행하는 경우, --checkpoints=<checkpoint_file.pth> 를 붙여주시면 됩니다.

## Synthesis from a checkpoint
### synthesis

text_list.txt 파일에 출력을 원하는 문장을 작성한 뒤 다음을 실행하면,

```
python synthesis.py ${checkpoint_path} ${text_list.txt} ${output_dir} --preset=<json>
```

output_dir 폴더에 문장마다의 wav파일, spectrogram 이 생성됩니다.


##From
- [arXiv:1710.07654](https://arxiv.org/abs/1710.07654): Deep Voice 3: Scaling Text-to-Speech with Convolutional Sequence Learning.
- [arXiv:1710.08969](https://arxiv.org/abs/1710.08969): Efficiently Trainable Text-to-Speech System Based on Deep Convolutional Networks with 
- https://github.com/r9y9/deepvoice3_pytorch

