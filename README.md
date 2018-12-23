# Flask Project

How to create flask project with virtual environment and Python 3 and templating with bootstrap framework

## Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes. See deployment for notes on how to deploy the project on a live system.

### Prerequisites

Make sure you have installed Python 3 on your device

### Project structure
```
* flask-project/
  |--- app/
  |    |--- db/
  |    |--- module/
  |    |    |--- __init__.py
  |    |    |--- controller.py
  |    |    |--- models.py
  |    |--- static/ (css, javascript, dist bootstrap)
  |    |--- templates/ (html file)
  |    |--- __init__.py
  |--- venv/
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
9. Access `localhost:5000` according port that created in `run.py`

![Sample](https://raw.githubusercontent.com/piinalpin/flask-project/master/Sample-run.PNG)

10. To stop the service of flask project (__CTRL + C__)

## Templating flask project with bootstrap

This project will use [Lumino Template Bootstrap](https://medialoot.com/item/lumino-admin-bootstrap-template/) or
[Live Demo](https://medialoot.com/preview/lumino-premium/index.html)

### Step to templating
1. Download template [here](https://medialoot.com/item/lumino-admin-bootstrap-template/)
2. Extract and copy css, fonts, and js directory in static directory according the above structure
3. Create `head.html` in templates directory according the above structure. This file will move tag `<head></head>` from Lumino template master `index.html` and change url for stylesheet and js is required. `css/` to `static/css/`, `js/` to `static/js/`
```html
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>Flask Project</title>
<link href="static/css/bootstrap.min.css" rel="stylesheet">
<link href="static/css/font-awesome.min.css" rel="stylesheet">
<link href="static/css/datepicker3.css" rel="stylesheet">
<link href="static/css/styles.css" rel="stylesheet">
<!--Custom Font-->
<link href="https://fonts.googleapis.com/css?family=Montserrat:300,300i,400,400i,500,500i,600,600i,700,700i" rel="stylesheet">
<!--[if lt IE 9]>
<script src="static/js/html5shiv.js"></script>
<script src="static/js/respond.min.js"></script>
<![endif]-->
```
4. Create `navbar.html` inside templates directory according the above structure. This file will move tag `<nav></nav>` from Lumino template master `index.html`
```html
<nav class="navbar navbar-custom navbar-fixed-top" role="navigation">
	<div class="container-fluid">
		<div class="navbar-header">
			<button type="button" class="navbar-toggle collapsed" data-toggle="collapse" data-target="#sidebar-collapse"><span class="sr-only">Toggle navigation</span>
				<span class="icon-bar"></span>
				<span class="icon-bar"></span>
				<span class="icon-bar"></span></button>
			<a class="navbar-brand" href="#"><span>Lumino</span>Admin</a>
			<ul class="nav navbar-top-links navbar-right">
				<li class="dropdown"><a class="dropdown-toggle count-info" data-toggle="dropdown" href="#"><em class="fa fa-envelope"></em><span class="label label-danger">15</span></a>
			<ul class="dropdown-menu dropdown-messages">
				<li>
					<div class="dropdown-messages-box"><a href="profile.html" class="pull-left">
						<img alt="image" class="img-circle" src="http://placehold.it/40/30a5ff/fff"></a>
							<div class="message-body"><small class="pull-right">3 mins ago</small>
								<a href="#"><strong>John Doe</strong> commented on <strong>your photo</strong>.</a>
						<br /><small class="text-muted">1:24 pm - 25/03/2015</small></div>
					</div>
				</li>
				<li class="divider"></li>
				<li>
					<div class="dropdown-messages-box"><a href="profile.html" class="pull-left">
						<img alt="image" class="img-circle" src="http://placehold.it/40/30a5ff/fff"></a>
						<div class="message-body"><small class="pull-right">1 hour ago</small>
							<a href="#">New message from <strong>Jane Doe</strong>.</a>
						<br /><small class="text-muted">12:27 pm - 25/03/2015</small></div>
					</div>
				</li>
				<li class="divider"></li>
				<li>
					<div class="all-button"><a href="#">
						<em class="fa fa-inbox"></em> <strong>All Messages</strong></a>
					</div>
				</li>
			</ul>
		</li>
		<li class="dropdown"><a class="dropdown-toggle count-info" data-toggle="dropdown" href="#">
			<em class="fa fa-bell"></em><span class="label label-info">5</span></a>
			<ul class="dropdown-menu dropdown-alerts">
				<li><a href="#">
					<div><em class="fa fa-envelope"></em> 1 New Message
						<span class="pull-right text-muted small">3 mins ago</span>
					</div>
				</a></li>
				<li class="divider"></li>
				<li><a href="#">
					<div><em class="fa fa-heart"></em> 12 New Likes
						<span class="pull-right text-muted small">4 mins ago</span>
					</div>
				</a></li>
				<li class="divider"></li>
				<li><a href="#">
					<div><em class="fa fa-user"></em> 5 New Followers
						<span class="pull-right text-muted small">4 mins ago</span>
					</div>
				</a></li>
			</ul>
		</li>
	</ul>
