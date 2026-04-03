# Урок 7-8. Зображення, відео, кольори та CSS-ефекти (HTML + CSS)

## Для кого цей матеріал
- Вік: 10–13 років
- Рівень: початковий
- Формат: 50% пояснення, 50% практика
- Технології: `HTML` + `CSS`

---

## Мета уроку

На цьому уроці учні:
- навчаться додавати зображення на сторінку;
- дізнаються, як вставляти відео;
- попрацюють із кольорами тексту, фону та блоків;
- познайомляться з `:first-child`, `:nth-child()`, `::before`, `::after`;
- навчаться робити сайт цікавішим і більш візуальним.

---

## Частина 1. Теорія

### 1. Зображення на сайті

Щоб додати картинку на сторінку, використовують тег `<img>`.

Він потрібен, коли ми хочемо показати:
- фото;
- ілюстрацію;
- аватар;
- картинку гри, тварини або героя.

#### Найважливіші частини тега `<img>`
- `src` — шлях до картинки;
- `alt` — текстовий опис картинки;
- `width` — ширина картинки.

#### `index.html`
```html
<img src="cat.jpg" alt="Милий кіт" width="250">
```

### Що означає `alt`

`alt` потрібен для пояснення, що саме зображено на картинці.

Наприклад:
```html
<img src="dog.jpg" alt="Собака біжить по траві">
```

Якщо картинка не відкриється, браузер покаже текст із `alt`.

---

### 2. Локальні та зовнішні зображення

Картинку можна підключити двома способами.

#### Локальна картинка
Тобто файл лежить у тебе в папці проєкту.

```html
<img src="images/minecraft.png" alt="Гра Minecraft">
```

#### Зовнішня картинка
Тобто картинка береться з інтернету через посилання.

```html
<img src="https://example.com/picture.jpg" alt="Картинка з інтернету">
```

Для навчальних проєктів краще частіше використовувати **локальні картинки**, бо вони зручніші для маленького сайту.

---

### 3. Відео на сайті

На сайт можна додавати не тільки картинки, а й відео.

Для цього існує тег `<video>`.

#### Простий приклад
```html
<video controls width="320">
    <source src="video.mp4" type="video/mp4">
</video>
```

### Що означає `controls`

`controls` додає кнопки керування:
- play;
- pause;
- перемотування;
- звук.

---

### 4. Кольори тексту і фону

За допомогою CSS можна змінювати:
- колір тексту;
- колір фону;
- колір окремих блоків;
- колір кнопок;
- колір заголовків.

#### `style.css`
```css
body {
    background-color: #f5f7fb;
    color: #1f2937;
}

h1 {
    color: #4f46e5;
}

.card {
    background-color: #ffffff;
}
```

Головне правило:
текст має бути **добре видно на фоні**.

---

### 5. Псевдоклас `:first-child`

`:first-child` дозволяє оформити **перший елемент** у групі.

#### `index.html`
```html
<div class="cards">
    <div class="card">Картка 1</div>
    <div class="card">Картка 2</div>
    <div class="card">Картка 3</div>
</div>
```

#### `style.css`
```css
.card:first-child {
    border: 3px solid #4f46e5;
}
```

Тепер перша картка виглядатиме особливо.

---

### 6. Псевдоклас `:nth-child()`

`:nth-child()` дозволяє вибрати певний елемент за номером.

#### Приклади
```css
.card:nth-child(2) {
    background-color: #dbeafe;
}

.card:nth-child(3) {
    background-color: #dcfce7;
}
```

Можна ще писати:
```css
.card:nth-child(even) {
    border-radius: 20px;
}
```

Це означає: вибрати **кожну другу** картку.

---

### 7. Псевдоелемент `::before`

`::before` додає щось **перед текстом або елементом**.

#### `style.css`
```css
.card-title::before {
    content: "⭐ ";
}
```

Тепер перед заголовком буде зірочка.

---

### 8. Псевдоелемент `::after`

`::after` додає щось **після тексту або елемента**.

#### `style.css`
```css
.card-title::after {
    content: " new";
    color: red;
}
```

Тепер після заголовка буде слово `new`.

---

## Частина 2. Практика

### План на 60 хв
1. `10 хв` — повторення, як працюють картинки і кольори
2. `15 хв` — вставка зображень і відео
3. `15 хв` — робота з кольорами та оформленням блоків
4. `15 хв` — ефекти через `:first-child`, `:nth-child()`, `::before`, `::after`
5. `5 хв` — підсумок уроку

---

### Що учні мають вміти після уроку
- додавати картинки на сторінку;
- вставляти просте відео;
- змінювати кольори фону і тексту;
- виділяти окремі елементи через `:first-child` і `:nth-child()`;
- додавати маленькі декоративні елементи через `::before` і `::after`.

