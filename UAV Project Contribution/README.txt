This is my contribution in the API under development for the UAV project,the project involves working with a Raspberry Pi as the primary computational unit and integrating various hardware components, including GPS module, motor, ESC, batteries, servos and camera. The API facilitates efficient communication between the software and hardware systems, enabling precise control and real-time data acquisition. This hands-on project combines expertise in software development, hardware interfacing, and embedded systems to create a fully functional and optimized UAV platform.

API-->

****1)Don't use as soon as you pull the folder from GitHub because One-Drive doesn't give permission for programs to run, instead download and move to directory out of One-Drive.**** 
****2)Models should be configured such that their results for fire is label: Fire for this to work
****3)Before this works you need to change file directories from within ai_models to match your models

1)Use open cmd within the folder and type"pip install -r requirements_falcon.txt".
2)To open server type "python API.py"
3)With cURL you can POST to the API:

*For GPS data in the format of latitude: 40.7128,longitude: -74.0060
curl -X POST http://localhost:8000/gps -H "Content-Type: application/json" -d '{"latitude": 40.7128,"longitude": -74.0060}'

*For images from a directory
curl -X POST http://localhost:8000/detection -H "Content-Type: application/json" -d "{\"image_directory\": \"C:/Users/victo/Downloads/fire.jpg\"}"

In this particular example, if you copy a file as a path "C:\Users\victo\Downloads\fire.jpg" this is what you get, you need to escape the 
double quotes, and make the "\" into backslashes "/" otherwise the cURL command won't work.
