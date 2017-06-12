# Project-3

Tutorial brief:

1 - Position images and text
2 - Add webfonts and colour fades
3 - Make it mobile and interactive
4 - Build your own business website

For this I decided to do a dog profile website with a dog breed quiz.
Not necessarily a business website but could turn it into a dog-sitting one.

Things still to do:
Change the background. It's too dull.
Any UX thoughts greatly appreciated!

Things I'm struggling with:
The fancy pop out font seems to be appearing from too far down the page.
The quiz, the functionality is there but it keeps crashing the page when it runs.
The UX of the quiz is a mess, thoughts on how to fix this would be great
Is it possible to layer more javascript in? Perhaps the 'submit' quiz button could shower the screen with stars?

I feel this should be the showcase piece and it's got someway to go still.

<!DOCTYPE html>
<head>
<script src="/assets/jquery.js"></script>
<link href="https://fonts.googleapis.com/css?family=Josefin+Sans:700|Source+Sans+Pro:600" rel="stylesheet">


<style>
    
 a {
      color: white;
    }
  ul {
      font-family: 'Source Sans Pro', sans-serif;
      text-align: right;
      padding: 10px;
      font-size: 25px;
    }
    li {
      display: inline;
      padding: 0px 10px 0px 10px;
    }
    
body {
  font-family: 'Source Sans Pro', sans-serif;
  margin: 0 auto;
  max-width: 600px;
  background: #0890ED
}
div {
  height: 200px;
  background-size: cover;
  position: relative;
  margin: 40px 0 0 0;
  border-radius: 12px;
}
h1 {
  font-family: 'Josefin Sans', sans-serif;
  text-align: center;
  font-size: 75px;
  color: white;
  margin: 60px 0 0 0;
}
h2 {
  font-family: 'Josefin Sans', sans-serif;
  text-align: center;
  color: white;
  margin: 0px 0 70px 0;
}
p {
  color: rgba(255,255,255,1);
  background: rgba(8,144,237,1);
  background: linear-gradient(bottom, rgba(0,0,0,1), rgba(0,0,0,.4));
  background: -webkit-linear-gradient(bottom, rgba(8,144,237,1), rgba(8,144,237,.4));
  background: -moz-linear-gradient(bottom, rgba(0,0,0,1), rgba(0,0,0,.4));
  padding: 10px;
  line-height: 28px;
  font-size: 22px;
  text-align: justify;
  position: absolute;
  bottom: 0;
  margin: 0;
  height: 30px;
  transition: height .5s;
  -webkit-transition: height .5s;
  -moz-transition: height .5s;
}

small {
  opacity: 0;
  font-size: 18px;
}

.show-description p {
  height: 155px;
}

.show-description small {
  opacity: 1;
}

.poppy{
  background-image: url("http://imgur.com/hIcDe5x.png");
}
.charlie{
  background-image: url("http://imgur.com/nT8InNu.png");
}
.treacle{
  background-image: url("http://imgur.com/Gzl8NJg.png");
}

.breed {
  float: right;
}
@media (max-width: 500px) {
  h1 {
    font-size: 50px;
    margin-top: 20px;
    line-height: 40px;
  }
  h2 {
    font-size: 20px;
    margin: 20px 0 30px 0;
  }
  div {
    margin: 20px 12px 0 12px;
  }
  p {
    font-size: 20px;
    line-height: 24px;
  }
  small {
    font-size: 10px;
  }
}

  
  input {
  margin: 5px 10px;
}
button {
  font-size: 20px;
  padding: 10px;
  margin: 20px 0;
  color: white;
  border: 0;
  border-radius: 10px;
  border-bottom: 3px solid #333;
}
#submit {
  background:  #ffd11a
;
}
#reset {
  background: orange;
}
#answer {
  border: 1px dashed #ccc;
  background: #eee;
  padding: 5px;
}

</style>

<header>
    <ul>
      <li><a href="#">POSTS</a></li>
      <li><a href="#">ABOUT ME</a></li>
      <li><a href="#">CONTACT</a></li>
    </ul>
    
<h1>Meet the dogs!</h1>
<h2>and find out which breed you are</h2>
</header>


<body>
<div class="poppy">
  <p>POPPY<span class="breed">Papillon</span><br />
  <small>AGE - 2yrs <br />
LOVES - Chasing balls and barking at cats. She's small but she can run and play for hours on end <br />
DISLIKES - Thunder, but she enjoy hiding under the duvet <br />
FAVOURITE FOOD - Fresh chicken, preferably warm from the oven <br />
</small></p>
</div>

<div class="charlie">
  <p>CHARLIE<span class="breed">Goldendoodle</span><br />
  <small>AGE - 4yrs <br />
LOVES - Being silly and rolling in the mud <br />
DISLIKES - When the walk is finished. Quite often he'll play hide and seek behind the trees to make it last that little bit longer  <br />
FAVOURITE FOOD - Anything <br /></p>
</div>

<div class="treacle">
  <p>TREACLE<span class="breed">Brussels Griffon</span><br />
  <small>AGE - 7yrs <br />
