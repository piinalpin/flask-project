# Flask Project

How to create flask project with virtual environment and Python 3

## Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes. See deployment for notes on how to deploy the project on a live system.

### Prerequisites

Make sure you have installed Python 3 on your device

### Project structure
```
* flask-project
  |--- app
  |    |--- db
  |    |--- module
  |    |    |--- __init__.py
  |    |    |--- controller.py
  |    |    |--- models.py
  |    |--- static (css, javascript, dist bootstrap)
  |    |--- templates (html file)
  |    |--- __init__.py
  |--- venv
  |--- run.py
```

### Step to create flask project

A step by step series of examples that tell you how to get a development env running

1. Install virtual environment

```
pip install virtualenv
```
2. Create virtual environment and activate inside your flask-project directory according the above structure
```
virtualenv venv
> On windows -> venv\Scripts\activate
> On linux -> . env/bin/activate
```
3. Install flask library on your virtual environment with pip
```
pip install flask
```
4. Create `run.py` directory inside flask-project according the above structure
```python
from app import app
app.run(debug=True, host='127.0.0.1', port=5000)
```
5. Create `controller.py` according the abpove structure (flask-project/app/module/)
```python
from flask import render_template, request
from app import app

@app.route('/')
def index():
  return render_template("index.html")
```
6. Create `__init__.py` inside app directory according the above structure (flask-project/app/)
```python
from flask import Flask

app = Flask(__name__)

from app.module.controller import *
```
7. Create `index.html` inside templates directory according the above structure
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Flask Project</title>
</head>
<body>
    <h1>This is from Flask Project -> app.module.controller.index</h1>
</body>
</html>
```
8. Run this project with terminal or command promt
```
python run.py
```
![Sample](flask-project/Sample-run.PNG)

End with an example of getting some data out of the system or using it for a little demo

## Running the tests

Explain how to run the automated tests for this system

### Break down into end to end tests

Explain what these tests test and why

```
Give an example
```

### And coding style tests

Explain what these tests test and why

```
Give an example
```

## Deployment

Add additional notes about how to deploy this on a live system

## Built With

* [Dropwizard](http://www.dropwizard.io/1.0.2/docs/) - The web framework used
* [Maven](https://maven.apache.org/) - Dependency Management
* [ROME](https://rometools.github.io/rome/) - Used to generate RSS Feeds

## Contributing

Please read [CONTRIBUTING.md](https://gist.github.com/PurpleBooth/b24679402957c63ec426) for details on our code of conduct, and the process for submitting pull requests to us.

## Versioning

We use [SemVer](http://semver.org/) for versioning. For the versions available, see the [tags on this repository](https://github.com/your/project/tags). 

## Authors

* **Billie Thompson** - *Initial work* - [PurpleBooth](https://github.com/PurpleBooth)

See also the list of [contributors](https://github.com/your/project/contributors) who participated in this project.

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details

## Acknowledgments

* Hat tip to anyone whose code was used
* Inspiration
* etc
