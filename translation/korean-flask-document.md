플라스크 독스를 보고 직접 번역해보고 싶다는 생각이 들어 이렇게 번역하게 되었습니다. 학습적인 용도로 작성된 문서입니다.
=========

# 빠르게 시작하기

 시작하기를 원하시나요? 이 페이지는 당신이 이미 플라스크를 설치했다고 가정하고, 플라스크에 대한 좋은 설명을 제공해줘요. 만약 설치하지 않으셨다면, 설치 섹션으로 이동하세요.

## 가장 작은 애플리케이션

 가장 작은 플라스크 애플리케이션은 다음과 같이 생겼어요.

```python
from flask import Flask
app = Flask(__name__)

@app.route('/')
def hello_world():
    return 'Hello, World!'
```

 그래서 이 코드는 무슨 역할을 할까요?

1. 먼저 우리는 **플라스크 클래스**를 참조했어요. 이 클래스의 인스턴스가 우리의 WSGI 애플리케이션이 될 거에요.
2. 다음으로 우리는 이 클래스의 인스턴스를 만들었어요. 첫 인자로는 애플리케이션의 모듈이나 패키지 이름이 들어갑니다.  만약 당신이 이 예제처럼 단 하나의 모듈만을 사용한다면, 당신은 `__name__`을 사용해야 해요. 왜냐하면 응용 프로그램으로 시작되거나 혹은 모듈로 가져올지에 따라 이름이 달라지기 때문인데요, 이는 플라스크가 템플릿, 정적 파일 등을 찾을 수 있도록 하기 위해 필요해요. 이에 대한 더 많은 정보를 얻고 싶다면 플라스크 문서를 보는 걸 추천할게요.
3. 우리는 플라스크에게 우리의 함수를 무슨 URL에 작동시킬지 알려주기 위해서 `route()`데코레이터를 사용해요.
4. 이 함수는 특정 기능에 대한 URL을 생성하는 데에도 이름이 사용되며 사용자 브라우저에 표시할 메시지를 반환해줘요.(의역)

 그냥 이 코드를 `hello.py` 혹은 비슷한 이름으로 저장하세요. 플라스크 자체와 충돌할 수 있기 때문에 당신의 애플리케이션을 `flask.py`로 불러서는 안 된답니다.

 애플리케이션을 실행하기 위해서는 플라스크 명령 또는 파이썬의 -m 스위치를 플라스크와 함께 사용하세요. 먼저 `FLASK_APP` 환경 변수를 선언하는 것을 통해 사용할 애플리케이션을 터미널에 알려야 합니다.

```
$ export FLASK_APP=hello.py
$ flask run
 * Running on http://127.0.0.1:5000/
```

 만약 당신이 윈도우를 사용한다면, 