</div>
</div><!-- /.container-fluid -->
</nav>
```
5. Create `sidebar.html`inside templates directory according the above structure. This file will move tag `<div></div>` for sidebar from Lumino template master `index.html`
```html
<div id="sidebar-collapse" class="col-sm-3 col-lg-2 sidebar">
		<div class="profile-sidebar">
			<div class="profile-userpic">
				<img src="http://placehold.it/50/30a5ff/fff" class="img-responsive" alt="">
			</div>
			<div class="profile-usertitle">
				<div class="profile-usertitle-name">Username</div>
				<div class="profile-usertitle-status"><span class="indicator label-success"></span>Online</div>
			</div>
			<div class="clear"></div>
		</div>
		<div class="divider"></div>
		<form role="search">
			<div class="form-group">
				<input type="text" class="form-control" placeholder="Search">
			</div>
		</form>
		<ul class="nav menu">
			<li class="active"><a href="index.html"><em class="fa fa-dashboard">&nbsp;</em> Dashboard</a></li>
			<li><a href="widgets.html"><em class="fa fa-calendar">&nbsp;</em> Widgets</a></li>
			<li><a href="charts.html"><em class="fa fa-bar-chart">&nbsp;</em> Charts</a></li>
			<li><a href="elements.html"><em class="fa fa-toggle-off">&nbsp;</em> UI Elements</a></li>
			<li><a href="panels.html"><em class="fa fa-clone">&nbsp;</em> Alerts &amp; Panels</a></li>
			<li class="parent "><a data-toggle="collapse" href="#sub-item-1">
				<em class="fa fa-navicon">&nbsp;</em> Multilevel <span data-toggle="collapse" href="#sub-item-1" class="icon pull-right"><em class="fa fa-plus"></em></span>
				</a>
				<ul class="children collapse" id="sub-item-1">
					<li><a class="" href="#">
						<span class="fa fa-arrow-right">&nbsp;</span> Sub Item 1
					</a></li>
					<li><a class="" href="#">
						<span class="fa fa-arrow-right">&nbsp;</span> Sub Item 2
					</a></li>
					<li><a class="" href="#">
						<span class="fa fa-arrow-right">&nbsp;</span> Sub Item 3
					</a></li>
				</ul>
			</li>
			<li><a href="login.html"><em class="fa fa-power-off">&nbsp;</em> Logout</a></li>
		</ul>
	</div><!--/.sidebar-->
```
6. Create `footer.html` this file will movetag `<div></div>` for footer from Lumino template master `index.html`
```html
<div class="row">
    <div class="col-sm-12">
        <p class="back-link">Lumino Theme by <a href="https://www.medialoot.com">Medialoot</a></p>
    </div>
</div>
```
7. Create `script.html` this file will move tag `<script></script>`from Lumino template master `index.html` and change url for stylesheet and js is required. `js/` to `static/js/`
```html
<script src="static/js/jquery-1.11.1.min.js"></script>
<script src="static/js/bootstrap.min.js"></script>
<script src="static/js/chart.min.js"></script>
<script src="static/js/chart-data.js"></script>
<script src="static/js/easypiechart.js"></script>
<script src="static/js/easypiechart-data.js"></script>
<script src="static/js/bootstrap-datepicker.js"></script>
<script src="static/js/custom.js"></script>
<script>
	window.onload = function () {
		var chart1 = document.getElementById("line-chart").getContext("2d");
		window.myLine = new Chart(chart1).Line(lineChartData, {
		responsive: true,
		scaleLineColor: "rgba(0,0,0,.2)",
		scaleGridLineColor: "rgba(0,0,0,.05)",
		scaleFontColor: "#c5c7cc"
		});
	};
