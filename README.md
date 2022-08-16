I AM NOT FINISHED!!!!!
====

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

## 1.Download an application named Cygwin

🔗 http://www.cygwin.com/

![image](https://user-images.githubusercontent.com/46515944/184843282-f1c646eb-be61-4585-ab8a-28f94747c8e4.png)

[![Image from Gyazo](https://i.gyazo.com/cf94d41e0aa2b41595b5f56af632b6c5.gif)](https://gyazo.com/cf94d41e0aa2b41595b5f56af632b6c5)

![image](https://user-images.githubusercontent.com/46515944/184843405-7398b87f-debd-4613-8067-e0d708c1c0c0.png)




🔱Testing 
====
Enter the command as following to test whether verything is alright.
    python test.py --data data/coco.yaml --img 1280 --batch 32 --conf 0.001 --iou 0.65 --device 0 --cfg cfg/yolor_p6.cfg --weights weights/yolor_p6.pt --name yolor_p6_val

Let me show you how it's like




🔱Prepare your own train data
====
** 1.Installment-Labelimg

First, open your anaconda prompt, then enter in：

    pip install labelimg
    
![image](https://user-images.githubusercontent.com/46515944/178677962-db8a83df-c66d-413c-a70c-2d169ecb1bff.png)

after finished, you can open it by the command：

    labelimg
    
and it looks like that
![image](https://user-images.githubusercontent.com/46515944/178678038-ef99ca39-8ba9-49a5-a825-c3a2260d7bb0.png)

** 2.Operatation-Labelimg

After the application is opend, then open the folder full of pictures.

[![Image from Gyazo](https://i.gyazo.com/ea4752782ba9b9ae41eeb2ac5aa7e3fc.gif)](https://gyazo.com/ea4752782ba9b9ae41eeb2ac5aa7e3fc)

Finally, circle the object you wanna train for detection.

[![Image from Gyazo](https://i.gyazo.com/885b36baa528329e9fca6a32e6234a7c.gif)](https://gyazo.com/885b36baa528329e9fca6a32e6234a7c)

🔱Amend the variables to fit in  your own model
====


🔱Trian the model
====

