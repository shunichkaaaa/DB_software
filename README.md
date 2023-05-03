# DB-2023-RestAPI

<div class="container">
  
  <div class="content">
  <h2>Короткий зміст</h2>
  <ol>
    <li><a href="#section1"> Кому буде корисним це керівництво? 🤔</a></li>
    <li><a href="#section2"> Що таке RestAPI та RestfulAPI? Різниця між ними 📲</a></li>
    <li><a href="#section3"> HTTP запити 📤</a></li>
    <li><a href="#section4"> Структура типових API та Microservice додатків 🛠</a></li>    
    <li><a href="#section5"> Приклади реалізація Restful-сервісу на мовах програмування C#, JavaScript, Python ⚙️</a></li>
    <li><a href="#section6"> Корисні посилання 🔗</a></li>
  </ol>
  </div>
  
  <div class="intro">
	<h2>Вступ</h2>
	<p> Це керівництво допоможе Вам розробити найпростіший Restful-сервіс всього за 10 хвилин! Тут зібрана уся базова інформація про структуру веб сервісу, 
	та пояснено, як користувач взаємодіє з ним через HTTP запити. Для кращої візуалізації матеріалу будуть приведенті відповідні фото та діаграми. </p>
	<p>Також, для того, щоб скористатися цим керівництвом вам потрібно становити відповідне IDE для кожної з мов програмування, а саме:</p>
	<ul>
		<li>Для C# - <a href="https://visualstudio.microsoft.com/vs/">Visual Studio(2022)</a>;</li>
		<li>Для JavaScript - Visual Studio Code;</li>
		<li>Для Python - <a href="https://www.jetbrains.com/pycharm/PythPyCharm">PyCharm</a> або Visual Studio(2022)</li>
        </ul>
    <p>Для тестування створеного Restful- сервісу має бути використана:</p>
    <ul>
        <li><a href="https://www.postman.com/downloads/">Postman API Platform</a></li>
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
	<p style="text-align:justify">API (Application Programming Interface) діють як інтерфейс між двома додатками для взаємодії та надання відповідних даних. Він використовує набір протоколів, за допомогою яких виконується операція.<i> Salesforce була першою організацією, яка офіційно запустила API, за якими слідували eBay та Amazon.</i> Крім того,<i><strong> 60% транзакцій, здійснених на eBay, використовують їх API.</strong></i> Варто зазначити, що <i><strong>майже дві третини організацій покладаються на API, і вони стали в 13 разів популярнішими з 2007 року.&nbsp;</strong></i></p>
	<p style="text-align:justify">Варто розглянути це на елементарному прикладі. Уявіть, що ви замовили посилку на відділення Нової Пошти, але там не можна відстежити прогрес доставки та місцезнаходження посилки. В цьому випадку вас буде мучити важливе екзистенційне питання - де знаходиться ваша посилка? Тут API приходить на допомогу. У цьому сценарії Нова Пошта запитує доступ до місцезнаходження вантажівки доставки від Google Maps через API, і відповідь надсилається до Нової Пошти, звідки ми можемо відстежувати місцезнаходження. API діє як посередник між двома додатками, які забезпечують взаємодію між ними.&nbsp;</p>
	<p style="text-align:justify">Отримавши базові знання про АРІ, давайте заглибимось і дізнаємось більше.</p>
	<p style="text-align:justify"><i>Але перед тим, як читати про API, давайте дізнаємось, що таке веб-сервіси і як вони пов'язані з API.</i></p>
	<p style="text-align:justify">Веб-сервіс використовує набір протоколів з відкритим кодом для обміну даними між додатками, тоді як API діє як інтерфейс між двома додатками, щоб забезпечити взаємодію між ними. Основна різниця полягає в тому, що веб-сервіс підтримує тільки протокол HTTP, тоді як API підтримує протокол HTTP/HTTPS. Веб-сервіс є одним із типів АРІ.</p>
	<blockquote>
	<p style="text-align:justify"><i><strong>❗️Важливо зазначити: Усі веб-сервіси є API, але не всі API є веб-сервісами❗️</strong></i></p>
	</blockquote>
	<p style="text-align:justify">Існують два типи веб-сервісів, які використовуються найчастіше: SOAP та REST.</p>
	<ul><li style="text-align:justify"><strong>SOAP (Simple Object Access Protocol)</strong> - це протокол, розроблений для обміну даними з безпекою програм, які створені на різних платформах або за допомогою різних мов програмування.</li><li style="text-align:justify"><strong>REST (Representational State Transfer),</strong> - це API, який дотримується набору правил, через які додатки та сервери взаємодіють. Він був спеціально розроблений для роботи з компонентами, такими як файли, об'єкти та медіа-компоненти.&nbsp;</li></ul>
	<p style="text-align:justify">REST використовує запити HTTP, такі як GET, PUT, POST та DELETE, для управління операціями CRUD (створення, читання, оновлення та видалення). Коли ви починаєте читати про REST, ви, напевно, захочете дізнатися більше про RESTful та їх різницю. Хоча REST - це набір обмежень, RESTful - це API, яке дотримується цих обмежень.&nbsp;</p>
	<p style="text-align:justify"><strong>Переваги REST API:</strong></p>
	<ul><li>REST API - легка та гнучка архітектура, яку можна легко реалізувати на будь-якій платформі або мові програмування.</li>
	<li>REST API не містить стану, що означає, що кожен запит містить всю необхідну інформацію для його виконання. Це дозволяє масштабувати додаток та зменшує навантаження на сервер.</li>
	<li>REST API широко використовується та підтримується більшістю сучасних мов програмування та фреймворків.</li>
	<li>REST API надає простий та стандартизований спосіб доступу до ресурсів через інтернет.</li></ul>
	<p><strong>Недоліки REST API:</strong></p>
	<ul><li>REST API може не бути найкращим вибором для складної бізнес-логіки та потоків роботи.</li>
	<li>REST API може бути складним у реалізації у деяких ситуаціях, особливо коли маємо справу зі складними структурами даних.</li>
	<li>REST API не надає вбудованого механізму автентифікації або авторизації, що означає, що розробники повинні реалізувати власні заходи безпеки.</li></ul>
	<p><strong>Переваги RESTful API:</strong></p>
	<ul><li>RESTful API - це стандартизована реалізація архітектури REST, що дозволяє розробникам легко будувати та підтримувати веб-сервіси.</li>
	<li>RESTful API забезпечує єдиний інтерфейс для доступу до ресурсів, що спрощує процес розробки.</li>
	<li>RESTful API підтримує кешування, що може покращити продуктивність, зменшивши кількість запитів до сервера.</li>
	<li>RESTful API можна використовувати з різноманітними форматами даних, включаючи XML та JSON.</li></ul>
	<p><strong>Недоліки RESTful API:</strong></p>
	<ul><li>RESTful API може бути не підходящим для складної бізнес-логіки та робочих потоків.</li>
	<li>RESTful API може бути складним у реалізації в певних ситуаціях, особливо при роботі з складними структурами даних.</li>
	<li>RESTful API може бути повільнішим за інші архітектури веб-сервісів, особливо при роботі з великою кількістю даних.</li></ul>
	<p><strong>Чим схожі REST API і RESTful API:</strong></p>
	<ul><li>Як REST API, так і RESTful API ґрунтуються на архітектурі REST.</li>
	<li>Як REST API, так і RESTful API є безстатевими, що означає, що кожен запит містить усю необхідну інформацію для завершення запиту.</li>
	<li>Як REST API, так і RESTful API надають простий та стандартизований спосіб доступу до ресурсів через інтернет.</li></ul>
	<p><strong>Чим відрізняються REST API і RESTful API:</strong></p>
	<table>
	<thead>
	<tr>
	<th>
	<p style="text-align:center">Фактори</p>
	</th>
	<th>
	<p style="text-align:center">REST API</p>
	</th>
	<th>
	<p style="text-align:center">RESTful API</p>
	</th>
	</tr>
	</thead>
	<tbody>
	<tr>
	<td>Визначення</td>
	<td>Розробляє API, щоб дозволити взаємодію клієнта з сервером.</td>
	<td>Веб-додаток використовує архітектуру REST, забезпечуючи взаємодію між різними системами.</td>
	</tr>
	<tr>
	<td>Робота</td>
	<td>Використовує веб-сервіси та базується на запиті та відповіді.</td>
	<td>Робота повністю базується на додатках REST.</td>
	</tr>
	<tr>
	<td>Характер</td>
	<td>Дуже пристосований та зручний для користувачів.</td>
	<td>Занадто гнучкий</td>
	</tr>
	<tr>
	<td>Протокол</td>
	<td>Міцний та більш безпечний протокол, з вбудованими архітектурними рівнями.</td>
	<td>Має транспортний протокол, менш безпечний порівняно з REST.</td>
	</tr>
	<tr>
	<td>Архітектура</td>
	<td>Має кеш, клієнт-сервер, безстанну систему з рівнями та єдиним інтерфейсом.</td>
	<td>Всі функції архітектури REST разом з деякими додатковими унікальними функціями.</td>
	</tr>
	<tr>
	<td>Формат даних</td>
	<td>Формат даних базується на HTTP.</td>
	<td>Формат даних базується на HTTP, тексті та JSON.</td>
	</tr>
	<tr>
	<td>Пропускна здатність</td>
	<td>Споживає мінімальну пропускну здатність.</td>
	<td>Споживає невелику пропускну здатність.</td>
	</tr>
	<tr>
	<td>Кеш</td>
	<td>Представляє кешовані та некешовані дані та видаляє некешовані дані, коли вони не потрібні.</td>
	<td>Клієнт може отримувати доступ до кешованої інформації в будь-який час та в будь-якому місці.</td>
	</tr>
	</tbody>
	</table>
	<p>Висновок:</p>
	<p>Хоча терміни REST API та RESTful API часто використовуються як взаємозамінні, вони мають відмінності між собою. REST API - це API, який відповідає принципам архітектури REST, тоді як RESTful API - це API, який відповідає принципам архітектури REST та задовольняє певні вимоги. Розуміння відмінностей між REST API та RESTful API є важливим для вибору правильного API для вашого веб-додатка та досягнення оптимальної продуктивності та користувацького досвіду.</p>


