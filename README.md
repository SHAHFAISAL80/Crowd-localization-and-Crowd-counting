Environment

python >=3.6 
pytorch >=1.4
opencv-python >=4.0
scipy >=1.4.0
h5py >=2.10
pillow >=7.0.0
imageio >=1.18
nni >=2.0 (python3 -m pip install --upgrade nni)




Quickly test

git clone https://github.com/dk-liang/FIDTM.git

Download Dataset and Model
Generate FIDT map ground-truth

Generate image file list: python make_npydata.py
Test example:

python test.py --dataset ShanghaiA --pre ./model/ShanghaiA/model_best.pth --gpu_id 0
python test.py --dataset ShanghaiB --pre ./model/ShanghaiB/model_best.pth --gpu_id 1  
python test.py --dataset UCF_QNRF --pre ./model/UCF_QNRF/model_best.pth --gpu_id 2  
python test.py --dataset JHU --pre ./model/JHU/model_best.pth --gpu_id 3  
If you want to generate bounding boxes,

python test.py --test_dataset ShanghaiA --pre model_best.pth  --visual True
(remember to change the dataset path in test.py)  
If you want to test a video,

python video_demo.py --pre model_best.pth  --video_path demo.mp4
(the output video will in ./demo.avi; By default, the video size is reduced by two times for inference. You can change the input size in the video_demo.py)
