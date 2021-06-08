# **Dense-optical-flow-using-RAFT**
This is a deep learning project for the prediction of optical flow in the image frames. The dataset taken is Sintel.
This document gives the instructions on how to run the code and the software/ libraries needed to run the code and view the project details for the subject Computer vision(IT813) which was done under the supervision of Mr Dinesh Naik.

### **The final submission is divided into the following directories:**
* **PPT**: contains the ppt `CV PRESENTATION.pdf` for the final presentation.
* **REPORT**: contains the final report `ComputerVisionReport.pdf` submitted
* **CODE**: `opticalflow.ipynb` contains the code for the implementation of the project.


### **Dataset**
*The dataset used for the project is Sintel dataset for flow prediction. It can be downloaded from http://files.is.tue.mpg.de/sintel/MPI-Sintel-complete.zip

### **Working environment**:
* The code is written in python.
* The code was run on google colab and can be run on jupyter notebook(with all the dependencies installed)

### **Dependencies for the project**:
1. pytorch 1.6.0
2. torchvision 0.7.0
3. Cudatoolkit 10.1
4. matplotlib
5. tensorboard
6. scipy
7. Opencv

### **How to run the code file?**
* Goto colab.google.com
* Upload the file opticalflow.ipynb
* The first cell !nvidia-smi shows the realtime allocation of resources, if it shows that around 16GB of RAM is allocated, then you are good to go, else the program may take a longer time to get executed.(you may wait for some time and run this code again to see if any change in the allocated memory)
* After successful execution of above block run all the code clocks below it.
* The final results are shown in terms of EPE(End Point Error).

### **Results:**
* **The results with manual hyperparameter tuning are**:

| BATCH SIZE    | LEARNING RATE | WEIGHT DECAY|GAMMA| GRU ITERATIONS| STEPS| SINTEL(CLEAN) EPE| SINTEL(FINAL)EPE|
|:-------------:|:-------------:|:-----------:|:---:|:-------------:|:----:|:----------------:|:---------------:|
| 10            | 0.000125      | 0.00001     |0.9  |12             |5000  |4.25              |5.05             |  
| 10            | 0.000125      | 0.00001     |0.9  |12             |10000 |3.50              |4.23             |
| 5             | 0.00125       | 0.00001     |0.9  |12             |5000  |3.76              |4.52             |
| 10            | 0.00125       | 0.00001     |0.9  |12             |5000  |2.43              |3.16             |
| 5             | 0.00001       | 0.00001     |0.9  |12             |5000  |5.67              |6.44             |
| 5             | 0.00001       | 0.00001     |0.9  |12             |5000  |3.83              |4.54             |
| 10            | 0.000125      | 0.00001     |0.9  |12             |5000  |4.25              |5.05             |
| 10            | 0.000125      | 0.00001     |0.9  |12             |10000 |3.38              |4.22             |
| 13            | 0.000125      | 0.00001     |0.85 |6              |5000  |5.16              |5.19             |
| 13            | 0.000125      | 0.00001     |0.85 |6              |10000 |4.06              |4.79                |


* **The results with one cycle learning policy are**:

| PROPERTY NAME    | PROPERTY VALUE |
|:----------------:|:--------------:|
| Batch size       | 13             |
| Learning Rate    | 0.000125       |
| Weight decay     | 0.00001        |
| Gamma            | 0.85           |
| GRU iterations   | 6              |
| steps            | 1000           |
| cycle momentum   | true           |
| Sintel(clean)EPE | 3.02           |
| Sintel(clean)EPE | 3.80           |

* **The results after transfer learning are**:

| BATCH SIZE    | LEARNING RATE | WEIGHT DECAY|GAMMA| GRU ITERATIONS| STEPS| SINTEL(CLEAN) EPE| SINTEL(FINAL)EPE|
|:-------------:|:-------------:|:-----------:|:---:|:-------------:|:----:|:----------------:|:---------------:|
| 13            | 0.000125      | 0.00001     |0.85 |6              |5000  |4.25              |5.05             |  
| 13            | 0.000125      | 0.00001     |0.85 |6              |10000 |2.10              |3.26             |
| 13            | 0.000125      | 0.00001     |0.85 |12             |5000  |1.81              |2.75             |
| 13            | 0.000125      | 0.00001     |0.85 |12             |10000 |1.60              |2.34             |

* **The results after changing the correlation radius are:**

| RADIUS| SINTEL(CLEAN) EPE| SINTEL(FINAL)EPE|
|:-----:|:----------------:|:---------------:|
|4      |1.60              |2.34             | 
|3      |1.58              |2.20             | 
|5      |1.56              |2.29             | 


### **Authors:**
| NAME                       | ROLL NUMBER     | 
|:--------------------------:|:-------------:| 
| Mohd Asif Khan Khaishagi   | 202IT013      | 
| Praful Kumar               | 202IT020      | 