<!-- Розділ 3 -->
<div class="section" id="section3">
  <h3>3. HTTP запити 📤</h3>
	<p>HTTP визначає набір методів запиту, які вказують на бажану дію для вказаного ресурсу. Хоча вони також можуть бути іменниками, ці методи запиту іноді називаються HTTP-дієсловами. Кожен з них реалізує різні семантики, але деякі загальні риси спільні для групи з них, наприклад, метод запиту може бути безпечним, ідемпотентним або кешованим.</p>
	<dl>
  <dt id="get"><code>GET</code></a></dt>
  <dd>
    <p>Метод <code>GET</code> запитує представлення вказаного ресурсу. Запити, що використовують GET, повинні лише отримувати дані.</p>
  </dd>
  <dt id="head"><code>HEAD</code></a></dt>
  <dd>
    <p>Метод <code>HEAD</code> запитує відповідь, ідентичну запиту <code>GET</code>, але без тіла відповіді.</p>
  </dd>
  <dt id="post"><code>POST</code></a></dt>
  <dd>
    <p>Метод <code>POST</code> надсилає сутність на вказаний ресурс, часто спричинюючи зміну стану або побічних ефектів на сервері.</p>
  </dd>
  <dt id="put"><code>PUT</code></a></dt>
  <dd>
    <p>Метод <code>PUT</code> замінює всі поточні представлення цільового ресурсу на відане навантаження запиту.</p>
  </dd>
  <dt id="delete"><code>DELETE</code></a></dt>
  <dd>
    <p>Метод <code>DELETE</code> видаляє вказаний ресурс.</p>
  </dd>
  <dt id="connect"><code>CONNECT</code></a></dt>
  <dd>
    <p>Метод <code>CONNECT</code> встановлює тунель до сервера, ідентифікованого цільовим ресурсом.</p>
  </dd>
  <dt id="options"><code>OPTIONS</code></a></dt>
  <dd>
    <p>Метод <code>OPTIONS</code> описує варіанти зв'язку для цільового ресурсу.</p>
  </dd>
  <dt id="trace"><code>TRACE</code></a></dt>
  <dd>
    <p>Метод <code>TRACE</code> виконує тест зворотного зв'язку повідомлень вздовж шляху до цільового ресурсу.</p>
  </dd>
  <dt id="patch"><code>PATCH</code></a></dt>
  <dd>
    <p>Метод <code>PATCH</code> застосовує часткові модифікації до ресурсу.</p>
  </dd>