---

## Практика 1. Додаємо картинки на сайт

### Завдання
Створи сторінку з:
- заголовком;
- коротким текстом;
- двома картинками.

### Готовий приклад результату

#### `index.html`
```html
<!DOCTYPE html>
<html lang="uk">
<head>
    <meta charset="UTF-8">
    <title>Моя улюблена гра</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <h1>Моя улюблена гра</h1>
    <p>Minecraft — це гра, у якій можна будувати власні світи.</p>

    <img src="images/minecraft-1.jpg" alt="Світ Minecraft" width="250">
    <img src="images/minecraft-2.jpg" alt="Будинок у Minecraft" width="250">
</body>
</html>
```

#### `style.css`
```css
body {
    font-family: Arial, sans-serif;
    background-color: #f5f7fb;
    padding: 20px;
}

h1 {
    color: #16a34a;
}

img {
    border-radius: 12px;
    margin-right: 10px;
    box-shadow: 0 4px 10px rgba(0,0,0,0.1);
}
```

---

## Практика 2. Додаємо відео

### Завдання
Додай на сторінку коротке відео або місце під відео.

### Готовий приклад результату

#### `index.html`
```html
<!DOCTYPE html>
<html lang="uk">
<head>
    <meta charset="UTF-8">
    <title>Моє відео</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <h1>Моє улюблене відео</h1>

    <video controls width="400">
        <source src="video/game.mp4" type="video/mp4">
        Твій браузер не підтримує відео.
    </video>
</body>
</html>
```

#### `style.css`
```css
body {
    font-family: Arial, sans-serif;
    background-color: #eef2ff;
    padding: 20px;
}

video {
    border-radius: 12px;
    box-shadow: 0 4px 10px rgba(0,0,0,0.12);
}
```

---

## Практика 3. Працюємо з кольорами

### Завдання
Зроби сторінку яскравішою:
- зміни фон;
- зміни колір заголовка;
- зроби кольорові картки.

### Готовий приклад результату

#### `index.html`
```html
<div class="cards">
    <div class="card">Червона картка</div>
    <div class="card">Синя картка</div>
    <div class="card">Зелена картка</div>
</div>
```

#### `style.css`
```css
body {
    background-color: #f8fafc;
    padding: 20px;
}

.cards {
    display: flex;
    gap: 15px;
}

.card {
    color: white;
    padding: 20px;
    border-radius: 12px;
    font-weight: bold;
}

.card:nth-child(1) {
    background-color: #ef4444;
}

.card:nth-child(2) {
    background-color: #3b82f6;
}

.card:nth-child(3) {
    background-color: #22c55e;
}
```

---

## Практика 4. Виділяємо картки через `:first-child` і `:nth-child()`

### Завдання
Зроби так, щоб:
- перша картка мала рамку;
- друга картка мала інший фон;
- кожна друга картка була трохи іншою.

### Готовий приклад результату

#### `index.html`
```html
<div class="cards">
    <div class="card">Картка 1</div>
    <div class="card">Картка 2</div>
    <div class="card">Картка 3</div>
    <div class="card">Картка 4</div>
</div>
```

#### `style.css`
```css
.cards {
    display: flex;
    gap: 15px;
    flex-wrap: wrap;
}

.card {
    background-color: white;
    padding: 20px;
    border-radius: 12px;
    box-shadow: 0 4px 10px rgba(0,0,0,0.08);
}

.card:first-child {
    border: 3px solid #4f46e5;
}

.card:nth-child(2) {
    background-color: #dbeafe;
}

.card:nth-child(even) {
    transform: translateY(-5px);
}
```

---

## Практика 5. Додаємо декор через `::before` і `::after`

### Завдання
Зроби заголовки карток цікавішими:
- перед текстом додай значок;
- після тексту додай маленький напис.

### Готовий приклад результату

#### `index.html`
```html
<div class="card">
    <h3 class="card-title">Minecraft</h3>
    <p>Моя улюблена гра.</p>
</div>
```

#### `style.css`
```css
.card {
    background-color: white;
    padding: 20px;
    border-radius: 12px;
    width: 220px;
}

.card-title::before {
    content: "⭐ ";
}

.card-title::after {
    content: " top";
    color: #ef4444;
    font-size: 14px;
}
```

---

## Мініпроєкт уроку

### Мініпроєкт: "Яскрава сторінка про мою улюблену тему"

Учень має створити сторінку, де є:
- заголовок;
- текст;
- 2–3 картинки;
- відео або місце під відео;
- кольорові блоки;
- хоча б один ефект через `:first-child`, `:nth-child()`, `::before` або `::after`.

