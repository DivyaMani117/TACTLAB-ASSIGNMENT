# TACTLAB-ASSIGNMENT
#!python3

from flask import Flask, request, render_template

app = Flask(__name__)

@app.route('/potato')
def welcome():
    return 'This is my first Flask! Yay!'

@app.route('/')
def rootpage():
    return render_template("index.html")
    
@app.route('/tactlab')
def tactlabpage():
    return 'This is my tactlab assignment!'
    
@app.route('/method', methods=['GET'])
def method():
    if request.method == 'POST':
        return "You've used a POST request!"
    else:
        return "I reckon you're probably using a GET request!"

app.run()