</script>
```
8. Create `dashboard.html`, this file will move tag `<div></div>` for content from Lumino master template `index.html`
```html
    <div class="panel panel-container">
			<div class="row">
				<div class="col-xs-6 col-md-3 col-lg-3 no-padding">
					<div class="panel panel-teal panel-widget border-right">
						<div class="row no-padding"><em class="fa fa-xl fa-shopping-cart color-blue"></em>
							<div class="large">120</div>
							<div class="text-muted">New Orders</div>
						</div>
					</div>
				</div>
				<div class="col-xs-6 col-md-3 col-lg-3 no-padding">
					<div class="panel panel-blue panel-widget border-right">
						<div class="row no-padding"><em class="fa fa-xl fa-comments color-orange"></em>
							<div class="large">52</div>
							<div class="text-muted">Comments</div>
						</div>
					</div>
				</div>
				<div class="col-xs-6 col-md-3 col-lg-3 no-padding">
					<div class="panel panel-orange panel-widget border-right">
						<div class="row no-padding"><em class="fa fa-xl fa-users color-teal"></em>
							<div class="large">24</div>
							<div class="text-muted">New Users</div>
						</div>
					</div>
				</div>
				<div class="col-xs-6 col-md-3 col-lg-3 no-padding">
					<div class="panel panel-red panel-widget ">
						<div class="row no-padding"><em class="fa fa-xl fa-search color-red"></em>
							<div class="large">25.2k</div>
							<div class="text-muted">Page Views</div>
						</div>
					</div>
				</div>
			</div><!--/.row-->
		</div>
		<div class="row">
			<div class="col-md-12">
				<div class="panel panel-default">
					<div class="panel-heading">
						Site Traffic Overview
						<ul class="pull-right panel-settings panel-button-tab-right">
							<li class="dropdown"><a class="pull-right dropdown-toggle" data-toggle="dropdown" href="#">
								<em class="fa fa-cogs"></em>
							</a>
								<ul class="dropdown-menu dropdown-menu-right">
									<li>
										<ul class="dropdown-settings">
											<li><a href="#">
												<em class="fa fa-cog"></em> Settings 1
											</a></li>
											<li class="divider"></li>
											<li><a href="#">
												<em class="fa fa-cog"></em> Settings 2
											</a></li>
											<li class="divider"></li>
											<li><a href="#">
												<em class="fa fa-cog"></em> Settings 3
											</a></li>
										</ul>
									</li>
								</ul>
							</li>
						</ul>
						<span class="pull-right clickable panel-toggle panel-button-tab-left"><em class="fa fa-toggle-up"></em></span></div>
					<div class="panel-body">
						<div class="canvas-wrapper">
							<canvas class="main-chart" id="line-chart" height="200" width="600"></canvas>
						</div>
					</div>
				</div>
			</div>
		</div><!--/.row-->

		<div class="row">
			<div class="col-xs-6 col-md-3">
				<div class="panel panel-default">
					<div class="panel-body easypiechart-panel">
						<h4>New Orders</h4>
						<div class="easypiechart" id="easypiechart-blue" data-percent="92" ><span class="percent">92%</span></div>
					</div>
				</div>
			</div>
			<div class="col-xs-6 col-md-3">
				<div class="panel panel-default">
					<div class="panel-body easypiechart-panel">
						<h4>Comments</h4>
						<div class="easypiechart" id="easypiechart-orange" data-percent="65" ><span class="percent">65%</span></div>
					</div>
				</div>
			</div>
			<div class="col-xs-6 col-md-3">
				<div class="panel panel-default">
					<div class="panel-body easypiechart-panel">
						<h4>New Users</h4>
						<div class="easypiechart" id="easypiechart-teal" data-percent="56" ><span class="percent">56%</span></div>
					</div>
				</div>
			</div>
			<div class="col-xs-6 col-md-3">
				<div class="panel panel-default">
					<div class="panel-body easypiechart-panel">
						<h4>Visitors</h4>
						<div class="easypiechart" id="easypiechart-red" data-percent="27" ><span class="percent">27%</span></div>
					</div>
				</div>
			</div>
		</div><!--/.row-->

		<div class="row">
			<div class="col-md-6">
				<div class="panel panel-default chat">
					<div class="panel-heading">
						Chat
						<ul class="pull-right panel-settings panel-button-tab-right">
							<li class="dropdown"><a class="pull-right dropdown-toggle" data-toggle="dropdown" href="#">
								<em class="fa fa-cogs"></em>
							</a>
								<ul class="dropdown-menu dropdown-menu-right">
									<li>
										<ul class="dropdown-settings">
											<li><a href="#">
												<em class="fa fa-cog"></em> Settings 1
											</a></li>
											<li class="divider"></li>
											<li><a href="#">
												<em class="fa fa-cog"></em> Settings 2
											</a></li>
											<li class="divider"></li>
											<li><a href="#">
												<em class="fa fa-cog"></em> Settings 3
											</a></li>
										</ul>
									</li>
								</ul>
							</li>
						</ul>
						<span class="pull-right clickable panel-toggle panel-button-tab-left"><em class="fa fa-toggle-up"></em></span></div>
					<div class="panel-body">
						<ul>
							<li class="left clearfix"><span class="chat-img pull-left">
								<img src="http://placehold.it/60/30a5ff/fff" alt="User Avatar" class="img-circle" />
								</span>
								<div class="chat-body clearfix">
									<div class="header"><strong class="primary-font">John Doe</strong> <small class="text-muted">32 mins ago</small></div>
									<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla ante turpis, rutrum ut ullamcorper sed, dapibus ac nunc.</p>
								</div>
							</li>
							<li class="right clearfix"><span class="chat-img pull-right">
								<img src="http://placehold.it/60/dde0e6/5f6468" alt="User Avatar" class="img-circle" />
								</span>
								<div class="chat-body clearfix">
									<div class="header"><strong class="pull-left primary-font">Jane Doe</strong> <small class="text-muted">6 mins ago</small></div>
									<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla ante turpis, rutrum ut ullamcorper sed, dapibus ac nunc.</p>
								</div>
							</li>
							<li class="left clearfix"><span class="chat-img pull-left">
								<img src="http://placehold.it/60/30a5ff/fff" alt="User Avatar" class="img-circle" />
								</span>
								<div class="chat-body clearfix">
									<div class="header"><strong class="primary-font">John Doe</strong> <small class="text-muted">32 mins ago</small></div>
									<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla ante turpis, rutrum ut ullamcorper sed, dapibus ac nunc.</p>
								</div>
							</li>
						</ul>
					</div>
					<div class="panel-footer">
						<div class="input-group">
							<input id="btn-input" type="text" class="form-control input-md" placeholder="Type your message here..." /><span class="input-group-btn">
								<button class="btn btn-primary btn-md" id="btn-chat">Send</button>
						</span></div>
					</div>
				</div>
				<div class="panel panel-default">
					<div class="panel-heading">
						To-do List
						<ul class="pull-right panel-settings panel-button-tab-right">
							<li class="dropdown"><a class="pull-right dropdown-toggle" data-toggle="dropdown" href="#">
								<em class="fa fa-cogs"></em>
							</a>
								<ul class="dropdown-menu dropdown-menu-right">
									<li>
										<ul class="dropdown-settings">
											<li><a href="#">
												<em class="fa fa-cog"></em> Settings 1
											</a></li>
											<li class="divider"></li>
											<li><a href="#">
												<em class="fa fa-cog"></em> Settings 2
											</a></li>
											<li class="divider"></li>
											<li><a href="#">
												<em class="fa fa-cog"></em> Settings 3
											</a></li>
										</ul>
									</li>
								</ul>
							</li>
						</ul>
						<span class="pull-right clickable panel-toggle panel-button-tab-left"><em class="fa fa-toggle-up"></em></span></div>
					<div class="panel-body">
						<ul class="todo-list">
							<li class="todo-list-item">
								<div class="checkbox">
									<input type="checkbox" id="checkbox-1" />
									<label for="checkbox-1">Make coffee</label>
								</div>
								<div class="pull-right action-buttons"><a href="#" class="trash">
									<em class="fa fa-trash"></em>
								</a></div>
							</li>
							<li class="todo-list-item">
								<div class="checkbox">
									<input type="checkbox" id="checkbox-2" />
									<label for="checkbox-2">Check emails</label>
								</div>
								<div class="pull-right action-buttons"><a href="#" class="trash">
									<em class="fa fa-trash"></em>
								</a></div>
							</li>
							<li class="todo-list-item">
								<div class="checkbox">
									<input type="checkbox" id="checkbox-3" />
									<label for="checkbox-3">Reply to Jane</label>
								</div>
								<div class="pull-right action-buttons"><a href="#" class="trash">
									<em class="fa fa-trash"></em>
								</a></div>
							</li>
							<li class="todo-list-item">
								<div class="checkbox">
									<input type="checkbox" id="checkbox-4" />
									<label for="checkbox-4">Make more coffee</label>
								</div>
								<div class="pull-right action-buttons"><a href="#" class="trash">
									<em class="fa fa-trash"></em>
								</a></div>
							</li>
							<li class="todo-list-item">
								<div class="checkbox">
									<input type="checkbox" id="checkbox-5" />
									<label for="checkbox-5">Work on the new design</label>
								</div>
								<div class="pull-right action-buttons"><a href="#" class="trash">
									<em class="fa fa-trash"></em>
								</a></div>
							</li>
							<li class="todo-list-item">
								<div class="checkbox">
									<input type="checkbox" id="checkbox-6" />
									<label for="checkbox-6">Get feedback on design</label>
								</div>
								<div class="pull-right action-buttons"><a href="#" class="trash">
									<em class="fa fa-trash"></em>
								</a></div>
							</li>
						</ul>
					</div>
					<div class="panel-footer">
						<div class="input-group">
							<input id="btn-input" type="text" class="form-control input-md" placeholder="Add new task" /><span class="input-group-btn">
								<button class="btn btn-primary btn-md" id="btn-todo">Add</button>
						</span></div>
					</div>
				</div>
			</div><!--/.col-->


			<div class="col-md-6">
				<div class="panel panel-default ">
					<div class="panel-heading">
						Timeline
						<ul class="pull-right panel-settings panel-button-tab-right">
							<li class="dropdown"><a class="pull-right dropdown-toggle" data-toggle="dropdown" href="#">
								<em class="fa fa-cogs"></em>
							</a>
								<ul class="dropdown-menu dropdown-menu-right">
									<li>
										<ul class="dropdown-settings">
											<li><a href="#">
												<em class="fa fa-cog"></em> Settings 1
											</a></li>
											<li class="divider"></li>
											<li><a href="#">
												<em class="fa fa-cog"></em> Settings 2
											</a></li>
											<li class="divider"></li>
											<li><a href="#">
												<em class="fa fa-cog"></em> Settings 3
											</a></li>
										</ul>
									</li>
								</ul>
							</li>
						</ul>
						<span class="pull-right clickable panel-toggle panel-button-tab-left"><em class="fa fa-toggle-up"></em></span></div>
					<div class="panel-body timeline-container">
						<ul class="timeline">
							<li>
								<div class="timeline-badge"><em class="glyphicon glyphicon-pushpin"></em></div>
								<div class="timeline-panel">
									<div class="timeline-heading">
										<h4 class="timeline-title">Lorem ipsum dolor sit amet</h4>
									</div>
									<div class="timeline-body">
										<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer at sodales nisl. Donec malesuada orci ornare risus finibus feugiat.</p>
									</div>
								</div>
							</li>
							<li>
								<div class="timeline-badge primary"><em class="glyphicon glyphicon-link"></em></div>
								<div class="timeline-panel">
									<div class="timeline-heading">
										<h4 class="timeline-title">Lorem ipsum dolor sit amet</h4>
									</div>
									<div class="timeline-body">
										<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit.</p>
									</div>
								</div>
							</li>
							<li>
								<div class="timeline-badge"><em class="glyphicon glyphicon-camera"></em></div>
								<div class="timeline-panel">
									<div class="timeline-heading">
										<h4 class="timeline-title">Lorem ipsum dolor sit amet</h4>
									</div>
									<div class="timeline-body">
										<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer at sodales nisl. Donec malesuada orci ornare risus finibus feugiat.</p>
									</div>
								</div>
							</li>
							<li>
								<div class="timeline-badge"><em class="glyphicon glyphicon-paperclip"></em></div>
								<div class="timeline-panel">
									<div class="timeline-heading">
										<h4 class="timeline-title">Lorem ipsum dolor sit amet</h4>
									</div>
									<div class="timeline-body">
										<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit.</p>
									</div>
								</div>
							</li>
						</ul>
					</div>
				</div>
			</div><!--/.col-->
		</div><!--/.row-->
