# Speech to Text and Text to Speech Python Program

This Python program allows you to convert speech to text and text to speech using the SpeechRecognition and pyttsx3 libraries.

## Requirements

Ensure you have the following libraries installed:

- `speech_recognition`: To recognize speech and convert it to text.
  ```
  pip install SpeechRecognition
  ```
- `pyttsx3`: To convert text to speech.
  ```
  pip install pyttsx3
  ```

## Usage

1. Import the required libraries:
```python
import speech_recognition as sr
import pyttsx3
```

2. Initialize the recognizer and the text-to-speech engine:
```python
r = sr.Recognizer()

def SpeakText(command):
    engine = pyttsx3.init()
    engine.say(command)
    engine.runAndWait()
```

3. Enter a loop to continuously listen for user input:
```python
while True:
    try:
        # Use the microphone as the source for input.
        with sr.Microphone() as source:
            # Wait for a second to let the recognizer adjust the energy threshold based on the surrounding noise level.
            r.adjust_for_ambient_noise(source, duration=0.2)

            # Listen for the user's input.
            audio = r.listen(source)

            # Use Google to recognize audio.
            MyText = r.recognize_google(audio)
            MyText = MyText.lower()

            print("Did you say: " + MyText)
            SpeakText(MyText)

    except sr.RequestError as e:
        print("Could not request results; {0}".format(e))
    except sr.UnknownValueError:
        print("An unknown error occurred.")
```

## How It Works

1. The program listens for user speech using the microphone as the input source.
2. The recognizer adjusts the energy threshold based on the surrounding noise level.
3. The user's speech is converted to text using Google's speech recognition service (`recognize_google`).
4. The text is then printed on the console.
5. The program utilizes the `pyttsx3` library to read the recognized text aloud.

## Contribution

Contributions to this project are welcome! If you encounter any issues or have ideas for improvements, feel free to create a pull request.

---
Created with ❤️
