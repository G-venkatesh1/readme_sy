#The script needs FP32,INT8 ONNX Models, Operations supported are
#Compare Outputs:

##Command to Run:
```python main.py <fp32_model_path> <int8_model_path> --compare_outputs --npy_fp32 fp32_outputs.npy --npy_int8 int8_outputs.npy --mse_json mse_values.json --cos_json cos_values.json --mse_txt mse_greater_than_0.5.txt```


##Description: 
This part involves comparing the outputs of FP32 and INT8 onnx models layer-wise. 
The layer-wise outputs are saved in numpy (npy) files
Metrics such as Mean Squared Error (MSE) and cosine similarity are calculated to quantify the difference between the outputs
If the MSE exceeds a threshold of 0.5 for any layer, its name and MSE value are saved in a text file.


#Model Summary:


##Command to Run:
```python main.py <fp32_model_path> <int8_model_path> --summary --json_fp32 fp32_summary.json --json_int8 int8_summary.json```

##Description: 
The models are loaded to extract summary information.
Node names, unique operation types, and the number of nodes from formula and traversal methods are collected.
The results are saved in JSON files for both the FP32 and INT8 models.

#Inference Time Measurement(Layer-wise):


##Commands to Run:
```python main.py <fp32_model_path> <int8_model_path> --inference_time```

##Explanation:
The model is loaded, and inference is performed.
Profiling is enabled to measure the inference time.
The results are saved in a JSON file containing profiling information.

##Additional Notes:

Replace <fp32_model_path> and <int8_model_path> with the actual file paths of the FP32 and INT8 ONNX models.
Ensure that Python and necessary libraries (such as NumPy, Torch, ONNX, and ONNXRuntime) are installed.
The output files (npy, JSON, and text files) will be created in the current directory unless specified otherwise.
