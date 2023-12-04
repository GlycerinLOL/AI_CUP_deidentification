# AICUP2023-TEAM-3868
此專案為 AICUP 隱私保護與醫學數據標準化競賽：解碼臨床病例、讓數據說故事比賽的Github code，程式部分我們有參考 [Robust DeID: De-Identification of Medical Notes using Transformer Architectures](https://github.com/obi-ml-public/ehr_deidentification/tree/main) 的訓練方式，並且我們設計了獨特的 PostProcess System
## 運行環境
### 使用 Anaconda 建立環境
```bash
conda create -n ehr python=3.7
```
### python 套件
```bash
pip install -r requirements.txt
```
## 運行方式
請新增 ```raw_data/``` folder後執行 ```preprocess.ipynb``` 中的程式，將會創建 train test dev dataset 格式為
### train dev data format
```python3
{
    "text": '...', // document content
    'meta': {"note_id": file_name},
    'spans': [{'label': 'MEDICALRECORD' ...}],
}
```
### test data format
```python3
{
    "text": '...', // document content
    'meta': {"note_id": file_name},
    'spans': [],
}
```
