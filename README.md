To run this, you need a GPU in your system.
Make sure you have the correct Python version which supports Pytorch, I am running Python 3.10
Make sure you have all the requirements in your system, if not run the below command
pip install -r requirements.txt

Now to train the model, run this command


python train.py --workers 8 --device 0 --batch-size 16 --data data/data.yaml --img 640 640
--cfg cfg/training/yolov7.yaml --weights '' --name yolov7 --hyp data/hyp.scratch.p5.yaml --epochs 500

This will produce a file named 'runs' which will have the weights folder
In the weights folder, best.pt is the one we use for detect.py

python detect.py --weights best.pt --conf 0.25 --source bonefracture/test/images

This will produce output images with the detection of fracture in the X-ray
