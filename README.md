# 파이썬 챗봇 만들기!!!!

### 카카오톡 플러스친구 관리자센터

- 플러스 친구 생성 후 공개설정(공개 안되면 검색안됨!!!)
- 스마트 채팅 API형 사용
- 


### c9 개발
- 우측 상단의 톱니바퀴에 들어가서 python3로 설정변경
- `sudo pip3 install flask` 플라스크 설치

### keyboard

```python3
import os
#json으로 변환해주기 위한 import
import json
from flask import Flask

app = Flask(__name__)

@app.route('/')
def hello():
    return '챗봇페이지입니다!!!'

@app.route('/keyboard')
def keyboard():
    
    #keyboard 딕셔너리 생성
    keyboard={
              "type" : "buttons",
              "buttons" : ["메뉴", "로또", "고양이","영화"]
    }
    
    #딕셔너리를 json으로 바꿔서 리턴해주기 위한 코드
    json_keyboard= json.dumps(keyboard)
    return json_keyboard

app.run(host=os.getenv('IP', '0.0.0.0'),port=int(os.getenv('PORT', 8080)))
```
### API

- request
    -url 
