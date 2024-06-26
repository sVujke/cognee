# cognee API Reference

## Overview


The Cognee API has:

1. Python library configuration entry points
2. FastAPI server 


## Python Library

# Module: cognee.config

This module provides functionalities to configure various aspects of the system's operation in the cognee library. 
It interfaces with a set of Pydantic settings singleton classes to manage the system's configuration.

## Overview
The config class in this module offers a series of static methods to configure the system's directories, various machine learning models, and other parameters.


## Methods


### system_root_directory(system_root_directory: str)
Sets the root directory of the system where essential system files and operations are managed.  Parameters:  
system_root_directory (str): The path to set as the system's root directory.
Example:
```python
cognee.config.system_root_directory('/path/to/system/root')
```

### data_root_directory(data_root_directory: str)
Sets the directory for storing data used and generated by the system.  
Parameters:  
data_root_directory (str): The path to set as the data root directory.

Example:
```python
import cognee
cognee.config.data_root_directory('/path/to/data/root')
```

### set_classification_model(classification_model: object)
Assigns a machine learning model for classification tasks within the system.  
Parameters:  
classification_model (object): The Pydantic model to use for classification.
Check cognee.shared.data_models for existing models.
Example:
```python
import cognee
cognee.config.set_classification_model(model)
```

set_summarization_model(summarization_model: object)
Sets the Pydantic model to be used for summarization tasks.  
Parameters:  
summarization_model (object): The model to use for summarization.
Check cognee.shared.data_models for existing models.
Example:
```python
import cognee
cognee.config.set_summarization_model(my_summarization_model)
```

### set_llm_model(llm_model: object)
Determines the model to handle LLMs.  Parameters:  
llm_model (object): The model to use for LLMs.
Example:
```python
import cognee
cognee.config.set_llm_model("openai")
```

### graph_database_provider(graph_engine: string)
Sets the engine to manage graph processing tasks. 
Parameters:  
graph_database_provider (object): The engine for graph tasks.
Example:
```python
from cognee.shared.data_models import GraphDBType

cognee.config.set_graph_engine(GraphDBType.NEO4J)
```



## API



For each API endpoint, provide the following details:



### Endpoint 1: Root
- URL: /add
- Method: POST
- Auth Required: No
- Description: Root endpoint that returns a welcome message.

#### Response
```json
{
  "message": "Hello, World, I am alive!"
}
```

### Endpoint 1: Health Check
- URL: /health
- Method: GET
- Auth Required: No
- Description: Health check endpoint that returns the server status.
#### Response
```json
{
  "status": "OK"
}
```

More endpoints are available in the FastAPI server. Documentation is in progress
