# AI-ML-Project-Embryo-Analysis-to-Improve-Success-Rate-of-IVF


**This project is a recreation of STORK repository [Github Link to STORK](https://github.com/ih-lab/STORK) which is used for embryo classification.**


***
<details><summary>Table of Contents</summary>  

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

***

<a name="ATP"/>

## 1. **About the project**
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

***

<a name="Prerequisites"/>

## 2. **Prerequisites**
<p align="justify">
    
-- Python Version 2.7  
-- Tensorflow Version 1.15
    
</p>

***

<a name="Dataset"/>

## 3. **Dataset**
---snip----

***

<a name="Data_Pipeline"/>

## 3. **Data Pipeline**

<p align="center">
  <img width="100%" src=Docs/pipeline.png>
</p>

***

<a name="Methodology"/>
## Methodology
---snip----

***

<a name="Results_and_Discussion"/>
## Results and Discussion
---snip----

***

<a name="References"/>
## References
---snip----

***

<a name="Contributors"/>
## Contributors
---snip----

***

<a name="Steps_To_Follow"/>

## 9. **Steps To Follow**

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