### Готовий приклад результату

#### `index.html`
```html
<!DOCTYPE html>
<html lang="uk">
<head>
    <meta charset="UTF-8">
    <title>Моя улюблена гра</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <header>
        <h1>Моя улюблена гра — Minecraft</h1>
        <p>Тут я зібрав картинки, відео і цікаві факти.</p>
    </header>

    <section class="gallery">
        <img src="images/minecraft-1.jpg" alt="Minecraft світ" width="220">
        <img src="images/minecraft-2.jpg" alt="Minecraft будівля" width="220">
        <img src="images/minecraft-3.jpg" alt="Minecraft герой" width="220">
    </section>

    <section class="cards">
        <div class="card">
            <h3 class="card-title">Будівництво</h3>
            <p>У грі можна створювати власні будинки і міста.</p>
        </div>
        <div class="card">
            <h3 class="card-title">Пригоди</h3>
            <p>У світі гри завжди можна знайти щось цікаве.</p>
        </div>
        <div class="card">
            <h3 class="card-title">Фантазія</h3>
            <p>Кожен може вигадати власну історію.</p>
        </div>
    </section>

    <section class="video-box">
        <video controls width="420">
            <source src="video/minecraft.mp4" type="video/mp4">
        </video>
    </section>
</body>
</html>
```

#### `style.css`
```css
body {
    font-family: Arial, sans-serif;
    background: linear-gradient(to bottom, #ecfccb, #eff6ff);
    padding: 20px;
    color: #1f2937;
}

h1 {
    color: #166534;
}

.gallery {
    display: flex;
    gap: 12px;
    margin: 20px 0;
    flex-wrap: wrap;
}

.gallery img {
    border-radius: 12px;
    box-shadow: 0 4px 10px rgba(0,0,0,0.1);
}

.cards {
    display: flex;
    gap: 15px;
    flex-wrap: wrap;
    margin-top: 20px;
}

.card {
    background-color: white;
    padding: 20px;
    border-radius: 14px;
    width: 220px;
    box-shadow: 0 4px 10px rgba(0,0,0,0.08);
}

.card:first-child {
    border: 3px solid #16a34a;
}

.card:nth-child(2) {
    background-color: #dbeafe;
}

.card-title::before {
    content: "🎮 ";
}

.card-title::after {
    content: " wow";
    color: #ef4444;
    font-size: 13px;
}

.video-box {
    margin-top: 20px;
}

video {
    border-radius: 12px;
    box-shadow: 0 4px 10px rgba(0,0,0,0.12);
}
```

---

## Типові помилки

- забули `alt` у картинки;
- шлях до картинки написаний неправильно;
- файл картинки лежить не в тій папці;
- відео не відтворюється, бо неправильний шлях до файлу;
- текст погано видно на фоні;
- `::before` або `::after` не працює, бо забули `content`;
- `:nth-child()` використано не для того елемента.

---

## Запитання для повторення

1. Для чого потрібен тег `<img>`?
2. Що означає `alt`?
3. Для чого потрібен тег `<video>`?
4. Які властивості змінюють колір тексту і фону?
5. Що робить `:first-child`?
6. Для чого використовується `:nth-child()`?
7. Що робить `::before`?
8. Що робить `::after`?

---

## Домашнє завдання

Створи яскраву сторінку на одну з тем:
- моя улюблена гра;
- моя тварина;
- мій герой;
- моя колекція;
- мій світ фантазії.

### На сторінці повинні бути:
- заголовок;
- 2–3 картинки;
- кольорові блоки;
- хоча б один ефект через `:first-child`, `:nth-child()`, `::before` або `::after`.

### Готовий приклад результату

#### `index.html`
```html
<!DOCTYPE html>
<html lang="uk">
<head>
    <meta charset="UTF-8">
    <title>Моя тварина</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <h1>Мій домашній улюбленець</h1>
    <img src="images/cat.jpg" alt="Мій кіт" width="250">

    <div class="card">
        <h3 class="card-title">Мій кіт</h3>
        <p>Він любить спати, гратися і бігати по кімнаті.</p>
    </div>
</body>
</html>
```

#### `style.css`
```css
body {
    font-family: Arial, sans-serif;
    background-color: #fff7ed;
    padding: 20px;
}

img {
    border-radius: 12px;
    margin-bottom: 20px;
}

.card {
    background-color: white;
    padding: 20px;
    border-radius: 14px;
    width: 260px;
}

.card-title::before {
    content: "🐾 ";
}
```

### Додаткове завдання
Спробуй:
- додати ще одну картинку;
- змінити кольори;
- зробити різний стиль для першого і другого блоку;
- додати невеликий підпис через `::after`.
