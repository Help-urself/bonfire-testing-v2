# update

<details>
  <summary> -new structure </summary>

`before`<br>
**1.install interceptor**
- install [ngrok](https://ngrok.com/) and start the server according to the instructions on the website.
- set webhook `https://api.telegram.org/botTOKEN/setWebhook?url=you url ngrok/hosting url`

### Simple [`send_message`](https://core.telegram.org/method/messages.sendMessage) request

```python
#git clone
import os
import sys
sys.path.append(os.path.abspath('your campfire folder path'))
import Bot
from Bot import Bots,commands,run
from flask import Flask
from method import *
import time
from flask import request,Response
import requests
app = Flask(__name__)
bot=Bots("TOKEN")#setting up a token for requests

@commands(app)#message handler
def main():#the main name can be anything, it doesn't matter
 try:
    message=request.get_json()#receive a message
    chat_id,text,message_id,message_author_username,message_author_id,message_author_is_bot,message_author_first_name,message_author_language_code,message_date=parse_message(message=message)#methods message
    if "/start" in text: #/start command handler
        send_message(bot=bot,chat_id=chat_id,text=f'hello @{message_author_username}!')#send message
 except Exception as error:
     print(error)
 return Response('OK', status=200)#return to cmd (POST/ 200 OK)

if __name__ == '__main__':
       run(app)#app.run(port=8080,host="0.0.0.0",debug=True)
```

```py
#pip install
from bonfire.Bot import Bots,commands,run
from flask import Flask
from bonfire.method import *
import time
from flask import request,Response
import requests
app = Flask(__name__)
bot=Bots("TOKEN")#setting up a token for requests

@commands(app)#message handler
def main():#the main name can be anything, it doesn't matter
 try:
    message=request.get_json()#receive a message
    chat_id,text,message_id,message_author_username,message_author_id,message_author_is_bot,message_author_first_name,message_author_language_code,message_date=parse_message(message=message)#methods message
    if "/start" in text: #/start command handler
        send_message(bot=bot,chat_id=chat_id,text=f'hello @{message_author_username}!')#send message
 except Exception as error:
     print(error)
 return Response('OK', status=200)#return to cmd (POST/ 200 OK)

if __name__ == '__main__':
       run(app)#app.run(port=8080,host="0.0.0.0",debug=True)
       """set-webhook - > https://api.telegram.org/botTOKEN/setWebhook?url=URL"""
```

`now`<br>
**1.install interceptor**
- install [ngrok](https://ngrok.com/) and start the server according to the instructions on the website.
- set webhook `https://api.telegram.org/botTOKEN/setWebhook?url=you url ngrok/hosting url`

### Simple [`send_message`](https://core.telegram.org/method/messages.sendMessage) request

```python
#git clone
import os
import sys
sys.path.append(os.path.abspath('your campfire folder path'))
from flask import Flask
from bonfire.Bot import *
from bonfire.method import *
import time
from flask import request,Response
import requests
app = Flask(__name__)
bot=Bots("TOKEN")#setting up a token for requests

@commands(app)#command handler, there can be only 1 in the code
def main():
 if message(request.get_json())['text'] == "Test":#receive a message
    send_message(bot,chat_id=message(request.get_json())['chat_id'],text=f"hello @{message(request.get_json())['author_username']}")#send message
 return Response('OK', status=200)#return status to cmd (POST 200 OK)
if __name__ == '__main__':

       run(app)#start code
       """set-webhook - > https://api.telegram.org/botTOKEN/setWebhook?url=URL"""
```


  </details>

