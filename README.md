# Psychiatrist ChatBot
## COSC 310 Software Engineering
## Individual project: Aidan Murphy
### Derived from Group 21: Pavni Agarwal, Riley Bolen, Gerren Hunter, Graham Itcush, Aidan Murphy and Maxwell Rex


------

### Local Environment Setup

#### Install Dependencies

`pip install nltk`

`pip install numpy`

`pip install keras`

`pip install tensorflow`

`pip install googletrans==3.1.0a0`

`pip install spacy`

download spacy model

`python -m spacy download en_core_web_sm`

When first running the program, it may ask you to download certain NTLK packages. The only way I found I could download them was by running the code below:

```python
import nltk
import ssl

try:
    _create_unverified_https_context = ssl._create_unverified_context
except AttributeError:
    pass
else:
    ssl._create_default_https_context = _create_unverified_https_context

nltk.download()
```

Link to source can be found here: https://stackoverflow.com/questions/38916452/nltk-download-ssl-certificate-verify-failed


#### Train ChatBot

To train the chatbot you can run the file `app/chatbot/train.py`
This isn't necessary though as this file has been run and the bot is already trained

#### Use ChatBot

To use the chatbot you can run the file `app/chatbot/chatbot_app.py`

------

### List of Features (for individual project)

#### google translate (googletrans library)

The chabot is now able to detect and translate a wide range of languages through the use of the googletrans library, the below example shows english, spanish, german and arabic. The bot translates the input text to english remembering what language it was input as, interprets and selects an appropriate response. The bot then translates it back into the source language and outputs it.

<img width="365" src="https://user-images.githubusercontent.com/77344004/161349714-05d2b003-37d0-4565-afbb-366fb5e23d0f.png">

You: Hi

Psychiatrist (en): Hi! How is your day going?

You: mi día es bueno (my day is good)

Psychiatrist (es): ¡Maravilloso de escuchar! (good to hear!)

You: ich bin arzt (I am a doctor)

Psychiatrist (de): Interessant. Magst du deine Arbeit? (interesting do you like your work?)

You: أرى الهلوسة

(I see hallucinations)

Psychiatrist (ar): تمام. هل لاحظت انخفاضًا في التنظيم في حياتك؟ (على سبيل المثال ، المنزل شديد الفوضى ، وانخفاض الرعاية الذاتية بشكل كبير ، وعدم القدرة على أداء المهام التي كنت تقوم بها من قبل

(OK. Have you noticed a decrease in organization in your life? (For example, the house is too cluttered, self-care is significantly reduced, and the inability to perform the tasks you used to do before)
