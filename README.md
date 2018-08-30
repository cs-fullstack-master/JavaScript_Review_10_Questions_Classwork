# JavaScript_Review_10_Questions_Classwork

### JavaScript String Literals

What will the output from the JavaScript below using string literals be?
```
let theAnswer = 2112;
let str = `The answer to the ultimate question: {theAnswer}`;
alert(str);
```
An alert box that displays 'The answer to the ultimate question: 2112'

An alert box that displays 'Undefined'

An alert box that displays 'The answer to the ultimate question: {theAnswer}'


<hr/>

### Execution Context

Given the following code:

```
function goDoIt(doWhat) {
    alert(`Just go and do ${doWhat}`);
}

slacker =
{
    whatDoYouDo : "Same as you do!",
    goDoIt : function() {
        alert();
    }
}

slacker.goDoIt("Get a job!");

```

* What will the result of the JavaScript code be?

An alert box with an empty message

An alert box saying "Get a Job!"

No alert dialog box but an error instead

<hr/>

### Try/Catch/Throw

The experimentWithTries() function in the following HTML page throws and catches exceptions:

```
<!DOCTYPE html>
<html>
<head>
    <title>Intro to JavaScript</title>
	<meta charset=&quot;utf-8&quot; />
</head>
<body>
    <script>
        experimentWithTries();

        function experimentWithTries() {
            try {
                try {
                    console.log('Starting the process...');
                    throw new Error('Something went wrong');
                    console.log('Ending the process...');
                }
                catch (ex) {
                    console.log(ex);
                    throw new Error(ex);
                }
                finally {
                    console.log('The inner finally block')
                }
            }
            catch (ex) {
                console.log(ex);
            }
            finally {
                console.log('The outer finally block')
            }
            console.log('Glad to be done!');
        }
    </script>
</body>
</html>
```

* What will be displayed in the console when the page is loaded in the browser?


Starting the process...  
Error: Something went wrong
The inner finally block  
Error: Error: Something went wrong
The outer finally block  
Glad to be done!


Starting the process...  
Error: Something went wrong 
Error: Error: Something went wrong
The outer finally block  
Glad to be done!


Starting the process...  
Error: Something went wrong
Ending the process...
The inner finally block  
Error: Error: Something went wrong
The outer finally block  
Glad to be done!


<hr/>

### Input/Confirm (undefined/null)

An HTML page contains the following:

```
<!DOCTYPE html>
<html>
<head>
    <title>Intro to JavaScript</title>
	<meta charset="utf-8" />
</head>
<body>
    <script>
        do {
            var input = prompt("Enter a value");
            var acceptable = confirm("Continue?");
            var theType = determineType(input);
            console.log("The type is: " + theType);
        } while (acceptable)

        function determineType(input) {
            if (!input)
                return 'undefined';
            switch (input.constructor) {
                case String: return "string with value '" + input + "'";
                case Number: return "number with value " + input;
                case Date: return "date with value " + input;
                case RegExp: return "regular expression with value " + input;
            }
        }
    </script>
</body>
</html>
```

* You load the page in the browser, and you enter these values before canceling out of the confirm dialog: test, 5, and 8/11/2017.

* What will be displayed in the console window?

The type is: undefined
The type is: undefined
The type is: undefined

The type is: string with value 'test'  
The type is: number with value 5  
The type is: date with value 8/11/2017  

The type is: string with value 'test'  
The type is: string with value '5'  
The type is: string with value '8/11/2017'  


<hr/>

### Typeof/null/undefined/hoisting

You have the following HTML page:

```
<!DOCTYPE html>
<html>
<head>
         <title>Intro to JavaScript</title>
          	<meta charset="utf-8" />
</head>
<body>
         <div id="result"></div>
         <script>
                  function doOperation() {
                           document.getElementById("result").innerHTML = languageName;
                           languageName = "JavaScript";
                           var languageName;
                           var fullName = ' ';
                           if (languageName === 'JavaScript')
                                    fullName = "Intro to " + languageName
                           else
                                    fullName = "Class Not Created Yet!";

                           console.log(fullName);
                  }

                  doOperation();
         </script>
</body>
</html>
```