LOVES - Being the sophisticated lady of the gang of keeping the others in line. <br />
DISLIKES - Being left out. She'll follow you anywhere <br />
FAVOURITE FOOD - Kibble with a little bit of warm water</p>
</div>
<br />

  <div id="wrapper">
    <h1>What dog breed are you?</h1>
    <h2>Take this questionnaire to find out!</h2>

    <form id="quiz">
      
      <h2>When it comes to other people you are...</h2>
      <label><input type="radio" name="q1" value="c4">
      Everyone's best friend
    </label><br />
      <label><input type="radio" name="q1" value="c3">
      Shy at first
    </label><br />
      <label><input type="radio" name="q1" value="c2">
      Leader of the pack
    </label><br />
      <label><input type="radio" name="q1" value="c1">
      Really close to those you let in
    </label><br />
      <label><input type="radio" name="q1" value="c5">
      The one taking care of everyone
    </label>
    <br />
    <br />
    <br />

    
      <h2>Woohoo! A day off work. How will you spend it?</h2> 
      <label><input type="radio" name="q2" value="c5">
      A day off work! What's that?
    </label><br />
      <label><input type="radio" name="q2" value="c3">
      A long lie in and then who knows
    </label><br />
      <label><input type="radio" name="q2" value="c4">
      People to see, things to do
    </label><br />
      <label><input type="radio" name="q2" value="c1">
      A leisurely brunch, maybe a gallery or coffee with friends
    </label><br />
      <label><input type="radio" name="q2" value="c2">
      Cycling into town to see what's new
    </label>
    <br />
    <br />
    <br />

      <h2>What's your ideal holiday?</h2>
      <label><input type="radio" name="q3" value="c4">
      Splashing in the sea, playing in the sand
    </label><br />
      <label><input type="radio" name="q3" value="c3">
      Anything that will involve a siesta
    </label><br />
      <label><input type="radio" name="q3" value="c2">
      Dancing the night away and meeting new people
    </label><br />
      <label><input type="radio" name="q3" value="c5">
      It's all about exploration and adventure
    </label><br />
      <label><input type="radio" name="q3" value="c1">
      Discovering different cultures, as long as there's wifi
    </label>
    <br />
    <br />
    <br />

      
      <h2>When it comes to food you are...</h2> 
      <label><input type="radio" name="q4" value="c1">
      All about fine dining and gourmet
    </label><br />
      <label><input type="radio" name="q4" value="c4">
      Not fussy, anything will do
    </label><br />
      <label><input type="radio" name="q4" value="c3">
      Anything fresh and seasonal
    </label><br />
      <label><input type="radio" name="q4" value="c5">
      Always trying new recipes, especially on other people
    </label><br />
      <label><input type="radio" name="q4" value="c2">
      Never at home, there are so many new places and pop ups to try!
    </label>
    <br />
    <br />
    <br />

      
      <h2>What's your favourite season?</h2>
      <label><input type="radio" name="q5" value="c5">
      Winter, I love the snow
    </label><br />
      <label><input type="radio" name="q5" value="c1">
      It doesn't bother me, I prefer to be inside
    </label><br />
      <label><input type="radio" name="q5" value="c3">
      Autumn for the crunchy leaves and cosy evenings
    </label><br />
      <label><input type="radio" name="q5" value="c4">
      It's all about the sunshine, it makes everyone so happy
    </label><br />
      <label><input type="radio" name="q5" value="c2">
      As long as it's not raining so I can be out and about I don't mind
    </label>
    <br />
    <br />
    <br />

      <button type="submit" id="submit" onclick="tabulateAnswers()">Which dog am I?</button>
      <button type="reset" id="reset" onclick="resetAnswer()">Start again</button>
    </form>

    <div id="answer">Your result will show up here!</div>
  </div>
</body>

<script>
  $('div').on('click', function() {
      $(this).toggleClass('show-description');
  });
  </script>

function tabulateAnswers() {
  
  var c1score = 0;
  var c2score = 0;
  var c3score = 0;
  var c4score = 0;
  var c5score = 0;
  
  
  var choices = document.getElementsByTagName('input');
  
  for (i=0; i<choices.length; i++) {
   
    if (choices[i].checked) {
   
      if (choices[i].value == 'c1') {
        c1score = c1score + 1;
      }
      if (choices[i].value == 'c2') {
        c2score = c2score + 1;
      }
      if (choices[i].value == 'c3') {
        c3score = c3score + 1;
      }
      if (choices[i].value == 'c4') {
        c4score = c4score + 1;
      }
      if (choices[i].value == 'c5') {
        c5score = c5score + 1;
      }
      
    }
  }
  
 
  var maxscore = Math.max(c1score,c2score,c3score,c4score,c5score);
  
  
  var answerbox = document.getElementById('answer');
  if (c1score == maxscore) { 
    answerbox.innerHTML = "Dachshund";
  }
  if (c2score == maxscore) { 
    answerbox.innerHTML = "Border Terrier";
  }
  if (c3score == maxscore) { 
    answerbox.innerHTML = "Whippet";
  }
  if (c4score == maxscore) { 
    answerbox.innerHTML = "Labrador";
  }
  if (c5score == maxscore) { 
    answerbox.innerHTML = "St Bernard";
  }
}


function resetAnswer() {
  var answerbox = document.getElementById('answer');
  answerbox.innerHTML = "Your result will show up here!";

</script>
