# speech-to-text
## Java Script
In the code below, I invoked the Web Speech Recognition API and initialized an instance stored in  recognition variable.
After this, I made references to  #textbox and #instructions components I characterized in the HTML utilizing JQuery to control them from the code.
content variable keeps track of text the application has converted and displayed in the textarea from the HTML file.
recognition.lang='ar'; for arabic language.

ex Git :

var speechRecognition = window.webkitSpeechRecognition
var recognition = new speechRecognition()
var textbox = $("#textbox")
var instructions = $("#instructions")
var content = ''
recognition.continuous = true
recognition.lang ='ar';
recognition.onstart = function() {
 instructions.text("ابدأ التحدث")
}

The onstart event handler is triggered when the recognition API starts and has microphone access.

ex Git :

recognition.onstart = function() {
 instructions.text("ابدأ التحدث")
}

onresult event handler is triggered when the recognition API has successfully converted speech from the user’s microphone to text, and the data is made available via the event.results variable.

ex Git :

recognition.onresult = function(event) {
 var current = event.resultIndex;
 var transcript = event.results[current][0].transcript
 content += transcript
 textbox.val(content)
}

Now If click the اضغط للبدء button your speech will convert to text

### ESP Steps
Steps for ESP32

1-connect to Internet .

2-Open Arduino IDE. 

3-In menu bar go to "File" then go to "Preferences". 

4-It will appare a box in the URLs box copy and past this URL: https://dl.espressif.com/dl/package_esp32_index.json 

5-go to "Tools" > "Board" > "Board Manager" in the menu bar. 

6-search for "ESP32". 

7-Install the Package .

8-After inslation process is completed you will find"INSTALLED" word.

9-Close the Board Manager. 

10-In menu bar go to "Tools" > "Board": you will find different ESP32 boards selct what is appropriate for your ESP32. 

11-Now you can try an example go to menu bar "File" > "Example".

12- in menu bar go to "Tools" > Port > select the port in the list and run the code.
