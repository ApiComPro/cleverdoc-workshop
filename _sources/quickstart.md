# QickStart
This is a quick start guide to get you up and running with the `CleverDoc` library.

## Dependencies

- Python 3.9
- PyTorch 1.11+
- Spark 3.4.0+
- Onnxruntime 1.10.0+
- Transformers 4.11.3+

## Installation
The following command installs CleverDoc from the [Python Package Index](https://pypi.org/project/cleverdoc/). You will need a working installation of Python 3.9 and pip.

```bash
pip install cleverdoc[inference]
```

## Quick tour

### Start Spark session with CleverDoc
```python
from cleverdoc import *
spark = start(license='your_license_key')
```

### Load an image to Spark DataFrame
```python
import pkg_resources
doc_example = pkg_resources.resource_filename('cleverdoc', 'resources/images/Personal_Health_Record_Example.png')
df = spark.read.format("binaryFile").load(doc_example)
```
Show the image
```python
show_images(df, "content")
```
### Define Spark ML pipeline for extract text
```python
from pyspark.ml.pipeline import PipelineModel

pipeline = PipelineModel(stages=[
    BinaryToImage(),
    ImageToString()
])
```

### Run the pipeline
```python
text_df = pipeline.transform(df)
text_df.show()
```

### Get extracted text
```python
print(text_df.select("text.text").collect()[0][0])
```

