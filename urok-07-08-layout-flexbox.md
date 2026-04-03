# Урок 7-8. Збираємо повноцінну вебсторінку (HTML + CSS)

## Для кого цей матеріал
- Вік: 10–13 років
- Рівень: початковий
- Формат: 40% коротке нагадування, 60% практика
- Технології: `HTML` + `CSS`

---

## Мета уроку

На цьому уроці учні:
- використають уже знайомі теги структури сторінки;
- застосують уже відомі `Flexbox` або `Grid` для розміщення блоків;
- навчаться збирати не окремі елементи, а цілу сторінку;
- створять мінісайт з меню, інформаційними блоками та картками.

---

## Частина 1. Коротке нагадування

На попередніх уроках ми вже знайомилися з:
- основною структурою HTML-сторінки;
- тегами `header`, `main`, `section`, `footer`;
- базовим оформленням через `CSS`;
- розміщенням елементів через `Flexbox` або `Grid`.

Тому на цьому уроці ми не вчимо це заново, а **використовуємо все разом**, щоб зібрати справжню вебсторінку.

Головна ідея уроку:
> не окремі теги заради тегів, а готова сторінка, яка виглядає як маленький сайт.

---

## Частина 2. Яку сторінку будемо збирати

На уроці учень створює одну завершену сторінку.

У ній мають бути:
- шапка сайту;
- меню;
- головний інформаційний блок;
- секція з картками;
- нижня частина сторінки.

### Варіанти теми сторінки
- Моя улюблена гра
- Моє хобі
- Моя тварина
- Моя команда супергероїв
- Мій мінісайт про Minecraft / Roblox / Brawl Stars

---

## Частина 3. План сторінки

Перед тим як писати код, корисно уявити сторінку як набір блоків.

### Схема сторінки
- `header` — назва сайту + меню
- `main`
  - перша `section` — короткий опис
  - друга `section` — картки
- `footer` — підпис або контакти

---

## Частина 4. Збираємо основу сторінки

### `index.html`
```html
<!DOCTYPE html>
<html lang="uk">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Мій мінісайт</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <header class="site-header">
        <h1>Мій мінісайт</h1>
        <nav class="menu">
            <a href="#about">Про мене</a>
            <a href="#cards">Цікаве</a>
            <a href="#footer">Контакти</a>
        </nav>
    </header>

    <main class="container">
        <section id="about" class="hero">
            <h2>Ласкаво прошу!</h2>
            <p>Це моя навчальна вебсторінка, яку я створив за допомогою HTML та CSS.</p>
        </section>

        <section id="cards" class="cards-section">
            <h2>Мої улюблені речі</h2>
            <div class="cards">
                <div class="card">
                    <h3>Картка 1</h3>
                    <p>Тут короткий опис.</p>
                </div>
                <div class="card">
                    <h3>Картка 2</h3>
                    <p>Тут короткий опис.</p>
                </div>
                <div class="card">
                    <h3>Картка 3</h3>
                    <p>Тут короткий опис.</p>
                </div>
            </div>
        </section>
    </main>

    <footer id="footer" class="site-footer">
        <p>Створено учнем на курсі HTML + CSS</p>
    </footer>
</body>
</html>
```

### `style.css`
```css
body {
    font-family: Arial, sans-serif;
    margin: 0;
    background-color: #f5f7fb;
    color: #1f2937;
}

.site-header {
    background-color: #4f46e5;
    color: white;
    padding: 20px;
}

.menu {
    display: flex;
    gap: 15px;
    margin-top: 10px;
}

.menu a {
    color: white;
    text-decoration: none;
    font-weight: bold;
}

.container {
    padding: 20px;
}

.hero {
    background-color: white;
    padding: 20px;
    border-radius: 14px;
    margin-bottom: 20px;
    box-shadow: 0 4px 10px rgba(0, 0, 0, 0.08);
}

.cards {
    display: flex;
    gap: 20px;
    flex-wrap: wrap;
}

.card {
    background-color: white;
    padding: 20px;
    border-radius: 14px;
    width: 220px;
    box-shadow: 0 4px 10px rgba(0, 0, 0, 0.08);
}

.site-footer {
    background-color: #312e81;
    color: white;
    padding: 15px 20px;
    margin-top: 20px;
}
```

---

## Частина 5. Що тут вже використовується

На цій сторінці ми вже застосували знайомі речі:
- структуру HTML-документа;
- `header`, `main`, `section`, `footer`;
- меню;
- блоки з контентом;
- картки;
- `Flexbox` для розташування елементів.

Тобто це вже не одна маленька вправа, а **майже готовий сайт**.

