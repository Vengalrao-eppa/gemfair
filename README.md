Requirements

	- Build a simple microservice that can receive an uploaded image and return a unique identifier for the uploaded image that can be used subsequently to retrieve the image.
	- Extend the microservice so that different image formats can be returned by using a
	  different image file type as an extension on the image request URL.
	- Extend the microservice with simple filters such as crop and rotation.
	- Write a series of automated tests that test the image upload, download and file
	format conversion capabilities.

	- API Details
		- API Endpoint: "/upload-image"
		- Output: Returns a JSON response
			for eg: { "id": "unique_id" }
		- Details:
			- When user requests the above endpoint, the user will be asked to select and image and click on upload to upload the image

		- API Endpoint: "/download"
		- URL Parameters:
			- "/download?id=unique_id"
			- "/download?exts=image_type" (image_type = jpeg|jpg|png|gif)
		- Output:
			- Loads the respective image in the browser for a unique id passed in URL
			- Loads all the images matched with the image_type(extension) in the browser
			- To download, click on the Image


Questions
	• What would you have done if you had more time?
		1. I would've implemented the Database to store the images and to serve the user requests
		2. Would've implemented a Cache mechanism to serve the repeated requests to download the image
		3. Would've designed a UI (least priority) to serve and upload the images
		4. Would've designed a queue mechanism to upload the multiple images at once
		5. Logic to handle/serve the large image files

	• How did you design this service to meet the high-performance requirement?
		1. Load Balancer to handle the number of requests
		2. Cloud Storage to store the images uploaded by users
		3. Cache mechanism to optimize the download of images

	• How did you approach testing this functionality?
		1. I've tested the application from Postman
		2. Tested Upload Image API for different Image formats (I've restricted the image types for JPED, JPG, PNG, GIF)
		3. Tested with unknown Image Id's


Unclear about Requirements
	- Extend the microservice with simple filters such as crop and rotation.
		1. When should we apply these filters (before uploading image to server or while serving the image as download request)
		2. For Rotating the image also, we can achieve this through Javascript in the browser itself


To run the application:
	python run.py
To test the application:
    python tests.py