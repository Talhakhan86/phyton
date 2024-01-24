# Creating the Flask Obejct (WSGI)
app = Flask(__name__)

# Creating the First Decorator
@app.route('/')
def printHome():
    return "Creating the Dynamically URL in Flask"

# Creating the Second Decorator
@app.route('/pass/<int:score>')
def printPass(score):
    return "You're passed and your score is : {}".format(score)

# Creating the Third Decorator
@app.route('/fail/<int:score>')
def printFail(score):
    return "You're Failed and your score is : {}".format(score)

# Creating the Fourth Decorator
@app.route('/result/<int:marks>')
def printResult(marks):
    result = ""
    if marks >= 60:
        result = "printPass"
    else:
        result = "printFail"
    return redirect(url_for(result , score = marks)) 


# Main Part
if __name__ == "__main__":
    app.run()
