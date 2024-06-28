# Generating Synthetic Flight Tracks Using Generative Adversarial Networks (GANS)  

Capstone Project  
DAEN 690-006  
Team Sky Squad: Neeraj Kumar Neela, Naga Pranavi Kandarpa, Sai Yeshwanth Reddy Chinakota, Pravallika Avula, Junaid Mohammed, Lalithanjali Yarrapatruni  
## Abstract
This project focuses on the generation of synthetic flight tracks using Generative Adversarial Networks (GANs) based on historical flight data from Zurich Airport. The dataset is based on runway 34 at Zurich Airport for the dates 3 October 2019 to 30 November 2019. The dataset includes information such as timestamp, altitude, callsign, and other relevant fields. The project aims to overcome the limitations of traditional simulation methods, which often rely on simplified models that may not accurately represent the complexities of real-world flight trajectories. The proposed system architecture comprises several key components, including a data source (OpenSky Network), data storage (Amazon S3), a computational cluster, a development environment (Jupyter Notebook), and the GAN model itself. The GAN is trained on historical flight data to learn the underlying patterns and dynamics of flight trajectories, allowing it to generate diverse synthetic trajectories that closely mimic real-world behavior. The generated flight tracks can be used for various applications, including air traffic simulation, flight path optimization, and anomaly detection. The proposed system architecture leverages cloud computing and AWS services for scalability and flexibility. The workflow includes data collection, preprocessing, model training, and generation of realistic flight trajectories. Security measures such as encryption and access control ensure the integrity and confidentiality of the data. The project aims to address the scarcity of data on new technologies and procedures in air traffic management, enabling scenario forecasting and innovation in airspace design. The significance of this research lies in its potential to enhance safety and efficiency in air traffic management through the generation of realistic synthetic flight tracks. Overall, this project aims to contribute to the field of air traffic management by providing a novel approach to generating synthetic flight tracks that can be used to improve the safety and efficiency of aviation operations.


## Problem Description
Air-to-air collision Risk Modelling for Airspace design and approval is dependent on accurate flight tracks. CRM typically uses historic flight tracks supplemented with simulated flight tracks. Historic flight tracks cannot represent new technologies and procedures. Simulated flight tracks can represent new technologies and procedures, however, even using super-computers a sufficient sample size of flight tracks cannot be generated. Conventional methods heavily rely on historical flight data, often neglecting emerging technologies and procedures, leading to an incomplete understanding of collision risks. The challenge lies in the scarcity of diverse flight track data for comprehensive risk analysis, constrained by computational limitations. To overcome this, the project proposes leveraging Generative Adversarial Networks (GANs) to synthesize realistic flight tracks. By training the GAN model on historical data, the aim is to produce a comprehensive dataset mirroring real-world trajectories, accommodating both conventional and emerging aviation scenarios. This approach facilitates proactive safety measures and informed decision-making in air traffic management.


<img width="331" alt="Picture1" src="https://github.com/SkySquad6/SyntheticFlightTrack/assets/159192661/d61809c4-983f-4c4b-8053-579148fba678">

## Project Goals  
The project goals are as follows.  
  * Generate one million realistic synthetic flight tracks using GANs to fill data gaps and assess emerging aviation risks.  
  * Develop validated tools for air traffic management, ensuring safety compliance and informed decision-making.  
  * Gain insights into flight data generation challenges for enhanced airspace design and risk modeling.  

## About the Files Attached to the GitHub  
* Zurich airport Runway 34 Data set which has the flight details downloaded from the OpenSky Network.
* GANS.ipynb - Wasserstein Gans visual using Python Code.

## Tool/algorithm that We Used for the project  
* Scaling algorithm to normalize features.
* GAN uses noise vectors to create synthetic routes.

## Cloud Platform (AWS)
Storage: EC2 instance built-in storage  
Computing: EC2 (Windows server)  
AWS S3 and Hopper cluster facilitate GAN training.   