```
9. Change `controller.py` to define templates and variables which is that will be load on `index.html` to parsing template. That will parsing `pageData` to load `dashboard.html`
```python
@app.route('/')
def index():
    pageData = {
        "breadcrumb": "Dashboard",
        "pageHeader": "Dashboard",
        "pages": "dashboard.html"
    }
    return render_template("index.html", pageData=pageData)
```
10. Change `index.html` to create templates page loader (Parsing template)
```html
<!DOCTYPE html>
<html>
<head>
	{% include "head.html" %}
</head>
<body>
	{% include "navbar.html" %}

    {% include "sidebar.html" %}

	<div class="col-sm-9 col-sm-offset-3 col-lg-10 col-lg-offset-2 main">
		<div class="row">
			<ol class="breadcrumb">
				<li><a href="#">
					<em class="fa fa-home"></em>
				</a></li>
				<li class="active">{{ pageData['breadcrumb'] }}</li>
			</ol>
		</div><!--/.row-->

		<div class="row">
			<div class="col-lg-12">
				<h1 class="page-header">{{ pageData['pageHeader'] }}</h1>
			</div>
		</div><!--/.row-->

		{% include pageData['pages'] %}

        {% include "footer.html" %}
	</div>	<!--/.main-->

	{% include "scripts.html" %}