---

## Частина 6. Практика

### План на 60 хв
1. `10 хв` — коротке нагадування, з яких блоків складається сайт
2. `15 хв` — збірка HTML-структури сторінки
3. `15 хв` — оформлення шапки, меню і контенту
4. `15 хв` — додавання карток і оформлення
5. `5 хв` — підсумок уроку

---

### Що учні мають вміти після уроку
- зібрати сторінку з кількох блоків;
- використати вже знайомі теги структури;
- зробити меню;
- розмістити картки через `Flexbox` або `Grid`;
- оформити сторінку так, щоб вона виглядала як мінісайт.

---

## Практика 1. Збираємо базовий макет сторінки

### Завдання
Створи сторінку, у якій буде:
- назва сайту;
- меню;
- блок з описом;
- блок з картками;
- футер.

### Готовий приклад результату

#### `index.html`
```html
<!DOCTYPE html>
<html lang="uk">
<head>
    <meta charset="UTF-8">
    <title>Моє хобі</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <header class="site-header">
        <h1>Моє хобі</h1>
        <nav class="menu">
            <a href="#about">Про мене</a>
            <a href="#cards">Моє хобі</a>
            <a href="#footer">Контакти</a>
        </nav>
    </header>

    <main class="container">
        <section id="about" class="hero">
            <h2>Привіт!</h2>
            <p>Я люблю створювати сайти та дізнаватися щось нове.</p>
        </section>

        <section id="cards" class="cards-section">
            <h2>Що мені подобається</h2>
            <div class="cards">
                <div class="card">
                    <h3>Ігри</h3>
                    <p>Я люблю цікаві пригоди та будівництво.</p>
                </div>
                <div class="card">
                    <h3>Малювання</h3>
                    <p>Мені подобається придумувати власних героїв.</p>
                </div>
                <div class="card">
                    <h3>Технології</h3>
                    <p>Я хочу навчитися робити свої сайти.</p>
                </div>
            </div>
        </section>
    </main>

    <footer id="footer" class="site-footer">
        <p>Мій навчальний сайт</p>
    </footer>
</body>
</html>
```

#### `style.css`
```css
body {
    font-family: Arial, sans-serif;
    margin: 0;
    background-color: #f5f7fb;
}

.site-header {
    background-color: #4f46e5;
    color: white;
    padding: 20px;
}

.menu {
    display: flex;
    gap: 15px;
}

.menu a {
    color: white;
    text-decoration: none;
}

.container {
    padding: 20px;
}

.hero,
.card {
    background-color: white;
    border-radius: 14px;
    padding: 20px;
    box-shadow: 0 4px 10px rgba(0,0,0,0.08);
}

.hero {
    margin-bottom: 20px;
}

.cards {
    display: flex;
    gap: 20px;
    flex-wrap: wrap;
}

.card {
    width: 220px;
}

.site-footer {
    background-color: #312e81;
    color: white;
    padding: 15px 20px;
    margin-top: 20px;
}
```

---

## Практика 2. Робимо меню

### Завдання
У шапці сторінки створити меню мінімум із 3 пунктів.

### Готовий приклад результату

#### `index.html`
```html
<header class="site-header">
    <h1>Моя сторінка</h1>
    <nav class="menu">
        <a href="#about">Про мене</a>
        <a href="#cards">Мої улюблені речі</a>
        <a href="#footer">Контакти</a>
    </nav>
</header>
```

#### `style.css`
```css
.site-header {
    background-color: #4f46e5;
    color: white;
    padding: 20px;
}

.menu {
    display: flex;
    gap: 15px;
    margin-top: 10px;
}

.menu a {
    color: white;
    text-decoration: none;
    font-weight: bold;
}
```

### Додаткове завдання
Спробуй змінити відстань між пунктами меню.

---

## Практика 3. Додаємо 3 картки

### Завдання
Створи 3 картки на тему своєї сторінки.

### Готовий приклад результату

#### `index.html`
```html
<div class="cards">
    <div class="card">
        <h3>Minecraft</h3>
        <p>Мені подобається будувати великі світи.</p>
    </div>
    <div class="card">
        <h3>Roblox</h3>
        <p>Там багато різних режимів і карт.</p>
    </div>
    <div class="card">
        <h3>Brawl Stars</h3>
        <p>Мені подобається швидкий темп гри.</p>
    </div>
</div>
```

#### `style.css`
```css
.cards {
    display: flex;
    gap: 20px;
    flex-wrap: wrap;
}

.card {
    background-color: white;
    padding: 20px;
    border-radius: 14px;
    width: 220px;
    box-shadow: 0 4px 10px rgba(0,0,0,0.08);
}
```

