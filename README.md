# Agricultural Time Series Library (AgriTSLib)

Agricultural time series data, characterized by high noise levels, strong seasonality, multi-modality, and large datasets, presents unique challenges in the study of crop growth processes. This research focuses on developing machine learning methods to handle these complexities, improving data quality, enhancing feature extraction during various growth stages, and enabling cross-modal analysis.

## Key Research Areas

1. **Data Cleaning and Preprocessing for Agricultural Time Series**:
   - Agricultural time series data often suffers from noise due to environmental changes, sensor inaccuracies, and missing data points. We explore robust preprocessing methods to clean and enhance the quality of the data. Our research emphasizes dealing with noisy, periodic, and multi-modal data (climate, soil, biology, phenotype) in crop growth studies.

2. **Machine Learning Models for Growth Stage Prediction**:
   - Different growth stages of crops require distinct feature extraction strategies. We focus on developing machine learning models that can precisely extract time-series features corresponding to different growth stages. These models will help improve the accuracy of forecasting and the analysis of the relationships between various crop growth phases.

3. **Multi-Modal Machine Learning Models**:
   - Agricultural data comes from diverse sources, such as text, images, and sensor data (depth, temperature, humidity, etc.). Our work aims to construct models that effectively handle multi-modal inputs, enabling the development of cross-modal analysis methods for predicting and understanding crop growth dynamics.

4. **Efficient Agricultural Time Series Analysis Framework**:
   - Existing machine learning frameworks often lack specific models tailored to agricultural time series data. Our goal is to build an efficient, extensible analysis framework that can handle multi-modal time series data effectively. This framework will provide a unified environment for model training, testing, hyperparameter tuning, and offer flexible components and visualization tools for crop growth analysis.

## Model Tasks and Framework

We address five primary tasks in agricultural time series analysis: 
- **Long-term and Short-term Forecasting**: Predicting crop yields and growth patterns based on time-series data.
- **Imputation**: Filling in missing data in time-series records to ensure the consistency and completeness of input data.
- **Anomaly Detection**: Identifying unusual events or outliers in the data that may indicate abnormal growth patterns or sensor malfunctions.
- **Classification**: Classifying different growth stages or crop types based on their time-series patterns.
- **Cross-modal Analysis**: Integrating text, image, and sensor data to provide a comprehensive analysis of crop growth.

## Objectives

- **Data Quality Enhancement**: Focusing on improving the quality of noisy, incomplete, and multi-modal agricultural data through advanced preprocessing techniques.
- **Feature Extraction Accuracy**: Enhancing the precision of time-series feature extraction to accurately reflect crop growth stages and their seasonal fluctuations.
- **Cross-modal Machine Learning Models**: Developing models capable of analyzing and predicting crop growth using multi-modal data, including text, images, and sensor data.
- **Scalable Framework**: Building a flexible and scalable time-series analysis framework that offers robust tools for model customization and hyperparameter optimization, along with visualization components tailored to agricultural tasks.



## 安装

1. 请确保您已安装 Python 3.8 或更高版本。
2. 安装所需依赖：
   ```bash
   pip install -r requirements.txt
   
## 使用说明

### 1. 运行基准模型

我们为所有基准模型提供了实验脚本，可以通过以下命令运行：

```bash
# 长期预测
bash ./scripts/long_term_forecast/ETT_script/TimesNet_ETTh1.sh
# 短期预测
bash ./scripts/short_term_forecast/TimesNet_M4.sh
# 数据清洗与插补
bash ./scripts/imputation/ETT_script/TimesNet_ETTh1.sh
# 异常检测
bash ./scripts/anomaly_detection/PSM/TimesNet.sh
# 分类
bash ./scripts/classification/TimesNet.sh
‘’‘
### 2. 自定义模型开发

如果您需要开发自己的模型，可以按照以下步骤操作：

1. **添加模型文件**  
   将模型文件添加到 `./models` 文件夹中，您可以参考现有的模型实现，例如 `./models/Transformer.py`。

2. **注册模型**  
   在 `./exp/exp_basic.py` 文件中，将新模型添加到 `Exp_Basic.model_dict` 中。例如：
   ```python
   model_dict = {
       'Transformer': Transformer,
       'YourModelName': YourModelClass,
   }
