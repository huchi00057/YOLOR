🔱Download YoloR Github Resources from WongKinYiu
====
🔗 https://github.com/WongKinYiu/yolor

[![Image from Gyazo](https://i.gyazo.com/9e069863952e4fbfb3427975592ae27e.gif)](https://gyazo.com/9e069863952e4fbfb3427975592ae27e)

🔱Do the following Pre-Work
====
## 1.Create a new environment

    conda create -n yolor python=3.9
    conda activate yolor
    cd yolor

## 2.Install Pytorch corresponded to your CUDA version

Enter the cmd to check version.

    nvidia-smi


![image](https://user-images.githubusercontent.com/46515944/184838709-c15d6adb-9829-4ff5-90ef-638a726b29f0.png)

Go through Pytorch to copy installmental command.

🔗https://pytorch.org/get-started/locally/

![image](https://user-images.githubusercontent.com/46515944/184838764-692471ae-0826-4822-9c15-dca76d9e8c6c.png)

After that, you must make sure that your Torch can work.

Enter the cmd to make sure.

    python
    import torch
    torch.cuda.is_available() 
    
If it work successfully, it'll show * True *.

![image](https://user-images.githubusercontent.com/46515944/184838899-23ed741a-6823-4ebf-9356-4457b170a53f.png)

## 3.Install the requirements.txt

    pip install -r requirements.txt

## 4.Downloads the pre-trained weight.

Scroll it until you see the title named "Testing", you'll see a link named yolor_p6.pt. Just download it!!

[![Image from Gyazo](https://i.gyazo.com/039fc4f3b616ec5c74ff7215a67fcdbc.gif)](https://gyazo.com/039fc4f3b616ec5c74ff7215a67fcdbc)

🔱Prepare data for testing as the following step
====
Because my service is Windows, not Ubuntu, we need to execute it like below.

If you master yolor, you can skip this step. The main purpose in the step is to make sure the sucess of necessiry installment.

## Open scripts/get_coco.sh with Git for Windows

![image](https://user-images.githubusercontent.com/46515944/185073630-e8ba336c-8b00-413f-b0f4-871fd2b9ec9a.png)

 If you don't have Git, you can download from the link.
 
🔗 https://git-scm.com/downloads

After you opened it, it'll like this.

![image](https://user-images.githubusercontent.com/46515944/185073897-55040ee3-1560-4778-bef1-500345cfeb3a.png)

Then, your yolor/scripts will full of zips, including test2017, train2017, val2017, and cco2017label.

![image](https://user-images.githubusercontent.com/46515944/185074032-93e2c5f4-b5d6-403e-a052-819573708ae3.png)

## Unzip and move them.

You can move them to anywhere, but onething must make sure that their paths are same with yolor/data/coco.yaml.

![image](https://user-images.githubusercontent.com/46515944/185074818-d8c05023-d217-4fef-bdfb-81dce54ebc88.png)

🔱Testing 
====
Enter the command as following to test whether verything is alright.

        python test.py --data data/coco.yaml --img 1280 --batch 32 --conf 0.001 --iou 0.65 --device 0 --cfg cfg/yolor_p6.cfg --weights weights/yolor_p6.pt --name yolor_p6_val

Let me show you how it's like



🔱Prepare your own train data
====
## 1.Installment-Labelimg

First, open your anaconda prompt, then enter in：

    pip install labelimg
    
![image](https://user-images.githubusercontent.com/46515944/178677962-db8a83df-c66d-413c-a70c-2d169ecb1bff.png)

after finished, you can open it by the command：

    labelimg
    
and it looks like that
![image](https://user-images.githubusercontent.com/46515944/178678038-ef99ca39-8ba9-49a5-a825-c3a2260d7bb0.png)

## 2.Operatation-Labelimg

After the application is opend, then open the folder full of pictures.

[![Image from Gyazo](https://i.gyazo.com/ea4752782ba9b9ae41eeb2ac5aa7e3fc.gif)](https://gyazo.com/ea4752782ba9b9ae41eeb2ac5aa7e3fc)

Finally, circle the object you wanna train for detection.

![5ea2cfa6f6463a4af9846d6c4a2d9900](https://user-images.githubusercontent.com/46515944/185072775-e3370799-ca4c-48a4-9d0d-cb13d0ca8f63.gif)

🔱Amend the variables to fit in  your own model
====
## Put your own data to yolor/data/data

![image](https://user-images.githubusercontent.com/46515944/185083001-cdfa9d20-ee5e-48dc-8f98-3492415dfe1b.png)


## Create a .cfg file in yolor/cfg

You can copy if from any .cfg file and amend some variables.

Like me, i chose yolor_p6.cfg.

And considering my Ram, so justify batch, subdivision, width, height, learning_rate, max_batches, steps.

> steps = (0.8 * max_batches ,0.9 * max_batches)

![image](https://user-images.githubusercontent.com/46515944/185080939-c9947b88-7b2e-4cc9-949a-3fc6a98a3866.png)

> filters = (classes + 5) * 3
> Search "[yolo]", and change the filters before "yolo", like bellowing picture shows.

![image](https://user-images.githubusercontent.com/46515944/185082036-4c314727-95cf-4dc6-93ea-2277e1854c5a.png)

It approximately in line 1569,1573,11577,1581,1605,1649,1693,1737.

![image](https://user-images.githubusercontent.com/46515944/185081698-da88c507-790f-4943-aa94-885967214467.png)
![image](https://user-images.githubusercontent.com/46515944/185081762-a487cea8-3075-4a1b-8ca1-ed43ab645d16.png)
![image](https://user-images.githubusercontent.com/46515944/185081786-8ff02f27-8634-4417-b8af-7af2635e3bc0.png)
![image](https://user-images.githubusercontent.com/46515944/185081816-98fb0229-0579-4f5c-943d-ce14d6c85e6e.png)
![image](https://user-images.githubusercontent.com/46515944/185081865-78f1e468-8cb9-40e0-99e8-2719e8588c4d.png)




## Create a .yaml file in yolor/data

It record the paths of your data handled in the last step, the number of classes, and classes' names.

![image](https://user-images.githubusercontent.com/46515944/185079295-65fd96e0-2d01-49a5-b53c-c72a10b7957a.png)

⚠ Type is .yaml

## Create a .names file in yolor/data

Store your own classes in lines like yolov4.

![image](https://user-images.githubusercontent.com/46515944/185078956-b0d2f0fe-d4c9-4248-96b8-9c3581af0153.png)

⚠ Type is .names

![image](https://user-images.githubusercontent.com/46515944/185079721-5beb182f-d437-4c8a-a160-5c79104ab8a3.png)


🔱Trian the model
====
## Train a new model

        python train.py --batch-size 4 --img 640 640 --data data/your.yaml --cfg cfg/your.cfg --epochs 300

If it break accidently, you don't need to train it from the start. Let me show you

## Train from the middle

        python train.py --batch-size 4 --img 640 640 --data data/your.yaml --cfg cfg/your.cfg --weights runs/train/yolor_p6/weights/best.pt --epochs 300



## Check and run your model

> After training ,your weight will store in yolor/runs/train/yolor_???

## Run it and TAKE A BREAK !!

> Test in Videos

        python detect.py --source path/your_video--cfg cfg/your.cfg --weights runs/train/your_best.pt 

> Test in Images

        python detect.py --source path/image/pic.jpg --cfg cfg/your.cfg --weights runs/train/your_best.pt 
        
Besides, you can run images for not just one. In other words, the model can detect a folder full of images one time.

        python detect.py --source path/img_folder --cfg cfg/your.cfg --weights runs/train/your_best.pt 