</body>
</html>
```
11. Run the project
```
python run.py
```
12. Access `localhost:5000` according port that created in `run.py`

![Sample Dashboard](https://raw.githubusercontent.com/piinalpin/flask-project/master/Sample-templating.PNG)

13. If you want to create an Error handling, create file `404.html` inside templates directory according the above structure
```html
<!DOCTYPE html>
<html lang="en">
<head>
    {% include "head.html" %}
</head>
<body>
<div class="row">
			<div class="col-lg-6 col-lg-offset-3">
				<div class="error-page text-center">
					<h1>Error 404</h1>
					<h3>Page Not Found</h3>
					<p>The page you requested could not be found. Use your browsers Back button to navigate to the page or use the search form to find what you are looking for.</p>
					<form>
						<div class="input-group input-group-lg">
							<input type="text" placeholder="Search" class="form-control">
								<div class="input-group-btn">
									<button type="button" class="btn btn-default" tabindex="-1">
										<i class="fa fa-search"></i>
									</button>
								</div>
						</div>
					</form>
					<br/>
					<a href="index.html" class="btn btn-lg btn-primary">Return to previous page</a>
				</div>
			</div><!-- /.col-->
		</div><!-- /.row -->
{% include "scripts.html" %}
</body>
</html>
```
14. Add source code error handling in `contoller.py` in module directory
```python
@app.errorhandler(404)
def notfound(error):
    return render_template("404.html")