* What will be displayed on the screen when the page is loaded in the browser?

Intro to JavaScript

null

undefined

Nothing because an error will display in the console


<hr/>

### HTML5 Form Elements how fields are submitted

You have the following form (assume it's loaded from http://localhost:35132/Account/FormTest)

```
<form method="get">
         <div>
                  <label for="first">First Name:</label>
                  <input type="text" id="first" name="firstName">
         </div>
         <div>
                  <label for="Id">Last Name:</label>
                  <input type="text" id="last" name="lastName">
         </div>
         <div>
                  <input type="submit" value="Submit">
         </div>
 </form>
```

* A user fills out the form with 'John' in the first name and 'Doe' in the last name.

* Which URL will the form submit?


http://localhost:35132/Account/FormTest

http://localhost:35132/Account/FormTest?firstName=John&lastName=Doe

http://localhost:35132/Account/FormTest?first=John&last=Doe

http://localhost:35132/Account/FormTest/GET/#first=John?last=Doe

<hr/>

### HTML5 Form Elements how fields are submitted

You are redesigning the form for the enrollment section of a college website. One of the elements on the page is the SAT score.

You need to choose the best input type to use for this element.

* What is the BEST input type to use for values like an SAT score?

text
select box
number
range

<hr/>

### Extra on Array Functions: sort, filter, forEach

You load the following page:

```
<!DOCTYPE html>
<html>
<head>
         <title>Intro to JavaScript</title>
          	<meta charset="utf-8" />
</head>
<body>
         <script>
                  var functionKeys = ["F1", "F2", "F5", "F3", "F7", "F6", "F9", "F8"];
                  var result = ' ';

                  function func1(key) {
                           switch (key) {
                                    case "F1":
                                             result += "F1";
                                    case "F2":
                                             result += "F2";
                                    case "F3":
                                             result += "F3";
                                    case "F4":
                                             result += "F4";
                                    case "F5":
                                             result += "F5";
                           }
                  }

                  functionKeys.forEach(function (k) { func1(k) });
                  console.log(result);
         </script>
</body>
</html>

```
* What will result contain?

F1F2F3F4F5F2F3F4F5F5F3F4F5

F1F2F3F5F2F3F5F5F3F5

F1F2F3F5

F1F2F5F3


<hr/>

### Let and Const

The body of an HTML page contains the following code: 

```
<div id="result" class="format-output"></div>
         <script>
                  const student_count = 24;
                  document.getElementById("result").innerHTML = getGradesList();

                  function getGradesList() {
                           student_count = 30;
                           let gradesList = ' ';
                           for (var i = 0; i < student_count; i++) {
                                    gradesList += getRandomGrade() + ' ';
                           }
                           return gradesList;
                  }

                  function getRandomGrade() {
                           const grades = "ABCDF";
                           return grades.charAt(Math.floor(Math.random() * grades.length));
                  }
         </script>

```

* What will be displayed on the screen when this page is previewed in the browser?

An error message

A list of random letters between A and F

A list of empty spaces

A list of random letters


<hr/>

### Events

You load the following page in the browser:
```
<!DOCTYPE html>
<html>
<head>
         <title>Intro to JavaScript</title>
          	<meta charset="utf-8" />
</head>
<body>
         <div onclick="takeAction()">
                  <div onclick="takeAction()">
                           <p onclick="takeAction()">There are many variations of passages of Lorem Ipsum available.</p>
                  </div>
         </div>
         <div id="result"></div>
         <script>
                  var count = 1;
                  function takeAction() {
                           document.getElementById("result").innerHTML = count++;
                  }
         </script>
</body>
</html>
```
* You click on the text in the paragraph three times.

* What gets displayed in the div with id result after the consecutive clicks?


246

369

111

123
