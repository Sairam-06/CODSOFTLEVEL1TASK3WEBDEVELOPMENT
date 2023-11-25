# CODSOFTLEVEL1TASK3WEBDEVELOPMENT
<!DOCTYPE html>
<html lang="en">
    
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Calculator</title>
    <link rel="stylesheet" type="text/css" href="style.css">
</head>
<body>
    <h1>Level 2</h1>
    <h1>Task 1: <u>CALCULATOR</u></h1>
    <br/> <br/><hr /> <br /> <br/> 

    <div id="container" class="container">
        <form name="calculator">
            <div class="wrapper">
                    <!-- Input Section -->
                <div class="InputArea">
                    <input id="inputBox" type="text" name="userInput" placeholder="0" disabled/>
                </div>
                <!-- Button Section -->
                <div class="buttons">

                    <div class="btnC btnr1">
                        <input id="ButtonC" type="button" value="C" />
                    </div>
                    <div class="btnMod btnr1">
                        <input id="Button(" type="button" value="(" />
                    </div>
                    <div class="btnSign btnr1">
                        <input id="Button)" type="button" value=")" />
                    </div>
                    <div class="btnD btnr1">
                        <input id="Button/" type="button" value="/" />
                    </div>
                    <div class="btn7 btnr2">
                        <input id="Button7" type="button" value="7" />
                    </div>
                    <div class="btn8 btnr2">
                        <input id="Button8" type="button" value="8" />
                    </div>
                    <div class="btn9 btnr2">
                        <input id="Button9" type="button" value="9" />
                    </div>
                    <div class="btnX btnr1">
                        <input id="Button*" type="button" value="x" />
                    </div>
                    <div class="btn4 btnr2">
                        <input id="Button4" type="button" value="4" />
                    </div>
                    <div class="btn5 btnr2">
                        <input id="Button5" type="button" value="5" />
                    </div>
                    <div class="btn6 btnr2">
                        <input id="Button6" type="button" value="6" />
                    </div>
                    <div class="btnM btnr1">
                        <input id="Button-" type="button" value="-" />
                    </div>
                    <div class="btn1 btnr2">
                        <input id="Button1" type="button" value="1" />
                    </div>
                    <div class="btn2 btnr2">
                        <input id="Button2" type="button" value="2" />
                    </div>
                    <div class="btn3 btnr2">
                        <input id="Button3" type="button" value="3" />
                    </div>
                    <div class="btnAdd btnr1">
                        <input id="Button+" type="button" value="+" />
                    </div>
                    <div class="btnDecimal btnr2">
                        <input id="Button." type="button" value="." />
                    </div>
                    <div class="btn0 btnr2">
                        <input id="Button0" type="button" value="0" />
                    </div>
                    <div class="btnBack btnr2">
                        <input id="Button%" type="button" value="%" />
                    </div>
                    <div class="btnEq btnr1">
                        <input id="Button=" type="button" value="=" />
                    </div>
                </div>
            </div>
        </form>
        <br/>
        <br/>
        <br/>
    </div>








-------------------------------------------->>>>>>>>.SCRIPT.JS
    window.onload = function() {
    var input = document.getElementById("inputBox");
    var container = document.getElementById("container");

    container.addEventListener("click", function(e) {
        buttonClick(e.target.id);
    });

    var calc = document.getElementById("Button=");
    calc.addEventListener("click",calculate);

    var C = document.getElementById("ButtonC");
    C.addEventListener("click", erase);

    function buttonClick(buttonId) {
        if((buttonId != "ButtonC") && (buttonId != "Button=")) {
            var button = document.getElementById(buttonId);
             var s = buttonId;
             s = s.replace("Button", "");
             entries(s);
        }
    }

    function entries(s) {
        input.value += s;
        /* button1: s = "1"
        input.value = undefined
        entries("1")
        input.value =+ s
        input.value = input.value + s = undefined + "1" = "1"
        button2 : s = "2"
        input.value ="1"
        entries("2")
        input.value = input.value + s = "1" + "2" ="12"
        */
    }

    function calculate() {
        if(input.value == ".") {
            alert("Please Enter a Mathematical Expression");
        }
        input.value = eval(input.value);
    }

    function erase() {
        input.value = "";
    }
};

    <script type="text/javascript" src="script.js"></script>
    
    
</body>

</html>  






















---------------------------------------------------->>>>>>>>>>.STYLE.CSS
* {
    padding: 0;
    margin: 0;
  }
  
  html{
      background-color: #d9f4ff;
  }
  
  hr {
      height: 2px;
      background-color: aqua;
  }
  
  h1{
      text-align: center;
      color: #42474b;
      height: 25px;
      font-size: 50px;
      padding: 35px;
  }
  
  .wrapper {
    display: grid;
    height: 600px;
    grid-template-rows: 100px 1fr;
    grid-template-columns: 1fr;
    grid-gap: 1px;
    
  }
  
  .buttons {
    display: grid;
    grid-template-rows: repeat(5, 1fr);
    grid-template-columns: repeat(4, 1fr);
    grid-gap: 4px;

  }
  
  .container {
    width: 425px;
    height: 600px;
    border: 2px solid black;
    border-radius: 10px;
    background-color: #000000;
    margin: 0 auto;
    padding: auto;
    box-shadow: 0px 0px 0px 15px rgba(0, 0, 0, 2);
  }
  
  .inputArea {
    background-color: #5b6d7c;
    grid-column: 1/2;
    display: block;
  }
  
  input[type="text"] {
    box-sizing: border-box;
    margin-top: 10px;
    margin-left: 10px;
    padding-top: 30px;
    padding-right: 38px;
    padding-bottom: 10px;
    font-size: 30px;
    background-color: rgb(218, 216, 216);
    text-align: right;
    border: 2px solid rgb(37, 37, 37);
    border-radius: 8px;
  }
/*   
  input[type=button]:hover {
    background-color: #8c8c8c;
  } */

  input[type="text"]:disabled {
    color:#000000;
  }
  
  .btnr1 {
    background: #25292c;
    text-align: center;
    width: 102px;
  }
  
  .btnr2 {
    background: #13171d;
    text-align: center;
    width: 102px;
  }
  
  .btnr1 > input {
    background: transparent;
    border: none;
    justify-content: center;
    align-self: end;
    color: white;
    font-size: 2.5em;
    margin-top: 25px;
  }
  
  .btnr2 > input {
    background: transparent;
    border: none;
    justify-content: center;
    align-self: end;
    color: white;
    font-size: 2.5em;
    margin-top: 25px;
  }
  
  .btnC > input {
    color: #ff7a00 !important;
  }

  body{
    width: 100%;
    height: 100vh;
    background: url('new\ pic.jpg')no-repeat;
    background-size: cover;
    display: flex;
    justify-content: center;
    align-items: center;
    font-size: 1rem;
  }