```
15. Run the project

16. Access `localhost:5000/dkjskdjksdekwrwr` according port that created in `run.py`

![Sample Error 404](https://raw.githubusercontent.com/piinalpin/flask-project/master/Sample-error-404.PNG)


### After change structure of flask project
```
* flask-project/
  |--- app/
  |    |--- db/
  |    |--- module/
  |    |    |--- __init__.py
  |    |    |--- controller.py
  |    |    |--- models.py
  |    |--- static/
  |    |    |--- css/
  |    |    |--- fonts/
  |    |    |--- js/
  |    |--- templates/
  |    |    |--- 404.html
  |    |    |--- dashboard.html
  |    |    |--- footer.html
  |    |    |--- head.html
  |    |    |--- index.html
  |    |    |--- login.html
  |    |    |--- navbar.html
  |    |    |--- scripts.html
  |    |    |--- sidebar.html
  |    |--- __init__.py
  |--- venv/
  |--- run.py
```

## Built With

* [Python 3](https://www.python.org/download/releases/3.0/) - The language programming used
* [Flask](http://flask.pocoo.org/) - The web framework used
* [Virtualenv](https://virtualenv.pypa.io/en/latest/) - The virtual environment used

## Clone or Download

You can clone or download this project
```
> Clone : git clone https://github.com/piinalpin/flask-project.git
```

## Authors

* **Alvinditya Saputra** - *Initial work* - [DSS Consulting](https://dssconsulting.id/) - [LinkedIn](https://linkedin.com/in/piinalpin) [Instagram](https://www.instagram.com/piinalpin) [Twitter](https://www.twitter.com/piinalpin)