---

## Практика 4. Додаємо індивідуальність

### Завдання
Зміни сторінку так, щоб вона стала більш "твоєю".

### Готовий приклад результату

#### `index.html`
```html
<section class="hero">
    <h2>Ласкаво прошу у світ моїх улюблених ігор!</h2>
    <p>Тут я зібрав коротку інформацію про те, що мені подобається найбільше.</p>
</section>
```

#### `style.css`
```css
body {
    background: linear-gradient(to bottom, #eef2ff, #f8fafc);
}

.hero {
    background-color: white;
    padding: 20px;
    border-radius: 14px;
    margin-bottom: 20px;
    box-shadow: 0 4px 10px rgba(0,0,0,0.08);
}
```

---

## Мініпроєкт уроку

### Мініпроєкт: "Моя готова сторінка"

Учень має зробити повну сторінку, де є:
- шапка;
- меню;
- короткий опис;
- 3 картки;
- футер;
- охайне оформлення.

### Готовий приклад результату

#### `index.html`
```html
<!DOCTYPE html>
<html lang="uk">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Моя улюблена гра</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <header class="site-header">
        <h1>Моя улюблена гра</h1>
        <nav class="menu">
            <a href="#about">Про гру</a>
            <a href="#cards">Мої причини</a>
            <a href="#footer">Контакти</a>
        </nav>
    </header>

    <main class="container">
        <section id="about" class="hero">
            <h2>Чому мені подобається Minecraft</h2>
            <p>Minecraft дає можливість будувати, досліджувати та вигадувати власні світи.</p>
        </section>

        <section id="cards">
            <h2>Що мені найбільше подобається</h2>
            <div class="cards">
                <div class="card">
                    <h3>Будівництво</h3>
                    <p>Можна створювати будинки, міста і замки.</p>
                </div>
                <div class="card">
                    <h3>Пригоди</h3>
                    <p>У грі цікаво шукати ресурси та досліджувати світ.</p>
                </div>
                <div class="card">
                    <h3>Фантазія</h3>
                    <p>Можна придумати власний сюжет і створити щось особливе.</p>
                </div>
            </div>
        </section>
    </main>

    <footer id="footer" class="site-footer">
        <p>Сторінку створив учень курсу HTML + CSS</p>
    </footer>
</body>
</html>
```

#### `style.css`
```css
body {
    font-family: Arial, sans-serif;
    margin: 0;
    background-color: #f4f7fb;
    color: #1f2937;
}

.site-header {
    background-color: #16a34a;
    color: white;
    padding: 20px;
}

.menu {
    display: flex;
    gap: 15px;
    margin-top: 10px;
}

.menu a {
    color: white;
    text-decoration: none;
    font-weight: bold;
}

.container {
    padding: 20px;
}

.hero,
.card {
    background-color: white;
    border-radius: 14px;
    padding: 20px;
    box-shadow: 0 4px 10px rgba(0,0,0,0.08);
}

.hero {
    margin-bottom: 20px;
}

.cards {
    display: flex;
    gap: 20px;
    flex-wrap: wrap;
}

.card {
    width: 220px;
}

.site-footer {
    background-color: #166534;
    color: white;
    padding: 15px 20px;
    margin-top: 20px;
}
```

---

## Типові помилки

- сторінка зібрана без логіки;
- шапка є, але меню не оформлене;
- картки стоять одна під одною, хоча учень хотів у ряд;
- `Flexbox` увімкнено не для того блоку;
- занадто багато тексту в картках;
- кольори вибрані так, що текст погано видно;
- елементи прилипають один до одного через відсутність відступів.

---

## Запитання для повторення

1. З яких головних частин складається проста вебсторінка?
2. Для чого потрібен `header`?
3. Де знаходиться головний зміст сторінки?
4. Для чого зручно використовувати `Flexbox` або `Grid`?
5. Що таке картка на сайті?
6. Чому важливо не просто написати код, а зібрати сторінку логічно?

---

## Домашнє завдання

Створи власний мінісайт на одну з тем:
- моя улюблена гра;
- моє хобі;
- мій домашній улюбленець;
- моя команда героїв;
- моя сторінка про себе.

### На сторінці повинні бути:
- `header`
- меню
- `main`
- хоча б 2 секції
- 3 картки
- `footer`

### Додаткове завдання
Спробуй зробити сторінку ще цікавішою:
- додай більше карток;
- зміни кольори;
- зроби свій стиль меню;
- придумай власну тему сайту.
