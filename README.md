<!DOCTYPE html>
<html lang="ru">
<head>
  <meta charset="UTF-8">
  <title>100 английских слов</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f5f5f5;
      margin: 0;
      padding: 20px;
      text-align: center;
    }

    h1 {
      margin-bottom: 20px;
    }

    .grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(120px, 1fr));
      gap: 15px;
    }

    .card {
      perspective: 1000px;
      cursor: pointer;
    }

    .inner {
      position: relative;
      width: 100%;
      height: 100px;
      transition: transform 0.6s;
      transform-style: preserve-3d;
    }

    .card.flipped .inner {
      transform: rotateY(180deg);
    }

    .front, .back {
      position: absolute;
      width: 100%;
      height: 100%;
      display: flex;
      align-items: center;
      justify-content: center;
      border-radius: 10px;
      backface-visibility: hidden;
      font-size: 16px;
      padding: 10px;
      box-sizing: border-box;
    }

    .front {
      background: #4CAF50;
      color: white;
    }

    .back {
      background: #2196F3;
      color: white;
      transform: rotateY(180deg);
    }
  </style>
</head>
<body>

<h1>100 популярных английских слов</h1>

<div class="grid" id="grid"></div>

<script>
const words = [
["time","время"],["person","человек"],["year","год"],["way","способ"],["day","день"],
["thing","вещь"],["man","мужчина"],["world","мир"],["life","жизнь"],["hand","рука"],
["part","часть"],["child","ребёнок"],["eye","глаз"],["woman","женщина"],["place","место"],
["work","работа"],["week","неделя"],["case","случай"],["point","точка"],["government","правительство"],
["company","компания"],["number","число"],["group","группа"],["problem","проблема"],["fact","факт"],
["be","быть"],["have","иметь"],["do","делать"],["say","сказать"],["get","получить"],
["make","создавать"],["go","идти"],["know","знать"],["take","брать"],["see","видеть"],
["come","приходить"],["think","думать"],["look","смотреть"],["want","хотеть"],["give","давать"],
["use","использовать"],["find","находить"],["tell","рассказывать"],["ask","спрашивать"],["work","работать"],
["seem","казаться"],["feel","чувствовать"],["try","пытаться"],["leave","уходить"],["call","звать"],
["good","хороший"],["new","новый"],["first","первый"],["last","последний"],["long","длинный"],
["great","великий"],["little","маленький"],["own","свой"],["other","другой"],["old","старый"],
["right","правильный"],["big","большой"],["high","высокий"],["different","разный"],["small","маленький"],
["large","большой"],["next","следующий"],["early","ранний"],["young","молодой"],["important","важный"],
["few","несколько"],["public","публичный"],["bad","плохой"],["same","тот же"],["able","способный"],
["to","к"],["of","из"],["in","в"],["for","для"],["on","на"],
["with","с"],["at","в"],["by","по"],["from","от"],["up","вверх"],
["about","о"],["into","внутрь"],["over","над"],["after","после"],["beneath","под"],
["under","под"],["above","над"]
];

// гарантируем ровно 100 карточек
const grid = document.getElementById('grid');

words.slice(0,100).forEach(([en, ru]) => {
  const card = document.createElement('div');
  card.className = 'card';

  card.innerHTML = `
    <div class="inner">
      <div class="front">${en}</div>
      <div class="back">${ru}</div>
    </div>
  `;

  card.addEventListener('click', () => {
    card.classList.toggle('flipped');
  });

  grid.appendChild(card);
});
</script>

</body>
</html>
