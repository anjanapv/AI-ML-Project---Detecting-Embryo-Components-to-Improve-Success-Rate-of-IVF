# AI-ML-Project-Embryo-Analysis-to-Improve-Success-Rate-of-IVF


**This project is a recreation of STORK repository [Github Link to STORK](https://github.com/ih-lab/STORK) which is used for embryo classification.**


![-----------------------------------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)

<!-- TABLE OF CONTENTS -->
<h2 id="table-of-contents"> :book: Table of Contents</h2>

<details open="open"><summary>Table of Contents</summary>  

1.[About the Project](#ATP)  
2.[Prerequisites](#Prerequisites)  
3.[Dataset](#Dataset)  
4.[Data_Pipeline](#Data_Pipeline)  
5.[Methodology](#Methodology)   
6.[Results and Discussion](#Results_and_Discussion)   
7.[References](#References)   
8.[Contributors](#Contributors)  
9.[Steps To Follow](#Steps_To_Follow)  
</details>


<a name="ATP"/>

<!-- ABOUT THE PROJECT -->
<h2 id="about-the-project"> :pencil: About The Project</h2>

<p align="justify">
Infertility is defined as a clinical condition of inability to conceive or get pregnant after one year or longer of unprotected sex. IVF stands for In vitro fertilization. It is a type of assistive reproductive technology (ART) for infertility treatment and surrogacy. Surrogacy is an arrangement where another woman agrees to labour deliver for another person where pregnancy is medically impossible. Approximately 16% which is 1 in 6 couples in Canada experience infertility (UCLA Health, 2020). This number has doubled since the 1980’s. Apart from the emotional trauma a couple goes through during their journey of infertility they have to invest a lot of time and money into the IVF process.
</p>

<p align="justify">
The below figure explains the whole IVF process step by step. IVF involves many steps, and each cycle would take an average duration of 6 to 8 weeks. At first the individual would undergo an initial consultation and testing with an infertility specialist and would be prescribed medication for ovarian stimulation in which the ovary is stimulated to produce multiple healthy eggs. Then the doctor retrieves the eggs from the woman’s ovary. The retrieved eggs are fertilized with the sperm from the semen sample of a partner or a sperm donor in a culture medium in a laboratory. The fertilized egg undergoes embryo culture where the fertilized eggs are allowed to grow in an artificial medium (incubator) under supervision. After 3 – 5 days once the embryo reaches the blastocyst stage, the best embryos are selected by the embryologists based on the morphological attributes and are transferred into the woman’s uterus. After two weeks of embryo transfer the couple undergoes for a pregnancy test and the success of the IVF process is determined.
</p>

<p align="center" width="100%">
    <img width="100%" src="https://www.pfcla.com/hubfs/infographic-1.svg"> 
</p>

<p align="justify">
Standard morphological assessment of the embryo by the embryologist has always been the major tool for selecting the best embryo for transfer.One cycle of an IVF process takes 6 to 8 weeks. On an average 3 IVF cycles is found to be clinically effective. The average cost of one round of IVF is estimated to be $15000, with a success rate of less than 50% per embryo transfer.Manual assessment may result in human error based on their experience, intuition and expertise. Multiple viable blastocysts were transferred to increase the chances of pregnancy, but this would result in multiple pregnancies and gestational complications in the mothers and babies. Therefore, identifying the single best viable blastocyst is recommended which would reduce the number of cycles administered and eliminate multiple pregnancies and other related issues. Our project aims at building a supervised learning classification model to classify the embryo based on their quality into good or bad thereby eliminating the factor of human error and the need for multiple cycles.
</p>

![-----------------------------------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)

<a name="Prerequisites"/>

<!-- PREREQUISITES -->
<h2 id="prerequisites"> :fork_and_knife: Prerequisites</h2>

[![made-with-python](https://img.shields.io/badge/Made%20with-Python-1f425f.svg)](https://www.python.org/) <br>

<!--This project is written in Python programming language. <br>-->
The following open source packages are used in this project:
* Numpy
* TensorFlow
* Keras
* dataset_utils
* math
* os
* random
* sys
* matplotlib

![-----------------------------------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)

<a name="Dataset"/>

<!-- DATASET -->
<h2 id="dataset"> :open_file_folder: Dataset</h2>

<p align="justify">
Source : STORK Framework.
Training Images : Good 42, Poor 42
Test Images: 14
This image dataset is publicly available and taken from the GitHub repository of STOCK, these images of human embryos were obtained from the Centre for Reproductive Medicine at Weill Cornell Medicine. There are total of 98 images. This image dataset was already in jpg format.
</p>

<p align="center">
  <img width="70%" src=Docs/dataset.jpg>
</p>

![-----------------------------------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)

<a name="Data_Pipeline"/>

<h2 id="Data_Pipeline"> :dart: Data Pipeline</h2>

<p align="center">
  <img width="100%" src=Docs/pipeline.png>
</p>

![-----------------------------------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)

<a name="Methodology"/>

<h2 id="Methodology"> :scroll: Methodology</h2>

<p align="justify">
    
A Deep Neural Network (DNN) is used for embryo image analysis based on Google’s Inception-V1 architecture. The STORK repository had multiple pre-trained models out of which Inception V1 is best suitable for image classification. We have used STORK framework to predict blastocyst quality into good or poor.
This study included a total of 98 blastocyst images, and the data is divided into two parts, 85% of the images (84) are used for training the model and the remaining 15% images (14) are used for testing the trained model.
    
</p>

![-----------------------------------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)


<a name="Results_and_Discussion"/>

<h2 id="Results_and_Discussion"> :mag: Results and Discussion</h2>

<p align="justify">
Deep neural network has high accuracy in classification of human embryo images. We have used pre trained Inception V1 model algorithm to train the images. The basic inception V1 has four parallel layers of 1X1 convolution, 3X3 convolution, 5X5 convolution and 3X3 max pooling.
By employing our model, we could select the best viable embryo for transferring to the uterus. With the current IVF process, it is preferred to go for 3 cycles where 1 cycle costs up to $15,000 and 6-8 weeks. If our model could classify the embryos as good and poor there is a possibility of reducing the number of cycles if IVF.
So, to classify the embryo, we leveraged a deep neural network to identify the quality of each embryo and we also used a stork framework, to find the quality of the embryo images. We have classified these embryo images into two, good and poor, by using the stork model. For testing the data, our model gives an accuracy of 100% from the total of 14 images, 14 were predicted correctly. One of our limitations is that while training we got an accuracy of 100% for training purposes, due to the limited number of datasets. Also, our model will go with the higher precision rate for true negative, where the poor embryo is predicted to be poor. We have developed a web page for the data product to Integrate the model, where an embryo image can be uploaded and check whether the probability of that image is good or poor. Which can be used by a common person to check the quality (probability) of the uploaded embryo as good or poor.
</p>


![-----------------------------------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)

<a name="References"/>

<h2 id="references"> :books: References</h2>

1. A. Muhammad, H. Adnan, C. Jiho, and R. P. Kang, “Detecting Blastocyst Components by Artificial Intelligence for Human Embryological Analysis to Improve Success Rate of In Vitro Fertilization.” https://www.ncbi.nlm.nih.gov/pmc/articles/PMC8877842/ 

2. A. Kirillova et al., “Should we transfer poor quality embryos?,” Fertil. Res. Pract., vol. 6, no. 1, pp. 1–7, 2020, doi: 10.1186/s40738-020-00072-5
3. P. F. Centre, “From consultation to embryo transfer.” https://www.pfcla.com/services/in-vitro-fertilization/overview
4. STORK GitHub https://github.com/ih-lab/STORK/tree/master/scripts


![---------------------------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)

<a name="Contributors"/>

<h2 id="contributors"> :writing_hand: Contributors</h2>

<p align="justify">
  :mortar_board: <i>All participants in this project are post graduate students of the Data Analytics for Business course</a> <b> @ </b> <a href="https://www.stclaircollege.ca/">St. Clair College</a></i>
  
  :girl: <b>Anjana Padikkal Veetil</b> <br>
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Email: <a>AP202@myscc.ca</a> <br>
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp; GitHub: <a href="https://github.com/anjanapv">@anjanapv</a> <br>
  
  :woman_in_tuxedo: <b>Nobin Ann Mathew</b> <br>
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Email: <a>NM91@myscc.ca</a> <br>
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp; GitHub: <a href="https://github.com/NobinMath">@nobinmathew</a> <br>

  :man: <b>Venkata Bhagya Teja Maridu</b> <br>
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Email: <a>VM49@myscc.ca</a> <br>
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp; GitHub: <a href="https://github.com/tejamaridu">@teja</a> <br>

  :boy: <b>Santosh Kumar Kantimahanti Lakshmi</b> <br>
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Email: <a>SK602@myscc.ca</a> <br>
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp; GitHub: <a href="https://github.com/santoshkumarklv">@santosh</a> <br>
  
  :man_beard: <b>Amal Mathew</b> <br>
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Email: <a>AM252@myscc.ca</a> <br>
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp; GitHub: <a href="https://github.com/Amalmathew5">@amal</a> <br>
</p>

![-----------------------------------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)

<a name="Steps_To_Follow"/>

<h2 id="Steps_To_Follow"> :arrow_right: Steps To Follow</h2>

<p align="justify">
To run the algorithm please follow these steps:  
</p>

<p align="justify">
1. Install the TensorFlow(version 1.15). Follow the instruction from here: https://www.tensorflow.org/install/
</p>

<p align="justify">
2. Pre-trained Models of CNN architectures should be downloaded from the "Pre-trained Models" part of https://github.com/wenwei202/terngrad/tree/master/slim#pre-trained-models and be located in your machine (e.g. AI-ML-Project-Embryo-Analysis-to-Improve-Success-Rate-of-IVF/scripts/slim/run/checkpoint). The files for pre-trained models should be available under the folder named "Checkpoint".
</p>

<p align="justify">
3. _NUM_CLASSES should be set as 2 ( as we are classifying the embryo into good or poor ) in embryo.py python file (this script is located in AI-ML-Project-Embryo-Analysis-to-Improve-Success-Rate-of-IVF/scripts/slim/datasets).
</p>

<p align="justify">
4. Run the convert.py (it is located in the "AI-ML-Project-Embryo-Analysis-to-Improve-Success-Rate-of-IVF/scripts" directory) to allocate the suitable percentage of images to train and validation sets. The convert.py needs three arguments: the address of images for training, the address of where the result will be located, and the percentage of validation images for the training step:  


```
$ python convert.py ../Images/train process/ 0

```
- Keep the percentage of validation images as 0 because we set 15% for validation inside the code.

- It will save converted .tf files in the "process" directory.
</p>

<p align="justify">
5. The Inception-V1 architecture should be run on the Train images from the "AI-ML-Project-Embryo-Analysis-to-Improve-Success-Rate-of-IVF/scripts/slim" directory. First go to the following directory: AI-ML-Project-Embryo-Analysis-to-Improve-Success-Rate-of-IVF/scripts/slim. Then open load_inception_v1.sh located in "run/" directory and edit PRETRAINED_CHECKPOINT_DIR,TRAIN_DIR, and DATASET_DIR addresses. See the load_inception_v1.sh, for instance. 
Then, run the following command in shell script:

```
$ ./run/load_inception_v1.sh

```
- If your system supports linux commands run load_inception_v1.sh otherwise run the below python file.

```
PRETRAINED_CHECKPOINT_DIR=run/checkpoint
TRAIN_DIR= /scripts/result #The directory where you want to save your trained models.
DATASET_DIR=/scripts/process #The directory where processed.tf records are located.

python train_image_classifier.py --train_dir=${TRAIN_DIR} --dataset_name=embryo --dataset_split_name=train 
--dataset_dir=${DATASET_DIR} --model_name=inception_v1 --checkpoint_path=${PRETRAINED_CHECKPOINT_DIR}/inception_v1.ckpt 
--checkpoint_exclude_scopes=InceptionV1/Logits --max_number_of_steps=5000 --batch_size=32 --learning_rate=0.01 
--save_interval_secs=100 --save_summaries_secs=100 --log_every_n_steps=300 --optimizer=rmsprop 
--weight_decay=0.00004 --clone_on_cpu=True
```
</p>

<p align="justify">
6. The trained algorithms should be tested using test set images. In folder "AI-ML-Project-Embryo-Analysis-to-Improve-Success-Rate-of-IVF/scripts/slim", predict.py loads a trained model on provided test images. This code needs 5 arguments

```
$ python predict.py v1 ../result/ ../../Images/test output.txt 2
```

- v1 = inception-v1, ../Images/test = the address of test set images, output.txt = the output result file, 2 = number of classes

- You can see output.txt in "AI-ML-Project-Embryo-Analysis-to-Improve-Success-Rate-of-IV/scripts/slim"
</p>

<p align="justify">
The generated output.txt file would look like this.  

>> Image name along with its image path / Probability of being a good embryo / Probability of being a bad embryo

</p>

<p align="center">
  <img width="70%" src=Docs/output.png>
</p>

<p align="justify">
7. The accuracy can be measured using accuracy measurement codes ("acc.py") in "useful" folder. The output.txt file should be in the same folder that you are running acc.py. Then run the following code:  
</p>

```
$ python acc.py
```

✤ <i>This was the final project for the course B016 - Data Analytics for Business(May 2021), at <a href="https://www.stclaircollege.ca/">St. Clair College</a><i>