</dl>
<p>Усі ці методи, окрім <code>TRACE</code>, сумісні із усіма популярними десктопними браузерами та їх мобільними версіями, як от</p>
	<ul><li><strong>Chrome</strong></li>
	<li><strong>Edge</strong></li>
	<li><strong>Firefox</strong></li>
	<li><strong>Opera</strong></li>
	<li><strong>Safari</strong></li></ul>
<blockquote>
<p><strong>Функціональність методу <code>TRACE</code> зловмисники можуть використати для доступу до інформації в HTTP заголовках, таких як кукі та дані автентифікації, тому цей метод не підтримується в більшості сучасних браузерів.</strong></p>
</blockquote>


<!-- Розділ 4 -->
<div class="section" id="section4">
  <h3>4. Структура типових API та Microservice додатків 🛠</h3>
  
  
<!-- Розділ 5 -->
<div class="section" id="section5">
  <h3>5. Приклади реалізація Restful-сервісу на мовах програмування C#, JavaScript, Python ⚙️</h3>
  <details>
     <summary>Розробка REST API на C# з Entity framework core та Pomelo 🟣</summary>
  <h4>Розробка найпростішого рестфул сервіса для роботи з базою даних використовуючи мову програмування C#</h4>
  <p>1. Після встановлення Visual studio(бажано версія 2022), створюємо проєкт як показано на знімку екрану</p>
  <img src="image/section5/Csharp/1_1.jpg"/>
  <img src="image/section5/Csharp/1_2.jpg"/>
  <p>2. Обираємо саме ASP.NET Core Web API</p>
  <img src="image/section5/Csharp/2_1.jpg"/>
  <img src="image/section5/Csharp/2_2.jpg"/>
  <p>3. Обираємо такі налаштування проекту</p>
  <img src="image/section5/Csharp/3.jpg"/>
  <p>4. Після створення маємо такий стартовий пакет, який включає деякий код у контролері, стартовому файлі проекту «Program.cs» та клас-приклад “WeatherForecast.cs”, який можна сміливо видаляти, він нам не знадобиться.</p>
  <img src="image/section5/Csharp/4_1.jpg"/>
  <img src="image/section5/Csharp/4_2.jpg"/>
  <p>5. Ви можете порівняти початкові файли зі знімками на екрані</p>
	<ul>
	     <li>Перейменуємо контролер та видалимо зайве з нього.</li>
             <img src="image/section5/Csharp/5_1.jpg"/>
             <img src="image/section5/Csharp/5_2.jpg"/>
             <li>Приведіть контролер до такої початкової форми, щоб мати змогу потім будувати його без написання його з нуля.</li>
 	</ul> 
  <p>6. Почнемо підготовлювати бібліотеки які потрібна нам для безпосередньої роботи з базою даних. Тиснемо на файл проекту, та у меню обираємо кнопку «Manage NuGetPackages»</p>
  <img src="image/section5/Csharp/6.jpg"/>
  <p>7. У менеджері нугет пакетів, маємо обрати зверху вкладку Browse та встановити три пакети: Pomelo, Entity framework та Swashbuckle</p>
	<p>Pomelo – пакет який дозволяє працювати з базами даних створених за допомогою MySQL
