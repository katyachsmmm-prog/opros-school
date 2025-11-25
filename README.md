<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Выбор школьного питания</title>
    <style>

        /* CSS стили остаются прежними, их не трогаем */
                * {
                        margin: 0;
                        padding: 0;
                        box-sizing: border-box;
                        font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;

        }

                body {
                        background-color: #f8f8f8;
                        color: #333;
                        line-height: 1.6;

        }

                .container {
                        max-width: 900px;
                        margin: 40px auto;
                        padding: 20px;

        }

                header {
                        background-color: #2c3e50;
                        color: white;
                        padding: 25px 0;
                        text-align: center;
                        margin-bottom: 20px;

        }

                h1 {
                        font-size: 26px;
                        margin-bottom: 5px;

        }

                .description {
                        margin-bottom: 20px;
                        padding: 15px 20px;
                        text-align: center;
                        border: 1px solid #ddd;
                        background-color: #ffffff;
                        font-size: 15px;

        }

                .class-buttons {
                        display: grid;
                        grid-template-columns: repeat(auto-fit, minmax(100px, 1fr));
                        gap: 12px;
                        margin-bottom: 30px;

        }

                .class-btn {
                        background-color: #ecf0f1;
                        color: #2c3e50;
                        border: 1px solid #bdc3c7;
                        padding: 15px;
                        cursor: pointer;
                        font-size: 15px;
                        font-weight: bold;
                        transition: all 0.2s;
                        border-radius: 0;

        }

                    .class-btn:hover {
                            background-color: #bdc3c7;
                            color: #2c3e50;

        }

                    .class-btn.active {
                            background-color: #2c3e50;
                            color: white;
                            border-color: #2c3e50;
                            box-shadow: 0 0 0 2px #3498db;

        }

                #admin-btn {
                        background-color: #95a5a6 !important;
                        color: white;
                        border: none;
                        display: block;
                        width: 100%;
                        max-width: 300px;
                        margin: 20px auto 0;
                        padding: 12px;

        }

                    #admin-btn:hover {
                            background-color: #7f8c8d !important;

        }

                .question-container, .admin-panel {
                        background-color: white;
                        padding: 30px;
                        box-shadow: 0 1px 3px rgba(0,0,0,0.1);
                        margin-bottom: 25px;
                        border-radius: 0;
                        border-top: 3px solid #3498db;

        }

                .question-title {
                        margin-bottom: 20px;
                        font-size: 18px;
                        font-weight: bold;
                        color: #2c3e50;
                        border-bottom: 1px solid #eee;
                        padding-bottom: 10px;

        }

                .options-container {
                        display: flex;
                        flex-direction: column;
                        gap: 8px;

        }

                .option {
                        display: flex;
                        align-items: center;
                        padding: 12px;
                        border: 1px solid #ddd;
                        cursor: pointer;
                        transition: all 0.1s;
                        background-color: #fcfcfc;
                        border-radius: 0;

        }

                    .option:hover {
                            background-color: #f0f0f0;

        }

                    .option.selected {
                            background-color: #eaf5ff;
                            border-color: #3498db;

        }

                    .option input[type="checkbox"] {
                            -webkit-appearance: none;
                            -moz-appearance: none;
                            appearance: none;
                            width: 18px;
                            height: 18px;
                            border: 2px solid #999;
                            border-radius: 0;
                            margin-right: 15px;
                            cursor: pointer;
                            position: relative;
                            outline: none;
                            transition: border-color 0.2s, background-color 0.2s;

        }

                        .option input[type="checkbox"]:checked {
                                border-color: #2ecc71;
                                background-color: #2ecc71;

        }

                            .option input[type="checkbox"]:checked::after {
                                    content: '✔';
                                    color: white;
                                    font-size: 12px;
                                    position: absolute;
                                    top: 50%;
                                    left: 50%;
                                    transform: translate(-50%, -50%);

        }

                .submit-btn {
                        background-color: #3498db;
                        color: white;
                        border: none;
                        padding: 14px 25px;
                        border-radius: 0;
                        cursor: pointer;
                        font-size: 16px;
                        font-weight: bold;
                        display: block;
                        margin: 30px auto 0;
                        transition: background-color 0.3s;

        }

                    .submit-btn:hover {
                            background-color: #2980b9;

        }

                    .submit-btn:disabled {
                            background-color: #cccccc;
                            cursor: not-allowed;

        }

                .login-form {
                        display: flex;
                        flex-direction: column;
                        gap: 15px;
                        max-width: 350px;
                        margin: 0 auto;

        }

                    .login-form input {
                            padding: 12px;
                            border: 1px solid #ddd;
                            border-radius: 0;
                            box-shadow: inset 0 1px 2px rgba(0,0,0,0.05);

        }

                .login-btn {
                        background-color: #3498db;
                        color: white;
                        padding: 12px;
                        border-radius: 0;
                        border: none;
                        cursor: pointer;

        }

                .notification {
                        padding: 15px;
                        background-color: #d1ecf1;
                        color: #0c5460;
                        border: 1px solid #bee5eb;
                        font-weight: bold;
                        text-align: center;
                        border-radius: 0;
                        margin-bottom: 20px;

        }

                .back-btn {
                        background-color: #95a5a6;
                        color: white;
                        border: none;
                        padding: 10px 18px;
                        border-radius: 0;
                        margin-bottom: 20px;
                        cursor: pointer;

        }

                    .back-btn:hover {
                            background-color: #7f8c8d;

        }

                .results-table {
                        width: 100%;
                        border-collapse: collapse;
                        margin-top: 20px;
                        border: 1px solid #ddd;

        }

                    .results-table th {
                            background-color: #34495e;
                            color: white;
                            padding: 12px 15px;
                            text-align: left;
                            border-bottom: 2px solid #2c3e50;
                            font-weight: normal;

        }

                    .results-table td {
                            padding: 10px 15px;
                            border-bottom: 1px solid #eee;

        }

                    .results-table tr:nth-child(even) {
                            background-color: #f9f9f9;

        }

                    .results-table tr:hover {
                            background-color: #f0f0f0;

        }

                .vote-count {
                        font-weight: bold;
                        color: #3498db;

        }

                .class-results-header {
                        border-bottom: 2px solid #3498db;
                        padding-bottom: 10px;
                        margin-bottom: 15px;

        }

                .total-responses {
                        background-color: #3498db;
                        color: white;
                        padding: 5px 10px;
                        border-radius: 0;
                        display: inline-block;
                        margin-top: 5px;

        }

                .no-data {
                        text-align: center;
                        padding: 20px;
                        color: #7f8c8d;
                        font-style: italic;
                        border: 1px dashed #ccc;
                        margin-top: 15px;

        }

                .hidden {
                        display: none;

        }


    </style>
