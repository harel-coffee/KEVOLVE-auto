# KEVOLVE
* KEVOLVE v1.1 Help file																		  
* K-mers based feature identifier for viral genomic classification                            
* Copyright (C) 2023  Dylan Lebatteux and Abdoulaye Banire Diallo    
* Author : Dylan Lebatteux												  
* Contact : lebatteux.dylan@courrier.uqam.ca

### Description
KEVOLVE, an approach based on a Genetic Algorithm  including a Machine-Learning kernel to extract a bag of minimal subsets of k-mers features maximizing a given classification score threshold. 

### Required softwares
* [python](https://www.python.org/downloads/) 
* [scikit-learn](https://scikit-learn.org/stable/install.html) 
* [numpy](https://numpy.org/install/)                        
* [biopython](https://biopython.org/wiki/Download)  
* [joblib](https://joblib.readthedocs.io/en/latest/)

### Parameters
List of parameters requiring adjustment in the configuration_file.ini :
* k_min : Minimum length of k-mers
* k_max : Maximum length of k-mers
* T : Percentage performance threshold (T = 0.999 is recommended) .
* training_fasta : Training fasta file path
* testing_fasta : Testing fasta file path
* k_mers_path : Path file of the extracted k-mers
* model_path : Path file of the prediction model
* prediction_path : Path of the sequence prediction file
* evaluation_mode : Evaluation mode during the prediction (True/False). 

### Utilization
1) Specify the parameters of the previous section in the configuration_file.ini.
2) Run the following command :
```sh
$ python main.py configuration_file.ini
```
3) Select an option:
- 1.Extract k-mers | Required parameters: T, k_min, k_max, training_fasta and k_mers_path
- 2.Fit a model | Required parameters: training_fasta, k_mers_path and model_path
- 3.Predict a sequences | Required parameters: testing_fasta, k_mers_path, model_path, prediction_path and evaluation_mode
- 4.Motif analyzer | Required parameters: training_fasta, k_mers_path and reference_sequence
- 5.Exit/Quit

### Fasta file format example for n sequences: 

```sh
>id_sequence_1|target_sequence_1 
CTCAACTCAGTTCCACCAGGCTCTGTTGGATCCGAGGGTAAGGGCTCTGTATTTTCCTGC 
>id_sequence_2|target_sequence_2						
CTCAACTCAGTTCCACCAGGCTCTGTTGGATCCGAGGGTAAGGGCTCTGTATTTTCCTGC
...
...
...
>>id_sequence_n-1|target_sequence_n-1									 
CTCAACTCAGTTCCACCAGGCTCTGTTGGATCCGAGGGTAAGGGCTCTGTATTTTCCTGC 
>id_sequence_n|target_sequence_n													 
CTCAACTCAGTTCCACCAGGCTCTGTTGGATCCGAGGGTAAGGGCTCTGTATTTTCCTGC 
```
* The character "|" is used to separate the sequence ID from its target. 
* The target must be specified in the fasta file for a prediction with evaluation_mode = True.
* For more detailed examples see the data sets in the Data folder   

### Output    
* k_mers.fasta: File of the extracted k-mers list 
* model.pkl : Prediction model generated by CASTOR-KRFE                                        
* Prediction.csv : Results file of the prediction of unknown genomic sequences   
* Signature_location.xlsx : Analysis report associated with a signature

### Reference to cite KEVOLVE
* [Lebatteux, Dylan, and Abdoulaye Baniré Diallo. "Combining a genetic algorithm and ensemble method to improve the classification of viruses." 2021 IEEE International Conference on Bioinformatics and Biomedicine (BIBM). IEEE, 2021.](https://ieeexplore.ieee.org/abstract/document/9669670)

### Reference to cite KANALYZER (Option 4: Motif analyzer)
* [Lebatteux, Dylan, et al. "KANALYZER: a method to identify variations of discriminative k-mers in genomic sequences." 2022 IEEE International Conference on Bioinformatics and Biomedicine (BIBM). IEEE Computer Society, 2022.](https://www.computer.org/csdl/proceedings-article/bibm/2022/09995370/1JC2uDIO8cE)
                                                                                  
