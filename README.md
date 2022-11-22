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
sys.path.append(os.path.abspath('C:/Users/User/Desktop/bonfire'))
from flask import Flask
from bonfire.Bot import *
from bonfire.method import *
import time
from flask import request,Response
import requests
app = Flask(__name__)
bot=Bots("5742908539:AAGP6V4K-sGYlRaJUFJlx2l8uNtk308lpiM")

@commands(app)#this function should be only 1 in the whole project
def main():#the name "main" can be anything, it will not affect the operation of the program
 message=message_method(request.get_json())#receive a message
 if "/start" in message['text']:#/start command handler
    send_message(bot,chat_id=message['chat_id'],text=f"hello @{message['author_username']}!")#send message
 return Response('Успешно', status=200)
if __name__ == '__main__':
       run(app)#start code
       """set-webhook - > https://api.telegram.org/botTOKEN/setWebhook?url=URL"""
```


  </details>