</head>
<body>
    <div class="container">
        <div id="main-page">
            <header>
                <h1>Система выбора школьного питания</h1>
                <p>Выберите ваш класс для начала опроса</p>
            </header>

            <div class="description">
                <p>Система сбора данных о предпочтениях учащихся. Выбор ограничен тремя позициями для каждого участника.</p>
            </div>

            <div class="class-buttons">
                <button class="class-btn main-class-btn" data-class="2">2 класс</button>
                <button class="class-btn main-class-btn" data-class="3">3 класс</button>
                <button class="class-btn main-class-btn" data-class="4">4 класс</button>
                <button class="class-btn main-class-btn" data-class="5">5 класс</button>
                <button class="class-btn main-class-btn" data-class="6">6 класс</button>
                <button class="class-btn main-class-btn" data-class="7">7 класс</button>
                <button class="class-btn main-class-btn" data-class="8">8 класс</button>
                <button class="class-btn main-class-btn" data-class="9">9 класс</button>
                <button class="class-btn main-class-btn" data-class="10">10 класс</button>
                <button class="class-btn main-class-btn" data-class="11">11 класс</button>
            </div>

            <button id="admin-btn" class="class-btn">🔑 Администратор</button>
        </div>

        <div id="survey-page" class="hidden">
            <button id="back-to-main" class="back-btn">← Назад</button>

            <header>
                <h1>Опрос питания для <span id="current-class"></span> класса</h1>
                <p>Выберите **до 3** вариантов питания, которые вам нравятся</p>
            </header>

            <div class="question-container">
                <div class="question-title">Какие варианты школьного питания вы предпочитаете?</div>

                <div class="options-container">
                </div>

                <button id="submit-survey" class="submit-btn" disabled>Готово</button>
            </div>
        </div>

        <div id="confirmation-page" class="hidden">
            <div class="notification">
                **Успешно.** Ваш выбор принят и сохранен. Спасибо за участие.
            </div>

            <button id="back-to-main-confirm" class="back-btn">Вернуться на главную</button>
        </div>

        <div id="error-page" class="hidden">
            <div class="notification" style="background-color: #f8d7da; color: #721c24; border-color: #f5c6cb;">
                **Ошибка.** Не удалось сохранить или загрузить данные. Проверьте подключение к интернету и URL API Google Sheets.
            </div>

            <button id="back-to-main-error" class="back-btn">Вернуться на главную</button>
        </div>

        <div id="admin-page" class="hidden">
            <button id="back-to-main-admin" class="back-btn">← На главную</button>

            <header>
                <h1>Панель администратора</h1>
                <p>Просмотр результатов опроса по классам</p>
            </header>

            <div id="login-section" class="admin-panel">
                <h2>Вход</h2>
                <form class="login-form">
                    <input type="text" id="username" placeholder="Логин" required>
                    <input type="password" id="password" placeholder="Пароль" required>
                    <button type="submit" class="login-btn">Войти</button>
                </form>
            </div>

            <div id="results-section" class="admin-panel hidden">
                <h2>Результаты опроса по классам</h2>
                <p>Выберите класс для просмотра детализации:</p>

                <div class="class-buttons">
                    <button class="class-btn admin-class-btn" data-class="2">2 класс</button>
                    <button class="class-btn admin-class-btn" data-class="3">3 класс</button>
                    <button class="class-btn admin-class-btn" data-class="4">4 класс</button>
                    <button class="class-btn admin-class-btn" data-class="5">5 класс</button>
                    <button class="class-btn admin-class-btn" data-class="6">6 класс</button>
                    <button class="class-btn admin-class-btn" data-class="7">7 класс</button>
                    <button class="class-btn admin-class-btn" data-class="8">8 класс</button>
                    <button class="class-btn admin-class-btn" data-class="9">9 класс</button>
                    <button class="class-btn admin-class-btn" data-class="10">10 класс</button>
                    <button class="class-btn admin-class-btn" data-class="11">11 класс</button>
                </div>

                <div id="results-container" class="results-container">
                </div>
            </div>
        </div>
    </div>

    <script>
        // *** НОВАЯ КОНСТАНТА API GOOGLE SHEETS ***
        const GOOGLE_APP_SCRIPT_URL = 'ВАША_ССЫЛКА_СЮДА'; // Вставьте вашу ссылку после Шага 2

        const ADMIN_USERNAME = '16';
        const ADMIN_PASSWORD = '16';

        // Данные опроса
        const foodOptions = [
            "Завтрак: Каша молочная с маслом",
            "Завтрак: Омлет с сосиской",
            "Завтрак: Блинчики с творогом",
            "Обед: Суп куриный с лапшой",
            "Обед: Борщ со сметаной",
            "Обед: Щи из свежей капусты",
            "Обед: Котлета куриная с гречкой",
            "Обед: Плов с говядиной",
            "Обед: Рыба запеченная с картофелем",
            "Полдник: Булочка с повидлом",
            "Полдник: Йогурт с печеньем",
            "Полдник: Фруктовый салат"
        ];

        // Глобальные переменные
        let currentClass = null;
        let selectedOptions = [];
        let currentActiveClassBtn = null;

        // Элементы DOM
        const mainPage = document.getElementById('main-page');
        const surveyPage = document.getElementById('survey-page');
        const confirmationPage = document.getElementById('confirmation-page');
        const errorPage = document.getElementById('error-page');
        const adminPage = document.getElementById('admin-page');
        const currentClassElement = document.getElementById('current-class');
        const optionsContainer = document.querySelector('.options-container');
        const submitSurveyBtn = document.getElementById('submit-survey');
        const adminBtn = document.getElementById('admin-btn');
        const loginForm = document.querySelector('.login-form');
        const resultsSection = document.getElementById('results-section');
        const loginSection = document.getElementById('login-section');
        const resultsContainer = document.getElementById('results-container');

        // *** ФУНКЦИИ СЕРВЕРНОГО ВЗАИМОДЕЙСТВИЯ (ТЕПЕРЬ GOOGLE SHEETS) ***

        async function fetchData() {
            if (GOOGLE_APP_SCRIPT_URL === 'ВАША_ССЫЛКА_СЮДА') {
                console.error("Ошибка: Вставьте GOOGLE_APP_SCRIPT_URL.");
                return {};
            }
            try {
                // Отправляем GET-запрос с параметром action=get
                const url = GOOGLE_APP_SCRIPT_URL + '?action=get';
                const response = await fetch(url, {
                    method: 'GET',
                });
                if (!response.ok) {
                    throw new Error(`HTTP error! status: ${response.status}`);
                }
                const data = await response.json();
                // Серверный скрипт вернет данные в виде объекта.
                return typeof data === 'object' && data !== null ? data : {};
            } catch (error) {
                console.error('Ошибка при загрузке данных (Google Sheets):', error);
                showErrorPage();
                return {};
            }
        }

        async function saveData(data) {
            if (GOOGLE_APP_SCRIPT_URL === 'ВАША_ССЫЛКА_СЮДА') {
                console.error("Ошибка: Вставьте GOOGLE_APP_SCRIPT_URL.");
                return false;
            }
            try {
                // Отправляем POST-запрос с данными
                const response = await fetch(GOOGLE_APP_SCRIPT_URL, {
                    method: 'POST',
                    // Мы отправляем action: 'save' и сами данные
                    body: JSON.stringify({
                        action: 'save',
                        data: data
                    }),
                    headers: {
                        'Content-Type': 'application/json'
                    }
                });
                if (!response.ok) {
                    throw new Error(`HTTP error! status: ${response.status}`);
                }
                const result = await response.json();
                return result.success;
            } catch (error) {
                console.error('Ошибка при сохранении данных (Google Sheets):', error);
                showErrorPage();
                return false;
            }
        }


        // *** ФУНКЦИИ УПРАВЛЕНИЯ СТРАНИЦАМИ (Остаются прежними) ***

        function hideAllPages() {
            mainPage.classList.add('hidden');
            surveyPage.classList.add('hidden');
            confirmationPage.classList.add('hidden');
            adminPage.classList.add('hidden');
            errorPage.classList.add('hidden');
        }

        function showMainPage() {
            hideAllPages();
            mainPage.classList.remove('hidden');
            selectedOptions = [];
            updateSubmitButton();
            // Сбрасываем форму входа при возврате на главную
            loginSection.classList.remove('hidden');
            resultsSection.classList.add('hidden');
            if (currentActiveClassBtn) {
                currentActiveClassBtn.classList.remove('active');
                currentActiveClassBtn = null;
            }
            resultsContainer.innerHTML = '';
        }

        function showSurveyPage() {
            hideAllPages();
            surveyPage.classList.remove('hidden');
        }

        function showConfirmationPage() {
            hideAllPages();
            confirmationPage.classList.remove('hidden');
        }

        function showErrorPage() {
            hideAllPages();
            errorPage.classList.remove('hidden');
        }

        function showAdminPage() {
            hideAllPages();
            adminPage.classList.remove('hidden');
        }

        // *** ИНИЦИАЛИЗАЦИЯ И ОБРАБОТЧИКИ (Остаются прежними) ***

        document.addEventListener('DOMContentLoaded', function () {
            document.querySelectorAll('.main-class-btn').forEach(btn => {
                btn.addEventListener('click', function () {
                    selectedOptions = [];
                    currentClass = this.getAttribute('data-class');
                    currentClassElement.textContent = currentClass;
                    showSurveyPage();
                    renderFoodOptions();
                    updateSubmitButton();
                });
            });

            document.getElementById('back-to-main').addEventListener('click', showMainPage);
            document.getElementById('back-to-main-confirm').addEventListener('click', showMainPage);
            document.getElementById('back-to-main-admin').addEventListener('click', showMainPage);
            document.getElementById('back-to-main-error').addEventListener('click', showMainPage);

            submitSurveyBtn.addEventListener('click', submitSurvey);
            adminBtn.addEventListener('click', showAdminPage);

            loginForm.addEventListener('submit', function (e) {
                e.preventDefault();
                const username = document.getElementById('username').value;
                const password = document.getElementById('password').value;

                if (username === ADMIN_USERNAME && password === ADMIN_PASSWORD) {
                    loginSection.classList.add('hidden');
                    resultsSection.classList.remove('hidden');
                    if (currentActiveClassBtn) {
                        currentActiveClassBtn.classList.remove('active');
                        currentActiveClassBtn = null;
                    }
                    resultsContainer.innerHTML = '';
                } else {
                    alert('Неверный логин или пароль');
                }
            });

            document.querySelectorAll('.admin-class-btn').forEach(btn => {
                btn.addEventListener('click', async function () {
                    if (currentActiveClassBtn) {
                        currentActiveClassBtn.classList.remove('active');
                    }
                    this.classList.add('active');
                    currentActiveClassBtn = this;

                    const classNum = this.getAttribute('data-class');
                    await showResultsForClass(classNum);
                });
            });
        });

        // *** ЛОГИКА ОПРОСА (Остается прежней) ***

        function renderFoodOptions() {
            optionsContainer.innerHTML = '';
            foodOptions.forEach((option, index) => {
                const checkboxId = `option-${currentClass}-${index}`;
                const optionElement = document.createElement('div');
                optionElement.className = 'option';
                optionElement.innerHTML = `
                            <input type="checkbox" id="${checkboxId}" data-index="${index}">
                            <label for="${checkboxId}">${option}</label>
                        `;

                const checkbox = optionElement.querySelector('input');
                checkbox.addEventListener('change', function () {
                    if (this.checked) {
                        if (selectedOptions.length < 3) {
                            selectedOptions.push(index);
                            optionElement.classList.add('selected');
                        } else {
                            this.checked = false;
                            alert('Можно выбрать не более 3 вариантов');
                        }
                    } else {
                        const optionIndex = selectedOptions.indexOf(index);
                        if (optionIndex !== -1) {
                            selectedOptions.splice(optionIndex, 1);
                            optionElement.classList.remove('selected');
                        }
                    }
                    updateSubmitButton();
                });

                optionElement.addEventListener('click', function (e) {
                    if (e.target.tagName !== 'INPUT') {
                        checkbox.click();
                    }
                });

                optionsContainer.appendChild(optionElement);
            });
        }

        function updateSubmitButton() {
            submitSurveyBtn.disabled = selectedOptions.length === 0;
        }

        // Отправка опроса (использует Google Sheets)
        async function submitSurvey() {
            if (selectedOptions.length === 0) return;
            submitSurveyBtn.disabled = true;

            // 1. Получаем текущие данные с сервера
            const currentData = await fetchData();
            const classData = currentData[currentClass] || {};

            // 2. Формируем новый ответ
            const responseId = Date.now().toString() + Math.random().toString(36).substring(2, 9);
            classData[responseId] = selectedOptions.map(index => foodOptions[index]);
            currentData[currentClass] = classData;

            // 3. Отправляем обновленные данные на сервер
            const success = await saveData(currentData);

            submitSurveyBtn.disabled = false;

            if (success) {
                showConfirmationPage();
            } else {
                // Если произошла ошибка (сбой сети, проблемы с записью на сервере)
                showErrorPage();
            }
        }

        // Показать результаты для класса (получает данные с Google Sheets)
        async function showResultsForClass(classNum) {
            resultsContainer.innerHTML = '<div>Загрузка результатов...</div>';

            // Получаем самые актуальные данные с сервера
            const allSurveyData = await fetchData();
            const classResults = allSurveyData[classNum];

            if (!classResults || Object.keys(classResults).length === 0) {
                resultsContainer.innerHTML = '<div class="no-data">Нет данных для этого класса</div>';
                return;
            }

            // Подсчет голосов
            const voteCount = {};
            foodOptions.forEach(option => {
                voteCount[option] = 0;
            });

            Object.values(classResults).forEach(selections => {
                selections.forEach(selection => {
                    if (voteCount.hasOwnProperty(selection)) {
                        voteCount[selection]++;
                    }
                });
            });

            const totalResponses = Object.keys(classResults).length;
            resultsContainer.innerHTML = '';

            const classHeader = document.createElement('div');
            classHeader.className = 'class-results-header';
            classHeader.innerHTML = `
                        <h3>Результаты для ${classNum} класса</h3>
                        <div class="total-responses">Всего ответов: ${totalResponses}</div>
                    `;
            resultsContainer.appendChild(classHeader);

            const table = document.createElement('table');
            table.className = 'results-table';

            const thead = document.createElement('thead');
            thead.innerHTML = `
                        <tr>
                            <th>Вариант питания</th>
                            <th>Количество выборов</th>
                            <th>Процент</th>
                        </tr>
                    `;
            table.appendChild(thead);

            const tbody = document.createElement('tbody');
            const sortedOptions = Object.entries(voteCount)
                .sort((a, b) => b[1] - a[1]);

            sortedOptions.forEach(([option, count]) => {
                // Процент рассчитывается относительно общего количества ОТВЕТОВ (участников), а не общего количества голосов
                const percentage = totalResponses > 0 ?
                    ((count / totalResponses) * 100).toFixed(1) : 0;

                const row = document.createElement('tr');
                row.innerHTML = `
                            <td>${option}</td>
                            <td class="vote-count">${count}</td>
                            <td>${percentage}%</td>
                        `;
                tbody.appendChild(row);
            });

            table.appendChild(tbody);
            resultsContainer.appendChild(table);
        }
    </script>
</body>
</html>
