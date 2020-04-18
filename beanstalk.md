pip --version
sudo pip install virtualenv
mkdir myflaskapp
cd myflaskapp
virtualenv env
source env/bin/activate  ( to deactivate command is:deactivate)
pip install flask
pip freeze > requirements.txt
env/
application.py
```
from flask import Flask
application = Flask(__name__)
application.debug = True
@application.route(‘/’, methods=[‘GET’])
def hello():
 return ‘<p>Hello world</p>’
if __name__ == “__main__”:
 application.run()
 ```
 python application.py
 http://127.0.0.1:5000
 pip install awsebcli
 eb init
 eb create --vpc vpcid
 eb status
 eb health
 eb logs
