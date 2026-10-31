<!DOCTYPE html>
<html lang="ru">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>Для моей Иры ❤️</title>
<style>
*{box-sizing:border-box}
body{
 margin:0;min-height:100vh;padding:25px 18px;
 background:radial-gradient(circle at top,#54234e,#170d27 65%,#090817);
 color:white;font-family:Arial,sans-serif;text-align:center;
 display:flex;justify-content:center;align-items:center;
}
.card{
 width:100%;max-width:440px;padding:30px 20px;
 background:#ffffff12;border:1px solid #ffffff25;
 border-radius:25px;box-shadow:0 15px 50px #0005;
}
h1{font-size:29px}
p{line-height:1.6;color:#f4dcec}
button{
 border:0;border-radius:15px;padding:15px 22px;
 background:#ff6fae;color:white;font-size:17px;
 font-weight:bold;margin:8px;cursor:pointer;
}
button:active{transform:scale(.96)}
#stars{font-size:38px;letter-spacing:8px;margin:20px 0}
.hidden{display:none}
.heart{font-size:75px;animation:pulse 1s infinite}
@keyframes pulse{50%{transform:scale(1.2)}}
.option{display:block;width:100%;margin:12px 0}
</style>
</head>
<body>
<div class="card">
 <div id="start">
  <div class="heart">💗</div>
  <h1>Для моей Иришки</h1>
  <p>Я приготовил для тебя маленькое приключение.<br>
  Пройди его до конца, и тебя ждёт кое-что особенное...</p>
  <button onclick="begin()">Начать приключение ✨</button>
 </div>

 <div id="game" class="hidden">
  <h1>Собери звёзды ⭐</h1>
  <p>Нажми на все пять звёздочек, чтобы открыть следующий этап.</p>
  <div id="stars">☆☆☆☆☆</div>
  <p id="count">Собрано: 0 из 5</p>
  <button onclick="collect()">Поймать звезду ✨</button>
 </div>

 <div id="question" class="hidden">
  <h1>Маленькая загадка 💕</h1>
  <p>Что становится сильнее, когда им делятся друг с другом?</p>
  <button class="option" onclick="answer(false)">Обида</button>
  <button class="option" onclick="answer(true)">Любовь ❤️</button>
  <button class="option" onclick="answer(false)">Расстояние</button>
  <p id="hint"></p>
 </div>

 <div id="final" class="hidden">
  <div class="heart">💋</div>
  <h1>Ты прошла! ❤️</h1>
  <p>
   Ну что, моя маленькая принцесса, поймала мой поцелуй? 🥹<br><br>
   Если бы я мог загадать одно желание, я бы загадал ещё тысячу дней рядом с тобой.<br><br>
   Ты моё самое любимое приключение. Я очень тебя люблю, Ира! ❤️‍🔥
  </p>
  <h2>Твой Лёшка ❤️‍🔥</h2>
  <button onclick="location.reload()">Сыграть ещё раз 💞</button>
 </div>
</div>

<script>
let collected=0;

function show(id){
 document.querySelectorAll('.card>div').forEach(x=>x.classList.add('hidden'));
 document.getElementById(id).classList.remove('hidden');
}

function begin(){show('game')}

function collect(){
 if(collected>=5)return;
 collected++;
 document.getElementById('stars').textContent='★'.repeat(collected)+'☆'.repeat(5-collected);
 document.getElementById('count').textContent='Собрано: '+collected+' из 5';
 if(collected===5){
  setTimeout(()=>show('question'),500);
 }
}

function answer(correct){
 if(correct)show('final');
 else document.getElementById('hint').textContent='Попробуй ещё раз, любимая ❤️';
}
</script>
</body> 
</html>