Entity framework core – спеціальна бібліотека засобів для безпосереднього спілкування з базою (цей фреймворк перетворює код C# у SQL)
SwashBuckle – засіб для полегшення роботи програміста, пропонує нам простий юзер інтерфейс при роботі з API під назвою Swagger, дуже зручний при розробці інструмент(швидка альтернатива PostMan)
  </p>
  <img src="image/section5/Csharp/7_1.jpg"/>
  <img src="image/section5/Csharp/7_2.jpg"/>
  <img src="image/section5/Csharp/7_3.jpg"/>
  <p>8.	Спочатку для використання Swagger потрібно налаштувати стартовий файл проекту, для вашої зручності ви можете взяти код з нашого стартового файлу, та змінити декілька полів, якщо хочете дізнатись більше про конфігурацію Swagger завітайте до сайту <a href="https://swagger.io/docs/open-source-tools/swagger-ui/usage/configuration/">(Посилання)</a></p>
  <pre><code>using Microsoft.OpenApi.Models;
  var builder = WebApplication.CreateBuilder(args);
  builder.Services.AddControllers();
  builder.Services.AddEndpointsApiExplorer();
  builder.Services.AddSwaggerGen(c =>
  {
      c.SwaggerDoc("v1", new OpenApiInfo { Title = "YourProjectName", Version = "v1" });
  });
  var app = builder.Build();
  if (app.Environment.IsDevelopment())
  {
      app.UseSwagger();
      app.UseSwaggerUI();
  }
  app.UseSwagger();
  app.UseSwaggerUI(c =>
  {
      c.SwaggerEndpoint("/swagger/v1/swagger.json", "YourProjectName V1");
  });
  app.UseHttpsRedirection();
  app.UseAuthorization();
  app.MapControllers();
  app.Run();
  </code></pre>
    <p>9.	У кінці матимете ось такий файл, можете запустити проект щоб подивитись як працює swagger, нижче на знімках екрану є приклад інтерфейсу, тут ви можете використати апі які ви написали у контролері, повторюючись, ви можете робите це саме у постмані, просто таким чином матимете більш зручний інтерфейс.</p>
  <img src="image/section5/Csharp/9_1.jpg"/>
  <img src="image/section5/Csharp/9_2.jpg"/>
  <img src="image/section5/Csharp/9_3.jpg"/>
  <img src="image/section5/Csharp/9_4.jpg"/>
  <p>10. Перед початком роботи з базою, нам потрібно буде створити папку у якій будуть створені конвертовані у C# класи, об’єкти з бази даних</p>
  <img src="image/section5/Csharp/10_1.jpg"/>
  <img src="image/section5/Csharp/10_2.jpg"/>
  <p>11. Після створення папки, знаходимо у пошуковій стрічці на панелі зверху Package Manager Console</p>
  <img src="image/section5/Csharp/11.jpg"/>
  <p>12. Нам знадобиться деякий окремий модуль бібліотеки EF core під назвою Tools, вводимо таку команду у Package manager console, та після виконання рухаємось далі до підключення до бази даних</p>
  <img src="image/section5/Csharp/12_1.jpg"/>
  <img src="image/section5/Csharp/12_2.jpg"/>
  <p>13. Після встановлення інструментів EF core, стягуємо(конвертуємо) базу даних у наш проект за допомогою такої команди:</p>
  <ul>
     <li>Scaffold-DbContext "server=назва серверу;port=порт айді;database=назва бази даних(схеми);uid=Нікнейм, який використовується при вході у воркбенч;password=Пароль при вході" Pomelo.EntityFrameworkCore.MySql -OutputDir MyDBContext -f</li>
     <img src="image/section5/Csharp/13_1.jpg"/>
     <img src="image/section5/Csharp/13_2.jpg"/>
     <li>Після написання Scaffold-DbContext записуємо стрічку-підключення по сигнатурі, приведеній на знімку екрана, або написаній. Потім вводимо назву бібліотеки яка буде використовуватись при створенні контексту бази, та маркер OutPutDirectory після якого пишемо назву папки яку створили і ставимо прапорець –f для створення нової папки якщо ви забудете її створити.</li>
 	</ul>
  <p>14. Якщо ви зробили все правильно, у цій папці ви отримаєте список конвертованих об’єктів з вашої бази та контекст бази, який уособлює собою створений прототип бази, який потрібен при використанні EF для доступу до бази. Якщо ви зробили щось не так, Package Manager Console сповістить вас помилкою, яку ви можете скопіювати і знайти в інтернеті.</p>
  <img src="image/section5/Csharp/14.jpg"/>
  <p>15. Після стягування бази, потрібно додати у Program.cs</p>
  <pre><code>builder.Services.AddDbContext&lt;MydbContext&gt;();</code></pre>
  <p>Наприкінці, матимете ось такий стартовий файл: </p>
  <img src="image/section5/Csharp/15.jpg"/>
  <p>16. Для доступу до бази через контролер нам потрібно зробити деякі зміни у ньому. По-перше, почнемо з Dependency injection, та додамо контекст напряму у контролер, на знімку екрану ви можете бачити приклад ін’єкції з логером(необов’язково, використовується для логів у консоль), та самим контекстом</p>
  <img src="image/section5/Csharp/16_1.jpg"/>
  <p>Після ін’єкції ми маємо приватне поле з контекстом, до якого можемо звернутись як на знімку екрану</p>
  <img src="image/section5/Csharp/16_2.jpg"/>
  <p>Якщо у вас не працює асинхронний метод ToListAsync можете використати синхронний або просто натиснути на нього ПКМ та обрати Quick Actions and Refactorings… і натиснути на using, це додасть посилання на бібліотеку EF core яка має у собі цей метод</p>
  <img src="image/section5/Csharp/16_3.jpg"/>
  <img src="image/section5/Csharp/16_4.jpg"/>
  <p>Також, після звертання до контексту, запишіть результат у змінну використовуючи неявне оголошення var, та виведіть її у методі Ok()</p>
  <img src="image/section5/Csharp/16_5.jpg"/>
  <p>17. Після написання початкового контролеру, можемо запустити проект та спробувати використати нашу API</p>
  <img src="image/section5/Csharp/17_1.jpg"/>
  <img src="image/section5/Csharp/17_2.jpg"/>
  <p>Якщо все правильно матимете, список юзерів зі своєї бази, спробуємо отримати те саме у постмані, не вимкнувши запущений проект, відкриваємо постман і можемо скопіювати регвест зі сваггеру</p>
  <img src="image/section5/Csharp/17_3.jpg"/>
  <p>Та вставляємо його у постман </p>
  <img src="image/section5/Csharp/17_4.jpg"/>
  <p>Для більш дрібного розуміння у використанні EF core для отримання і зміни данних у таблиці, ми залишимо тут деякі посилання на офіційну документацію та наш контролер з лабораторної №6</p>
  <pre><code>using EduDBlab6.Models;
  using EduDBlab6.MyDBContext;
  using Microsoft.AspNetCore.Mvc;
  using Microsoft.EntityFrameworkCore;
  namespace EduDBlab6.Controllers
  {
      [ApiController]
      [Route("[controller]")]
      public class UserController : ControllerBase
      {
          private readonly MydbContext _context;
          public UserController(MydbContext context)
          {
              _context = context;
          }
          [HttpGet()]
          public async Task<IActionResult> GetUser()
          {
              var users = await _context.Users.ToListAsync();
              return Ok(users);
          }
          [HttpGet("id")]
          public async Task<IActionResult> GetUserById(int id)
          {
              var user = await _context.Users.Where(x => x.Id == id).FirstOrDefaultAsync();
              if (user == null)
                  throw new Exception($"User with id {id} wasn't found in the database");
              return Ok(user);
          }
          [HttpPost]
          public async Task<IActionResult> AddUser(UserRequestModel user)
          {
              var existingUser = await _context.Users.Where(x => x.Id == user.Id).FirstOrDefaultAsync();
              if (existingUser != null)
                  throw new Exception("User is not found");
              var newUser = new User()
              {
                  Id = user.Id,
                  Username = user.Username,
                  Email = user.Email,
                  Password = user.Password,
                  Avatar = user.Avatar,
                  Role = user.Role
              };
              _context.Users.Add(newUser);
              await _context.SaveChangesAsync();
              return Ok(newUser);
          }
          [HttpPut("update")]
          public async Task<IActionResult> UpdateUser(UserRequestModel user)
          {
              var existingUser = await _context.Users.Where(x => x.Id == user.Id).FirstOrDefaultAsync();
              if (existingUser == null)
                  throw new Exception("The user with such id doesn't exist");
              existingUser.Username = user.Username;
              existingUser.Email = user.Email;
              existingUser.Password = user.Password;
              existingUser.Avatar = user.Avatar;
              existingUser.Role = user.Role;
              _context.Users.Update(existingUser);
              await _context.SaveChangesAsync();
              return Ok(existingUser);
          }
          [HttpDelete("id")]
          public async Task<IActionResult> DeleteUser(int id)
          {
              var deletingUser = await _context.Users.Where(x => x.Id == id).FirstOrDefaultAsync();
              if (deletingUser == null)
                  throw new Exception("The user with such id doesn't exist");
              _context.Users.Remove(deletingUser);
              await _context.SaveChangesAsync();
              return Ok();
          }
      }
  }
  </pre></code>
  </details>
  
  <details>
     <summary>Розробка REST API на JavaScript з Node.js, MySQL та Express 🟡</summary>
  <h4>I. Створення програми Node.js</h4>
  <p> Тепер, коли ми вивчили, що таке REST, і мали швидкий огляд баз даних MySQL, давайте поринемо у створення нашого додатку RESTFul.</p>
  <p><span class="two">1.</span> По-перше, нам потрібно створити папку для нашого проекту командою нижче:</p>
  <pre><code> mkdir your-direcoty-name && cd your-direcoty-name</code></pre>
  <pre><i>	Створення нової папки для проекту</i></pre>
  <p> Наведена вище команда створить папку your-direcoty-name і змінить каталог на цю папку.</p>
  <p><span class="two">2.</span> Далі ми ініціалізуємо новий проект node.js командою нижче: </p>
  <pre><code> npm init -y</code></pre>
  <pre><i>	Ініціалізація нового проекту Node.js </i></pre>
  <p> Наведена вище команда ініціалізує новий проект Node.js, пропускаючи всі підказки для деталей проекту. Команда також створить файл package.json в кореневому каталозі нашого 
  проекту, який буде записувати всі необхідні метадані про наш проект. Ви можете вирішити пройти через підказки, щоб ввести деталі проекту, видаливши прапор '-y' з команди.</p>
  <p><span class="two">4.</span> Далі ми встановимо залежності, які нам потрібні для нашого проекту.</p>
  <pre><code> npm install express MySQL cors</code></pre>
  <pre><i>	Установка Cors</i></pre>
  <p> Наведена вище команда займе трохи часу, щоб завершитись, але в результаті будуть встановлені Express, MySQL і Cors.</p>
  <p><span class="two">5.</span> Нарешті, давайте подивимося на нашу структуру проекту. В кінці цього підручника, наша структура проекту буде виглядати так:</p>
  <img src="image/section5/JavaScript/1.jpg"/>
  <pre><p><i>	Структура проекту. </i></p></pre>
  <h4>II. Налаштування Express сервера</h4>
  <p> Тепер, коли ми встановили наші залежності, давайте налагодимо їх роботу, спочатку налаштувавши наш express сервер.</p>
  <p><span class="two">1.</span> Створіть файл app.js і додайте до нього наступний фрагмент коду нижче. Ми імпортуємо наступне:</p>
  <ul>
      <li>Express: Для створення нашого сервера.</li>
      <li>Cors: Дозволити і перенаправити ресурси запиту.</li>
      <li>Router: Саме тут наші маршрути API будуть визначені пізніше в розділах.</li>
      <li>AppError and errorHandler: Це наші глобальні функції обробки помилок. Ми створимо їх пізніше.</li>
  </ul>  
  <img src="image/section5/JavaScript/2_1.jpg"/>
  <pre><p><i>	Налаштування наших залежностей. </i></p></pre>
  <p><span class="two">2.</span> Далі ми створюємо app екземпляр з express, використовуючи express.json() middleware у нашому додатку для передачі 
  закодованого тіла URL. Нарешті, ми робимо наш API router middleware, аби слухати вхідні запити по визначеній URL.<br>
  Потім ми робимо перевірку на URL-адрес, відсутні у наших кінцевих точках, і кидаємо помилку 404 користувачеві, якщо такі знайдені. 
  Глобальний обробник помилок буде обробляти це (ми створимо його в наступних розділах).</p>
  <img src="image/section5/JavaScript/2_2.jpg"/>
  <pre><p><i> Перевірка на "спорчені" URL-адреси у кінцевих точках та направлення користувачів на 404, якщо вони є. </i></p></pre>
  <p><span class="two">3.</span> Нарешті, ми налаштуємо нашу програму для прослуховування порту 3000.</p>
  <img src="image/section5/JavaScript/2_3.jpg"/>
  <pre><p><i>	Вибір порту 3000 для нашого порту прослуховування. </i></p></pre>
  <h4>IIІ. Підключення до MySQL</h4>
  <p> Тепер у нас налаштований Express сервер. Давайте перейдемо до налаштування нашої бази даних MySQL.</p>
  <p><span class="two">1.</span> Створіть папку service у нашому кореневому каталозі проекту. У папці service створіть файл db.js і 
  додайте до нього наступні фрагменти коду нижче.</p>
  <p> <b>УВАГА!</b> назву бази даних "mydb" замініть назвою власної БД; пароль задайте також свій (який Ви задавали при встановленні MySQL)</p>
  <img src="image/section5/JavaScript/3.jpg"/>
  <pre><p><i> Підключення до бази даних MySQL методом createConnection. </i></p></pre>
  <p> Наведений вище код буде підключатися до нашої бази даних MySQL за допомогою методу MySQL createConnection. Метод createConnection приймає хост, 
  ім'я користувача, пароль і ім'я бази даних як необхідні параметри.</p>
  <h4>IV. Створення контролерів додатка</h4>
  <p> Ми успішно підключили нашу базу даних MySQL. Давайте приступимо до створення routes для нашого застосунку.</p>
  <p><span class="two">1.</span> У нашому кореневому каталозі проекту створіть папку контролерів, а потім створіть файл index.js у папці контролерів. 
  Спочатку ми імпортуємо наш глобальний обробник помилок та наше підключення до бази даних MySQL.</p>
  <img src="image/section5/JavaScript/4_1.jpg"/>
  <pre><p><i> Імпортування глобального обробника помилок. </i></p></pre>
  <p><span class="three">2.</span> Далі ми створимо наш обробник getAllUsers для отримання всіх користувачів у нашій базі даних. Цей обробник буде використовувати 
  метод запиту MySQL, який приймає SQL-запит і функцію зворотного виклику як параметри. Якщо під час операції сталася помилка, ми повернемо помилку користувачеві 
  за допомогою класу AppError. Потім ми повертаємо дані користувачеві, коли операція успішно виконується з кодом стану 200.</p>
  <img src="image/section5/JavaScript/4_2.jpg"/>
  <pre><p><i> Обробник getAllUsers. </i></p></pre>
  <p> Усі інші обробники створюємо по такому самому принципу. Нижче прикріплений весь вміст файлу index.js з папки controllers. </p>
  <pre><code>const AppError = require("../utils/appError");
const conn = require("../services/db");

exports.getAllUsers = (req, res, next) => {
  conn.query("SELECT * FROM User", function (err, data, fields) {
    if (err) return next(new AppError(err));
    res.status(200).json({
      status: "success",
      length: data?.length,
      data: data,
    });
  });
};

exports.createUser = (req, res, next) => {
  if (!req.body) return next(new AppError("No form data found", 404));
  const values = [
    req.body.username,
    req.body.email,
    req.body.password,
    req.body.Role,
  ];
  conn.query(
    "INSERT INTO User (username, email, password, Role) VALUES(?)",
    [values],
    function (err, data, fields) {
      if (err) return next(new AppError(err, 500));
      res.status(201).json({
        status: "success",
        message: "user added!",
      });
    }
  );
};

exports.getUserById = (req, res, next) => {
  if (!req.params.id) {
    return next(new AppError("No user id found", 404));
  }
  conn.query(
    "SELECT * FROM User WHERE id = ?",
    [req.params.id],
    function (err, data, fields) {
      if (err) return next(new AppError(err, 500));
      res.status(200).json({
        status: "success",
        length: data?.length,
        data: data,
      });
    }
  );
};

exports.updateUser = (req, res, next) => {
  if (!req.params.id) {
    return next(new AppError("No user id found", 404));
  }
  conn.query(
    "UPDATE User SET status='completed' WHERE id=?",
    [req.params.id],
    function (err, data, fields) {
      if (err) return next(new AppError(err, 500));
      res.status(201).json({
        status: "success",
        message: "user info updated!",
      });
    }
  );
};

exports.deleteUser = (req, res, next) => {
  if (!req.params.id) {
    return next(new AppError("No todo id found", 404));
  }
  conn.query(
    "DELETE FROM User WHERE id=?",
    [req.params.id],
    function (err, fields) {
      if (err) return next(new AppError(err, 500));
      res.status(201).json({
        status: "success",
        message: "user deleted!",
      });
    }
  );
};
</code></pre>
  <h4>V. Створення глобальних обробників помилок</h4>
  <p> Тепер давайте швидко створимо наші глобальні обробники помилок.</p>
  <p><span class="two">1.</span> Для початку створення папки utils в кореневому каталозі нашого проекту. 
  Потім створіть файли appError.js і errorHandler.js. Додайте наступний фрагмент коду до файлу appError.js:</p>
  <img src="image/section5/JavaScript/5_1.jpg"/>
  <pre><p><i> Файл appError.js. </i></p></pre>
  <p> Наведений вище код створює клас AppError, який розширює вбудований клас Error. Потім ми передамо повідомлення про помилку та статус конструктору класу Error. 
  Далі ми перевіримо, який тип помилки стався в нашій програмі з початком коду стану, і додамо помилку в трасування стека помилок.</p>
  <p><span class="three">2.</span> Далі відкрийте файл errorHandler.js і додайте фрагмент коду нижче:</p>
  <img src="image/section5/JavaScript/5_2.jpg"/>
  <pre><p><i> Файл errorHandler.js. </i></p></pre>
  <p> Наведений вище код перевірить можливі помилки в нашому додатку і відправить клієнту відповідний код помилки і стану, не ламаючи нашу програму. </p>
  <h4>VІ. Створення routes</h4>
  <p><span class="two">1.</span> У нашому кореневому каталозі проекту створіть папку routes, потім створіть файл index.js та додайте до нього наступний фрагмент коду нижче.</p>
  <img src="image/section5/JavaScript/6.jpg"/>
  <pre><p><i> Routes для застосунку. </i></p></pre>
  <p> Наведений вище код створює route object з класу express-router. Потім ми робимо наступні routes в нашому додатку.</p>
  <ul>
      <li>Get Route: щоб отримати всі користувачів в нашій базі даних.</li>
      <li>Post Route: щоб додати нового користувача в нашу базу даних.</li>
      <li>Get Route: щоб отримати користувача по його id.</li>
      <li>Put Route: оновити дані користувача по id.</li>
      <li>Delete Route: щоб вилучити користувача за ідентифікатором.</li>
  </ul>  
  <p> Потім експортуємо route object. </p>
  <h4>VІІ. Локальний запуск сервера</h4>
  <p>Аби локально запустити наш сервер , маємо написати в консолі:</p>
  <img src="image/section5/JavaScript/7.jpg"/>
  <p>При чому директорії, з якої запускаємо консоль, має бути папка з Вашою БД (замість DataBase_nodejs має бути назва Вашої директорії, яку створювали напочатку)</p>
  <h4>VІІІ. Тестування роботи API</h4>
  <p><span class="two">1.</span> Запускаємо Postman та в поле для HTTP запиту вводимо наші запити. Наприклад:</p>
  <img src="image/section5/JavaScript/8_1.jpg"/>
  <pre><p><i> Отримати усіх користувачів. </i></p></pre>
  <img src="image/section5/JavaScript/8_2.jpg"/>
  <pre><p><i> Отримати користувача по id. </i></p></pre>
  <p> Примітка: впевніться, що в розділі Headers у Вас виставлений наступний content-type header:</p>
  <img src="image/section5/JavaScript/8_3.jpg"/>
  <p> Він визначає формат обєкту, щоб серврев знав, як його передавати.</p>
  </details>
  
  
  <details>
     <summary>Розробка REST API на Python 🟢</summary>
     	<p>Посібник по створенню простого рестфул сервісу за допомогою Python бібліотек fastapi та pymysql.<br>
Після встановлення мови Python на комп’ютер та будь-якої зручної вам IDE, створюємо новий проект у будь-якій папці, та, першим ділом, встановлюємо потрібні пакети за допомогою встановщика пакетів pip, посібник по встановленню pip можете знайти за посиланням, також встановлення всього потрібного для розробки на Python ми всі проходили на першому курсі на лекціях Новотарського М.А.
</p>
     	<ol>
		<li>
			<p>Тож, перш за все, встановлюємо потрібні бібліотеки:</p>
			<img src="image/section5/Python/1.png"/>
			<img src="image/section5/Python/2.png"/>
			<p>Бібліотека uvicorn знадобиться для розгротання локального серверу з запитами.</p>
			<img src="image/section5/Python/3.png"/>
		</li>
		<li>
			<p>Наступним кроком буде прописання необхідних залежностей у коді програми для подальшого використання:</p>
			<img src="image/section5/Python/4.png"/>
		</li>
		<li>
			<p>Після цього, створюємо клас бази даних з даними по підключенню та оголошенням середовища</p>
			<pre><code>
			app = FastAPI()
			class DataBase(object):
			def __new__(cls):
				if not hasattr(cls, 'instance'):  
					cls.instance = super(DataBase, cls).__new__(cls)
				return cls.instance
			def __init__(self):
				self.connection = None
				self.cursor = None 
				self.__connect() 
			def __connect(self):
				self.connection = pymysql.connect(  
					host='хост вашого серверу, айпі або localhost',
					port=3306, - стандартний порт до бази MySql
					user='root', - ім’я юзера, по стандарту root
					password='password123', - пароль до бази який задається на початку
					database='mydb', - назва конкретної бази(scheme)
				)
				self.cursor = self.connection.cursor(pymysql.cursors.DictCursor) 
			def execute(self, command):  
				self.cursor.execute(command) 
				result = self.cursor.fetchall()
				self.connection.commit() 
				return result
			</code></pre>
		</li>	
		<li>
			<p>Після цього кроку, майже все налаштування рестфул сервісу закінчене, можемо створити просте GET request API</p>
			<pre><code>
			@app.get("/api/allusers") – Через знак собачки задається тип регвесту і посилання

			async def get_users():
				db = DataBase() – зазначене використання бази даних

				return JSONResponse(db.execute('SELECT * FROM user')) – використання SQL-коду який переводиться зі стрічки у SQL за допомогою методу execute() нашої сутності бази даних.			
			</code></pre>
		</li>	
		<li>
			<p>На цьому написання рестфул сервісу майже закінчене, щоб протестувати сервіс, потрібно запустити команду:</p>
			<pre><code>uvicorn main:app --reload</code></pre>
			<img src="image/section5/Python/5.png"/>
			<p>На знімку екрану можемо побачити що сервер розгорнувся і ми можемо звертатись до нього за посиланням http://127.0.0.1:8000 , перенесемо запит у постман і спробуємо використати ГЕТ регвест по нашій базі:</p>
			<img src="image/section5/Python/6.png"/>
		</li>	
		<li>
			<p>Таким чином використовуючи SQL код у методі execute(), можемо легко створити рестфул сервіс використовуючи python, для прикладу працюючого сервісу, прикладаємо код до нашої бази, який ви можете використати, але змінивши код під потреби свого серверу:</p>
		</li>	
	</ol>
			<pre><code>
			import fastapi
			from fastapi import FastAPI, Request
			from fastapi.responses import JSONResponse
			import pymysql
			app = FastAPI()
			class DataBase(object):
			def __new__(cls):
				if not hasattr(cls, 'instance'):
					cls.instance = super(DataBase, cls).__new__(cls)
				return cls.instance
			def __init__(self):
				self.connection = None
				self.cursor = None
				self.__connect()
			def __connect(self):
				self.connection = pymysql.connect(  
				host='localhost',  
				port=3306,           
				user='root', 
				password='urpassword123',
				database='urdbname',  
				)
				self.cursor = self.connection.cursor(pymysql.cursors.DictCursor)
			def execute(self, command): 
				self.cursor.execute(command) 
				result = self.cursor.fetchall()
				self.connection.commit() 
				return result
			@app.get("/api/allusers")
			async def get_users():
				db = DataBase() 
				return JSONResponse(db.execute('SELECT * FROM user'))
			@app.get('/api/user/{id}')
			def get_user_by_id(id):
				db = DataBase()  
				result = db.execute(f'SELECT * FROM user WHERE id={id}') 
				if not result: 
					raise fastapi.HTTPException(status_code=404)
				return JSONResponse(result)
			@app.post('/api/adduser', status_code=201)
			async def add_new_user(req: Request):  
				req_dict = await req.json() 
				try:
					username = req_dict['username']
					email = req_dict['email'] 
					password = req_dict['password'] 
					role = req_dict['Role']
				except:     
					raise fastapi.HTTPException(status_code=400)
				db = DataBase()
				db.execute(f"INSERT INTO `user`(`username`, `email`, `password`, `Role`) " 
				f"VALUES ('{username}','{email}','{password}',{role});")
				return {'message':'New user added!'}
			@app.put('/api/updateuser/{id}')
			async def update_user(id, req: Request):
				req_dict = await req.json() 
				db = DataBase()
				for key in req_dict:  
					if not db.execute(f'SELECT * FROM user WHERE id={id}'):
						raise fastapi.HTTPException(status_code=404)
					db.execute(f'UPDATE user SET {key}="{req_dict[key]}" WHERE id={id}')
				return {"message":'Updated!'}
			@app.delete('/api/deleteuser/{id}')
			def delete(id):
				db = DataBase()
				if not db.execute(f'SELECT * FROM user WHERE id={id}'):
					raise fastapi.HTTPException(status_code=404)
				db.execute(f'DELETE FROM `user` WHERE id={id}')
				return {'message':f'User with id={id} deleted'}
		</code></pre>

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
