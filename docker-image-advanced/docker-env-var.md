## Docker Environment Variables

- Consider the app.py file below:
```python
import os
from flask import Flask
app = Flask(__name__)
…
…
color = "red"
@app.route("/")
def main():
print(color)
return render_template('hello.html', color=color)
if __name__ == "__main__":
app.run(host="0.0.0.0", port="8080")
```
- The app.py file contains a variable called color. The value of the variable is red. It will make the background color of the web page red.
- What if we want to change the color of the web page? We can change the value of the color variable in the app.py file. But, we have to rebuild the image and recreate the container.
- We can use environment variables to change the value of the color variable without rebuilding the image and recreating the container.
- We can create app.py file as below:
```python
import os
from flask import Flask
app = Flask(__name__)
…
…
color = "red"
@app.route("/")
def main():
print(color)
return render_template('hello.html', color=color)
if __name__ == "__main__":
app.run(host="0.0.0.0", port="8080")
```
- We have two options to set the value of the color variable:
    - We can set the value of the color variable using export command. Example: `export APP_COLOR=blue; python app.py`
    - We can set the value of the color variable in the docker run command. Example: `docker run -d -p 5000:5000 -e APP_COLOR=blue simpleapp`
- We can inspect the environment variables of a container using the docker inspect command.
```
docker inspect <container_name>
```

Date of Learning: 07/01/2024