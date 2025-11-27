## Image creation using tensorflow
This repository contains a Go-based image recognition service powered by TensorFlow. It provides a simple HTTP API for classifying images using a pre-trained deep learning model.  

## Getting Started  

### Building the Docker Image  
Build the image using the following command:  
```bash
docker build -t localhost/recognition .
```

### Running the Service  
Start the service in a Docker container:  
```bash
docker run -p 8080:8080 --rm localhost/recognition
```

### Using the API  
Send an image for classification via a POST request:  
```bash
curl localhost:8080/recognize -F 'image=@./cat.jpg'
```

Example response:  
```json
{
  "filename": "cat.jpg",
  "labels": [
    { "label": "tabby", "probability": 0.45087516 },
    { "label": "Egyptian cat", "probability": 0.26096493 },
    { "label": "tiger cat", "probability": 0.23208225 },
    { "label": "lynx", "probability": 0.050698064 },
    { "label": "grey fox", "probability": 0.0019019963 }
  ]
}
```

## Implementation Details  
This service was developed as part of the tutorial *Build an Image Recognition API with Go and TensorFlow*. It demonstrates how to integrate TensorFlow's machine learning capabilities into a Go application, exposing them through a RESTful endpoint.

## License  
MIT License
