# Project: Finetuning phi 1.5 pretrained LLM for Kotlin code completion


##Overview
This project is designed to handle and process Kotlin source code files for training a causal language model. The key objectives include cleaning and preparing Kotlin source code, splitting it into training, validation, and test datasets, and using these datasets to fine-tune a pretrained causal language model. The project focuses on creating an end-to-end functioning prototype rather than perfecting any single component. The aim is to demonstrate the workflow of preparing data and training a model with advanced parameter-efficient fine-tuning techniques.


##Features
Source Code Cleaning: Automated removal of comments and formatting of Kotlin source files.
Data Splitting: Organizing cleaned data into distinct sets for training, validation, and testing.
Model Training: Fine-tuning a pretrained model using Parameter Efficient Fine-tuning (PEFT) techniques.


##Prerequisites
Before setting up the project, ensure the following are installed:

- Python 3.8 or higher
- Git
- Required Python libraries: **torch, transformers, datasets, rouge, bitsandbytes, peft, pandas, numpy, nltk**


## Installation
####Clone the Kotlin repository and move all .kt files to separate directory to use as data source:
Run in terminal

`git clone https://github.com/JetBrains/kotlin.git`

`!mkdir kotlin_files`

`!find kotlin -type f -name "*.kt" -exec mv {} kotlin_files \;`

####Install Required Python Packages:

`!pip install accelerate transformers einops datasets peft bitsandbytes rouge --upgrade`

###Run the `finetuning_phi15_for_Kotlin_code_completion.ipynb` file ***(detailed comments in the file)***


##Limitations
This project was developed with the primary goal of creating an end-to-end workflow, rather than optimizing or perfecting any specific aspect. As such, several limitations were encountered, including CUDA memory constraints that prevented full-scale training and evaluation. 

#P.S. Personal Notes
##Reflections on the Learning Process
This project was my first foray into the world of fine-tuning transformers, particularly in the domain of natural language processing with code. I gained substantial insights into handling large datasets, managing memory resources efficiently, and navigating the complexities of model configurations. One of the biggest takeaways was understanding the nuances of the PEFT (Parameter Efficient Fine-tuning) technique, which was both challenging and rewarding. Managing to get everything to work end-to-end, albeit not perfectly, has greatly enhanced my confidence in handling large-scale machine learning projects.

##Challenges and Overcoming Them
One of the significant challenges I faced was related to CUDA memory limitations. As a beginner in fine-tuning large models, I underestimated the resource requirements, leading to frequent out-of-memory errors. To mitigate this, I had to learn about more efficient batch processing, model quantization, and leveraging model sharding techniques to fit the training process within available resources. These solutions weren't perfect but allowed me to proceed with training under constrained conditions. Another challenge was understanding and applying the advanced settings of the transformers library, which I overcame by extensively reviewing documentation and community forums.

##Future Directions
If I had more resources or time, I would focus on optimizing the model's memory usage further to enable more extensive training sessions without interruptions. Additionally, I would like to explore other models that might be more efficient and suitable for handling source code. Implementing a more robust error handling and recovery process would also be on my agenda to make the training process more resilient. Lastly, I aim to refine the data preprocessing steps to improve model performance and potentially achieve better fine-tuning results.


