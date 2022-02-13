
Speech Recognition is an important feature in several applications used such as home automation, artificial intelligence, etc. This article aims to provide an introduction on how to make use of the SpeechRecognition and pyttsx3 library of Python.

Installation required:

Python Speech Recognition module:
pip install speechrecognition
PyAudio: Use the following command for linux users
sudo apt-get install python3-pyaudio
Windows users can install pyaudio by executing the following command in a terminal

pip install pyaudio
Python pyttsx3 module:
pip install pyttsx3
Speech Input Using a Microphone and Translation of Speech to Text

Allow Adjusting for Ambient Noise: Since the surrounding noise varies, we must allow the program a second or too to adjust the energy threshold of recording so it is adjusted according to the external noise level.
Speech to text translation: This is done with the help of Google Speech Recognition. This requires an active internet connection to work. However, there are certain offline Recognition systems such as PocketSphinx, but have a very rigorous installation process that requires several dependencies. Google Speech Recognition is one of the easiest to use.
Translation of Speech to Text:

First, we need to import the library and then initialize it using init() function. This function may take 2 arguments.

init(driverName string, debug bool)
drivername: [Name of available driver] sapi5 on Windows | nsss on MacOS
debug: to enable or disable debug output
After initialization, we will make the program speak the text using say() function.
This method may also take 2 arguments.

say(text unicode, name string)
text: Any text you wish to hear.
name: To set a name for this speech. (optional)
Finally, to run the speech we use runAndWait() All the say() texts won’t be said unless the interpreter encounters runAndWait().
