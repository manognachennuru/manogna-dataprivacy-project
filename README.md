### Exploring Privacy Risks: Reconstructing Medical Images from Obfuscated Gradients in Federated Learning

Federated learning offers collaborative machine learning while preserving data privacy. However, concerns persist regarding privacy in medical image analysis. Leveraging a reconstruction attack framework proposed by Yue et al., I aim to assess gradient obfuscation techniques' effectiveness in safeguarding patient privacy. With medical images being highly sensitive, I'll evaluate methods like gradient noise injection, compression, and quantization. Through experiments with real-world medical datasets, I'll quantify potential privacy leaks and assess the impact on model utility. Balancing privacy with model performance is crucial in healthcare. This project aims to contribute to more robust privacy protection mechanisms, enhancing patient confidentiality in medical image analysis within federated learning.

Dataset Used: chest-xray: https://www.kaggle.com/datasets/paultimothymooney/chest-xray-pneumonia

<img src="doc/results.PNG" width=600>

### References : https://github.com/KAI-YUE/rog. 
### Gradient Obfuscation Gives a False Sense of Security in Federated Learning
![](https://img.shields.io/badge/Python-3-blue) ![](https://img.shields.io/badge/Pytorch-1.9.0-blue)

Federated learning has been proposed as a privacy-preserving machine learning framework that enables multiple clients to collaborate without sharing raw data. However, client privacy protection is not guaranteed by design in this framework.  Prior work has shown that the gradient sharing strategies in federated learning can be vulnerable to server data reconstruction attacks. In practice, though, clients may not transmit raw gradients considering the high communication cost or due to privacy enhancement requirements. Empirical studies have demonstrated that gradient obfuscation, including the intentional gradient noise injection and the unintentional gradient compression, can provide more privacy protection against reconstruction attacks. In this work, we present a new data reconstruction attack framework targeting the image classification task in federated learning.

<br />

#### Prerequisites

- install Python packages
    ```bash
    pip3 install -r requirements.txt
    ```

- Download the pretrained models and put them under `model_zoos` ([link](https://huggingface.co/erickyue/rog_modelzoo/tree/main))

- Download the csv file (https://storage.googleapis.com/openimages/v6/oidv6-class-descriptions.csv) and put it under `data` folder

- The images for a minimal runnable example has been included under `data` folder. The ImageNet validation dataset can be used for a full test. 

<br />

#### Example


- Run the example with QSGD: 
    ```bash
    python3 main.py
    ```
    The script will load the configuration file `config.yaml`. The results will be stored under `experiments`.

- Run the example with FedAvg:
    ```bash
    python3 attack_fedavg.py
    ```
    The script will load the configuration file `config_fedavg.yaml`. 


    You can change the settings in the configuration file. For example, use a different compression scheme with 
    ```
    compress: topk
    ```

<br />

