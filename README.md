# secret-messenger-cordova-ios

This is a Cordova iOS Single Page App that allow registered users to send each other pictures with text messages hidden inside the pictures, which is called Steganography.

	Steganography - is the practice of concealing a file, message, image, or video within another file, message, image, or video.

The application will allow users to register, login, take a photograph using the device camera, encode a text message inside the image, upload the image with the hidden message to the server along with a targeted user to whom to send the message, download a list of messages being sent to the current user, download an image from the message queue, and decode a text message inside a downloaded image.

User Interface

	Ratchet framework was used to build my interface and managing navigation between screens. 

The app has a launcher icon and splashscreen screen.

1. There is a single screen for login and register.

		The following screens should only be accessible after the user logs in.

2. There is a screen (modal) showing list of available messages for the logged in user. 

3. There is a screen (modal) for taking a picture with the device camera and then embedding a message in that image and sending it to a selected user's message queue. The user must be logged in to see this screen.

4. There is a screen (modal) for displaying the downloaded image and message that was embedded. 



Process of Steganography (Accessing the bits inside an Image )

To access the bits inside an image, I put the image onto an HTML5 Canvas Element. Then I call the getImageData( ) method to retrieve an array of values.
Each pixel has four values. One for red, one for green, one for blue, and one for alpha. Every value is between 0 and 255. This is one byte, or 8 bits.

I loop through all the values and read those numbers and change those numbers by taking the binary version of text messages and saving those bits in the blue channels starting at a certain pixel on the canvas element. Once I have changed the numbers I pass them back to the image.
