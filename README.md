# AI CUP 2023-TEAM-3868
With the rapid development of medical technology, the application of data in the medical field has become increasingly important. These data not only help clinicians better understand patients’ health conditions, but can also be used for disease prediction, medical research, and healthcare policy making. However, the use of such data also brings a key issue, namely privacy protection. How to fully utilize medical data while ensuring patient privacy has become an urgent challenge.

This project is for the AI CUP Privacy Protection and Medical Data Standardization Competition: Decoding Clinical Cases, Letting Data Tell Stories. For the code, we referred to the training method of [Robust DeID: De-Identification of Medical Notes using Transformer Architectures](https://github.com/obi-ml-public/ehr_deidentification/tree/main), and designed a unique PostProcess System. For the data, we additionally included the [i2b2 dataset](https://portal.dbmi.hms.harvard.edu/), increasing the labels from 21 to 28, which adds a certain degree of generalization ability. For more details, please see [DOCS](https://docs.google.com/document/d/1dTvvhDPMTLfh49-yTl7hSe3SgdtqZJ2VHw4hNgfVkjQ/edit?usp=sharing).

## Environment
### Create environment with Anaconda
```bash
conda create -n ehr python=3.7
```
### Python packages
```bash
pip install -r requirements.txt
```

## Checkpoint
|        Class         | Description                          
| :------------------: | :----------------------------------- 
|     `formal_split`          | [huggingface](https://huggingface.co/vickt/AI_CUP_deidentification_formal_split/tree/main)
|     `Add_i2b2_formal_split`          | [huggingface](https://huggingface.co/vickt/AI_CUP_deidentification_add_i2b2_formal_split/tree/main)
|     `Add_i2b2_lower_continue`          | [huggingface](https://huggingface.co/vickt/AI_CUP_deidentification_add_i2b2_lower_continue/tree/main)

## Usage
Please create a folder named ```raw_data/``` under the path and run the code in ```data_create.ipynb```. The code will create Train, Test, and Dev datasets, with the following formats:

### Train/Dev data format
```python3
{
    "text": '...', # document content
    "meta": {"note_id": file_name},
    "spans": [{"label": "MEDICALRECORD", ...}],
}
```

### Test data format
```python3
{
    "text": '...', # document content
    "meta": {"note_id": file_name},
    "spans": [],
}
```
