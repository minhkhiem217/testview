<p id="message">Number Guessing Game in HTML</p>
<input id="number" />
<button onclick="myFunction()">Button</button>
<h4 id="pastResult">PAST RESULT</h4>

<script>
    var min = 1;
    var max = 100;
    var yourRandomNumber = Math.ceil(Math.random() * (+max - + min )) + +min;
    var pastResult = '';
    var count = 10;
    //alert(yourRandomNumber);

    function myFunction(){
        if(count == 1){
            alert('You lose. your correct number is '+ yourRandomNumber+',Please retry');
            location.reload();
        }
        var yourInput = document.getElementById('number').value;
        if(yourInput == yourRandomNumber){
            document.getElementById('message').innerHTML = 'WOW Correct :v';
            document.getElementById('message').style.backgroundColor = '#33ff33';
        }
        else if(yourInput < yourRandomNumber){
            count--;
            document.getElementById('message').innerHTML = 'Your number is too low. You have '+ count +' :D';
            document.getElementById('message').style.backgroundColor = '#ff3333';
        }
        else if(yourInput > yourRandomNumber){
            count--;
            document.getElementById('message').innerHTML = 'Your number is too high. You have '+ count +' :D';
            document.getElementById('message').style.backgroundColor = '#ff3333';
        }
        pastResult = pastResult + yourInput + '<br>';
        document.getElementById('pastResult').innerHTML = pastResult;
    }

</script>