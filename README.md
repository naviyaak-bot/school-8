# school-8
<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <title>Интерактивная Веб-страница</title>
    <style>
        /* Тег <style> для оформления (CSS) */
        :root { --main-color: #2c3e50; --accent-color: #3498db; }
        
        body { 
            font-family: sans-serif; 
            margin: 0; padding: 0; 
            background: #f4f4f4; /* Фон страницы */
            color: var(--main-color); /* Цвет текста */
        }

        /* Стилизованные заголовки */
        h1 { 
            text-align: center; 
            color: var(--accent-color); 
            text-transform: uppercase; 
            text-shadow: 2px 2px 5px rgba(0,0,0,0.1);
        }

        /* Стилизованные гиперссылки */
        a { 
            color: var(--accent-color); 
            text-decoration: none; 
            transition: 0.3s; /* Плавный переход */
        }
        a:hover { color: #e74c3c; border-bottom: 2px solid; }

        /* Блок контента */
        .container { width: 80%; margin: auto; background: white; padding: 20px; box-shadow: 0 0 10px rgba(0,0,0,0.1); }

        /* Динамический CSS-эффект и Анимация */
        .box {
            width: 100px; height: 100px; background: var(--accent-color);
            margin: 20px 0;
            animation: rotateAnim 4s infinite linear; /* CSS-анимация */
            transition: transform 0.5s; /* Динамический эффект при наведении */
        }
        .box:hover { transform: scale(1.2) rotate(15deg); cursor: pointer; }
        @keyframes rotateAnim { from { border-radius: 0%; } to { border-radius: 50%; } }

        /* Нестандартный элемент (кастомная кнопка) */
        .custom-button {
            padding: 10px 20px; background: linear-gradient(45deg, #3498db, #8e44ad);
            color: white; border: none; border-radius: 25px; font-weight: bold;
        }

        /* Фотогалерея (Flexbox) */
        .gallery { display: flex; gap: 10px; flex-wrap: wrap; margin-top: 20px; }
        .gallery img { width: 200px; height: 150px; object-fit: cover; border-radius: 8px; cursor: pointer; }

        /* Стили для видео и аудио */
        video, audio { width: 100%; max-width: 500px; display: block; margin: 10px 0; }
    </style>
</head>
<body>

    <div class="container">
        <!-- Заголовок -->
        <h1>Мой мультимедийный проект</h1>

        <!-- Навигация -->
        <nav>
            <a href="#about">О теме</a> | 
            <a href="#gallery">Галерея</a> | 
            <a href="#contacts">Контакты</a>
        </nav>

        <!-- Содержательный блок -->
        <section id="about">
            <h2>Разметка и текст</h2>
            <p>Здесь находится текст с применением различных <b>стилей</b> и <mark>маркировки</mark>.</p>
            
            <!-- Динамический элемент -->
            <div class="box"></div>

            <!-- Изображение-карта (Map) -->
            <h3>Изображение-карта</h3>
            <img src="https://placeholder.com" usemap="#workmap" alt="Карта">
            <map name="workmap">
                <area shape="rect" coords="34,44,270,350" alt="Сектор 1" href="https://google.com">
            </map>
        </section>

        <!-- Мультимедиа -->
        <section>
            <h3>Мультимедиа (Видео и Аудио)</h3>
            <video controls>
                <source src="movie.mp4" type="video/mp4"> Ваш браузер не поддерживает видео.
            </video>
            <audio controls>
                <source src="audio.mp3" type="audio/mpeg"> Ваш браузер не поддерживает аудио.
            </audio>
        </section>

        <!-- Интерактив и JS -->
        <section>
            <h3>Интерактивные элементы и JS</h3>
            <button class="custom-button" onclick="jsAnimation()">Запустить JS-анимацию</button>
            <div id="jsBox" style="width:50px; height:50px; background:red; margin-top:10px; position:relative;"></div>
        </section>

        <!-- Фотогалерея -->
        <section id="gallery">
            <h3>Фотогалерея</h3>
            <div class="gallery">
                <img src="https://placeholder.com" alt="Фото 1">
                <img src="https://placeholder.com" alt="Фото 2">
                <img src="https://placeholder.com" alt="Фото 3">
            </div>
        </section>

        <!-- Внешний код (Опрос) -->
        <section>
            <h3>Опрос (Внешний код)</h3>
            <div id="poll-container">
                <!-- Сюда обычно вставляется скрипт от Google Forms или SurveyMonkey -->
                <p><i>Здесь загружается внешний виджет опроса...</i></p>
            </div>
        </section>

        <!-- Контакты -->
        <section id="contacts">
            <h3>Страница контактов</h3>
            <form>
                <input type="text" placeholder="Ваше имя"><br><br>
                <input type="email" placeholder="Email"><br><br>
                <button type="submit">Отправить</button>
            </form>
        </section>
    </div>

    <!-- JavaScript сценарии -->
    <script>
        // JS-анимация
        function jsAnimation() {
            let elem = document.getElementById("jsBox");   
            let pos = 0;
            let id = setInterval(frame, 5);
            function frame() {
                if (pos == 350) {
                    clearInterval(id);
                } else {
                    pos++; 
                    elem.style.left = pos + 'px'; 
                }
            }
        }

        // Пример простого интерактивного сценария
        document.querySelector('.custom-button').addEventListener('mouseover', () => {
            console.log("Пользователь хочет нажать на кнопку");
        });
    </script>
</body>
</html>
