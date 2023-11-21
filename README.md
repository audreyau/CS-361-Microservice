# CS 361 Microservice
Microservice for Michelle Bang's individual project.

## How to programmatically REQUEST data from the microservice
This microservice, built with Express, responds to GET requests to the `/getRandomImage` endpoint by providing a randomly selected image path.

To programmatically initiate a request for data from the microservice, call the getRandomImage() function in the microservice.js file. This function is specifically designed to utilize the Fetch API for making a GET request to the /getRandomImage endpoint on the server.

Example: ```getRandomImage();```<br>

Specific code within getRandomImage(): ```fetch('http://localhost:2000/getRandomImage')```

### Example call:

## How to programmatically RECEIVE data from the microservice
To receive data from the microservice, you can use the Fetch API to retrieve the contents from the URL http://localhost:2000/getRandomImage. Subsequently, parse the response as a JSON file. The resulting data object obtained from parsing the JSON response contains the image path. Utilize this image path to update the src attribute of the UI.

I've encapsulated all these steps in a pre-made function named getRandomImage(). To trigger the process of receiving and updating the UI with a random image, you can invoke this function.

Example (in Index.html): ```<button onclick="getRandomImage()">Randomize Image</button>```

Specific code within getRandomImage(): 
```
    .then(response => response.json())
    .then(data => {
      const randomImagePath = data.imagePath;
      document.getElementById('randomizedImage').src = randomImagePath;
    })
    .catch(error => {
      console.error(error);
    });
```

## UML SEQUENCE DIAGRAM
<img width="1387" alt="Screen Shot 2023-11-20 at 5 59 49 PM" src="https://github.com/audreyau/CS-361-Microservice/assets/52758047/8b0ddb8e-c151-4265-9a53-b8ce6d1d00a7">