## Dataset
![pic 15](https://github.com/SkySquad6/SyntheticFlightTrack/assets/159192661/0292fb5a-8ab6-4d6a-bfe6-d5db65e30ff9)

The datasets we are using are a set of data points which represent position of the point at that instance of time and a number of these points can be considered as a flight track. The data was collected by OpenSky Network, the world's largest crowdsourced dataset of real-time and historical flight positions, democratizing air traffic information. 
 
Our dataset offers a unique glimpse into the operations of runway 34 at Zurich Airport (LSZH) for a specific period spanning from October 3rd, 2019, to November 30th, 2019. With 71,400 meticulously cleaned data points, each representing a snapshot of a flight's journey, this resource unlocks valuable insights into various aspects of runway usage. The time frame itself holds significance. Covering late fall, it captures the transition from summer to winter, potentially revealing how changing weather patterns like wind direction and strength impacted runway selection. Examining how wind conditions influenced the distribution of arrivals and departures on runway 34 could expose valuable trends for safety and efficiency optimizations.


## Solution Approach

![Picture2](https://github.com/SkySquad6/SyntheticFlightTrack/assets/159192661/6d14d674-effe-4691-bf21-d6030a0277e3)

 The proposed system architecture for generating flight tracks using Generative Adversarial Networks (GANs) leverages cloud computing and publicly available datasets for scalability and flexibility. It consists of several core components. Firstly, the OpenSky Network serves as the primary data source, providing historical flight track data, particularly focusing on the Zurich dataset. This data is then securely stored in Amazon S3, a highly scalable and reliable object storage service, facilitating easy access for subsequent processing. A cloud-based computational cluster is provisioned to harness the necessary processing power for GAN training, offering flexibility in selecting instance types based on workload demands.  
 
Within this computational environment, Jupyter Notebooks provide an interactive development environment for constructing the GAN architecture using preferred deep learning frameworks such as TensorFlow or PyTorch. The GAN model, developed within the Jupyter Notebook, undergoes rigorous training on historical flight data from OpenSky, with the adversarial process between the generator and discriminator networks driving optimization of flight track generation. The trained GAN model produces realistic flight tracks, which can be utilized for various downstream applications including air traffic simulation, flight path optimization, and anomaly detection.  

The workflow involves data collection, cleaning, and preprocessing from OpenSky, followed by secure storage of preprocessed data in Amazon S3. Subsequently, a computational cluster is provisioned, and a Jupyter Notebook instance is launched for GAN model development. The GAN training process accesses data directly from S3, and the generated flight tracks are evaluated and visualized for quality assessment. Additionally, the architecture offers flexibility in cloud provider selection, with AWS chosen for this project due to factors such as cost and tool compatibility.  

## Model Selection
Generative Adversarial Networks (GANs) are chosen for their significant advantages in synthesizing realistic and diverse flight track data, specifically to address the project's objectives of representing new technologies and procedures absent from historical data. GANs excel at capturing complex, high-dimensional distributions inherent in real-world flight trajectories, ensuring that generated data possesses intricate spatiotemporal patterns characteristic of air traffic movements. Moreover, GANs provide a robust solution for overcoming the scarcity of historical data concerning new technologies and procedures by simulating plausible flight tracks aligned with projected trajectories. These synthetic flight tracks enable comprehensive scenario forecasting, empowering safety and efficiency analyses with insights into potential risks and optimization opportunities. Additionally, GAN-produced flight tracks serve as valuable tools for airspace design innovation, providing a sandbox environment for assessing, fine-tuning, and optimizing future airspace management solutions. Overall, GANs stand out as the superior choice due to their capability to represent trajectories shaped by new technologies, enable scenario forecasting, and foster innovation in airspace design.

 ![Picture4](https://github.com/SkySquad6/SyntheticFlightTrack/assets/159192661/d4c827a1-d60f-4615-85b9-37860b202445)  
Synthetic flight routes – MINMAX SCALING  
* X axis: Scaled Longitude  
* Y axis: Scaled Latitude


![Picture5](https://github.com/SkySquad6/SyntheticFlightTrack/assets/159192661/83e4608e-6b1f-45a3-a96c-66772ebaa999)  
Altitude distribution – MINMAX SCALING


![Picture6](https://github.com/SkySquad6/SyntheticFlightTrack/assets/159192661/f9845a49-0afb-4fe9-8e05-67915bd59877)  
Comparison – MINMAX SCALING 


![Picture10](https://github.com/SkySquad6/SyntheticFlightTrack/assets/159192661/166a2e7e-4976-4002-8cde-aac5d0c11b3b)  
Comparison – STANDARD SCALING 
* X axis: Longitude
* Y axis: Latitude
  
![Picture11](https://github.com/SkySquad6/SyntheticFlightTrack/assets/159192661/55e6a1c5-31f9-4166-a819-18c8a0884869)  


### Wasserstein GAN  
<img width="435" alt="image" src="https://github.com/SkySquad6/SyntheticFlightTrack/assets/159192661/928f7bb9-2471-435a-b78b-28d9c032055a">

If you have any questions, please contact us via email.  
nneela@gmu.edu  
nkandarp@gmu.edu  
pavula@gmu.edu  
schinako@gmu.edu  
jmohamm4@gmu.edu  
lyarrapa@gmu.edu  
