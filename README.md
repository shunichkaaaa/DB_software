# DB-2023-RestAPI

<div class="container">
  
  <div class="content">
  <h2>Короткий зміст</h2>
  <ol>
    <li><a href="#section1"> Кому буде корисним цей гайд? 🤔</a></li>
    <li><a href="#section2"> Що таке RestAPI та RestfulAPI? Різниця між ними 📲</a></li>
    <li><a href="#section3"> HTTP запити 📤</a></li>
    <li><a href="#section4"> Структура типових API та Microservice додатків 🛠</a></li>    
    <li><a href="#section5"> Приклади реалізація Restful-сервісу на мовах програмування C#, JavaScript, Python ⚙️</a></li>
	<li><a href="#section6"> Корисні посилання 🔗</a></li>
  </ol>
  </div>
  <div class="intro">
	<h2>Вступ</h2>
	<p> Цей гайд допоможе Вам розробити найпростіший Restful-сервіс всього за 10 хвилин! Тут зібрана уся базова інформація про структуру веб сервісу, 
	та пояснено, як користувач взаємодіє з ним через HTTP запити. Для кращої візуалізації матеріалу будуть приведенті відповідні фото та діаграми. </p>
	<p>Також, для того, щоб скористатися цим гайдом вам потрібно становити відповідне IDE для кожної з мов програмування, а саме:</p>
	<ul>
		<li>Для C# - Visual Studio(2022);</li>
		<li>Для JavaScript - Visual Studio Code;</li>
		<li>Для Python - PythPyCharm або Visual Studio(2022);</li>
	</ul>
  </div>
</div>

<!-- Розділ 1 -->
<div class="section" id="section1">
  <h3>1. Кому буде корисним цей гайд? 🤔</h3>
  <p>Наш посібник буде корисним насамперед back-end розробникам та людям, які прагнуть до нових знань. Це також може бути цікаво викладачу, та 
  взагалі буть-кому, хто цікавиться методами взаємодії з Restful services та базами даних. Дізнаватись щось нове завжди приємно!😋</p>

<!-- Розділ 2 -->
<div class="section" id="section2">
  <h3>2. Що таке RestAPI та RestfulAPI? Різниця між ними 📲</h3>

<!-- Розділ 3 -->
<div class="section" id="section3">
  <h3>3. HTTP запити 📤</h3>

<!-- Розділ 4 -->
<div class="section" id="section4">
  <h3>4. Структура типових API та Microservice додатків 🛠</h3>


<!-- Розділ 5 -->
<div class="section" id="section5">
  <h3>5. Приклади реалізація Restful-сервісу на мовах програмування C#, JavaScript, Python ⚙️</h3>
  <details>
     <summary>Розробка REST API на C# з Entity framework core та Pomelo 🟣</summary>
  <p><span class="two">1.1</span> </p>
  <img src="image/section5/C#/1_1.jpg"/>
  <p><span class="two">1.2</span> </p>
  <img src="image/section5/C#/1_2.jpg"/>
  <p><span class="two">1.3</span> </p>
  <img src="image/section5/C#/2_1.jpg"/>
  <p><span class="two">1.4</span> </p>
  <img src="image/section5/C#/2_2.jpg"/>
  <p><span class="two">1.5</span> </p>
  <img src="image/section5/C#/3.jpg"/>
  </details>
  <details>
     <summary>Розробка REST API на JavaScript з Node.js, MySQL та Express 🟡</summary>
  <h4>I. Створення програми Node.js</h4>
  <p><span class="two">1.</span> Тепер, коли ми вивчили, що таке REST, і мали швидкий огляд баз даних MySQL, 
  давайте поринемо у створення нашого додатку RESTFul. По-перше, нам потрібно створити папку для нашого проекту з командою нижче:</p>
  <pre><code> mkdir your-direcoty-name && cd your-direcoty-name</code></pre>
  <i> Створення нової папки для проекту </i>
  <p> Наведена вище команда створить папку your-direcoty-name і змінить каталог на цю папку. Далі ми ініціалізуємо новий проект node.js командою нижче: </p>
  <pre><code> npm init -y</code></pre>
  <p><span class="two">2.</span> Нарешті, давайте подивимося на нашу структуру проекту. В кінці цього підручника, наша структура проекту буде виглядати так:</p>
  <img src="image/section5/JavaScript/1.jpg"/>
  <p><span class="two">3.</span> </p>
  <img src="image/section5/Python/17_4.jpg"/>
  <p><span class="two">4.</span> </p>
  <img src="image/section5/JavaScript/2_2.jpg"/>
  <p><span class="two">5.</span> </p>
  <img src="image/section5/JavaScript/2_3.jpg"/>
  </details>
  <details>
     <summary>Розробка REST API на Python 🟢</summary>
  <p><span class="two">1.1</span> </p>
  <img src="image/section5/Python/17_4.jpg"/>
  <p><span class="two">1.2</span> </p>
  <img src="image/section5/Csharp/1_2.jpg"/>
  <p><span class="three">1.3</span> </p>
  <img src="image/section5/Python/1_3.png"/>
  <p><span class="three">1.4</span> </p>
  <img src="image/section5/Python/1_4.png"/>
  <p><span class="three">1.5</span> </p>
  <img src="image/section5/Python/1_5.png"/>
  </details>
</div>


<div class="section" id="section6">
  <h3>6. Корисні посилання 🔗</h3>
  <ol>
	<li><a href="https://dev.mysql.com/downloads/mysql/">Завантаження MySQL Universal Installer</a></li>
	<li><a href="https://www.youtube.com/playlist?list=PLXr7EDDqEOkYiUDqyM3yMg4K2abjEyagl">Плейліст лекцій БД 2023</a></li>
	<li><a href="https://github.com/YehorSeniuk/IOO">Репозиторій проекту IOO</a></li>
	<li><a href="https://yehorseniuk.github.io/IOO/">Gh-pages проекту IOO</a></li>
  </ol>
</div>

