# Урок: HTML + CSS — блокові теги та стилі (без JS)

## Мета уроку
Після уроку ти зможеш:
- розуміти базові **блокові теги HTML**;
- писати структуру сторінки;
- виносити стилі в **окремий CSS-файл**;
- стилізувати блоки і текст покроково.

---

## 1) Структура проєкту

Створи папку, наприклад `lesson-html-css`, і в ній 2 файли:

- `index.html`
- `styles.css`

Приклад:

```text
lesson-html-css/
  index.html
  styles.css
```

---

## 2) Як підключити CSS до HTML

У `index.html` в `<head>` додай:

```html
<link rel="stylesheet" href="styles.css" />
```

- `rel="stylesheet"` — тип підключення
- `href="styles.css"` — шлях до CSS-файлу

> Якщо файл CSS в тій самій папці, достатньо просто `styles.css`.

---

## 3) Базовий HTML-шаблон

### `index.html`

```html
<!doctype html>
<html lang="uk">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Урок HTML + CSS</title>
  <link rel="stylesheet" href="styles.css" />
</head>
<body>
  <main class="container">
    <header class="box">
      <h1>Мій перший макет</h1>
      <p>Вивчаємо блокові теги і стилі.</p>
    </header>

    <section class="box">
      <h2>Розділ 1</h2>
      <p>Тут текст першого розділу.</p>
    </section>

    <section class="box">
      <h2>Розділ 2</h2>
      <p>Тут текст другого розділу.</p>
    </section>

    <footer class="box">
      <p>© 2026 Навчальний приклад</p>
    </footer>
  </main>
</body>
</html>
```

---

## 4) CSS покроково: “ось тег → ось стиль → пояснення”

### Крок 1. Стилізуємо всю сторінку (`body`)

```css
body {
  margin: 0;
  font-family: Arial, sans-serif;
  background: #eef2ff;
  color: #222;
}
```

**Пояснення:**
- `margin: 0;` прибирає стандартні відступи браузера.
- `font-family` задає шрифт.
- `background` — фон сторінки.
- `color` — базовий колір тексту.

---

### Крок 2. Контейнер (`.container`)

```css
.container {
  max-width: 800px;
  margin: 24px auto;
  padding: 0 16px;
}
```

**Пояснення:**
- `max-width: 800px;` обмежує ширину контенту.
- `margin: 24px auto;` центрує блок по горизонталі.
- `padding` дає внутрішній простір зліва/справа.

---

### Крок 3. Блоки (`.box`)

```css
.box {
  background: #fff;
  border: 1px solid #dbe1ff;
  border-radius: 12px;
  padding: 16px;
  margin-bottom: 16px;
}
```

**Пояснення:**
- `background` — білий фон блока.
- `border` — тонка рамка.
- `border-radius` — округлення кутів.
- `padding` — відступ між рамкою і текстом.
- `margin-bottom` — відстань між блоками.

---

### Крок 4. Заголовок першого рівня (`h1`)

```css
h1 {
  margin: 0 0 10px;
  color: #243b6b;
  font-size: 32px;
}
```

**Пояснення:**
- `margin: 0 0 10px;` прибирає верхній відступ і залишає нижній.
- `color` змінює колір заголовка.
- `font-size` робить головний заголовок більшим.

---

### Крок 5. Заголовки другого рівня (`h2`)

```css
h2 {
  margin: 0 0 8px;
  color: #304a85;
  font-size: 24px;
}
```

**Пояснення:**
- Візуально відділяє розділи.
- Робить структуру сторінки читабельною.

---

### Крок 6. Абзаци (`p`)

```css
p {
  margin: 0;
  line-height: 1.6;
  font-size: 16px;
}
```

**Пояснення:**
- `line-height: 1.6;` покращує читабельність.
- `font-size: 16px;` комфортний розмір для тексту.

---

## 5) Повний файл CSS

### `styles.css`

```css
body {
  margin: 0;
  font-family: Arial, sans-serif;
  background: #eef2ff;
  color: #222;
}

.container {
  max-width: 800px;
  margin: 24px auto;
  padding: 0 16px;
}

.box {
  background: #fff;
  border: 1px solid #dbe1ff;
  border-radius: 12px;
  padding: 16px;
  margin-bottom: 16px;
}

h1 {
  margin: 0 0 10px;
  color: #243b6b;
  font-size: 32px;
}

h2 {
  margin: 0 0 8px;
  color: #304a85;
  font-size: 24px;
}

p {
  margin: 0;
  line-height: 1.6;
  font-size: 16px;
}
```

---

## 6) Які теги для чого (шпаргалка)

- `<main>` — головний контент сторінки
- `<header>` — верхній блок
- `<section>` — окремий змістовний розділ
- `<footer>` — нижній блок
- `<h1>`, `<h2>` — заголовки
- `<p>` — текст абзацу
- `<div>` — універсальний блок, якщо семантичний тег не підходить

---

## 7) Типові помилки

1. CSS не підключився:
   - перевір `href="styles.css"`
   - перевір назву файлу (включно з регістром)
2. Немає змін на сторінці:
   - збережи обидва файли
   - перезавантаж сторінку (Ctrl+F5)
3. Стилі “стрибають”:
   - перевір дужки `{}` і `;` у CSS

---

## 8) Практичні завдання

### Завдання 1 (база)
Створи сторінку з:
- `header`,
- 2 `section`,
- `footer`.

Оформи блоки через клас `.box`.

### Завдання 2 (текст)
Для `h1`, `h2`, `p` задай:
- колір,
- розмір,
- відступи,
- міжрядковий інтервал.

### Завдання 3 (дизайн)
Зміни стиль так, щоб:
- фон сторінки був світло-сірий,
- блоки мали тінь,
- заголовки були темно-сині.

### Завдання 4 (підвищений)
Додай третій розділ “Контакти”:
- заголовок,
- 2 абзаци,
- окремий стиль рамки лише для цього блоку через додатковий клас.

---

## 9) Шпаргалка: варіанти запису CSS-властивостей

Нижче — найуживаніші властивості з різними форматами запису.

### `margin` (зовнішні відступи)

```css
margin: 16px;                 /* всі сторони */
margin: 10px 20px;            /* top/bottom, left/right */
margin: 8px 16px 24px;        /* top, left/right, bottom */
margin: 5px 10px 15px 20px;   /* top, right, bottom, left */

margin-top: 10px;
margin-right: 20px;
margin-bottom: 15px;
margin-left: 20px;

margin: 0 auto;               /* центрування блочного елемента по горизонталі */
```

### `padding` (внутрішні відступи)

```css
padding: 12px;
padding: 8px 16px;
padding: 8px 16px 20px;
padding: 4px 8px 12px 16px;

padding-top: 10px;
padding-left: 14px;
```

### `border` (рамка)

```css
border: 1px solid #333;            /* товщина + стиль + колір */
border: 2px dashed #0a7;
border: 3px dotted #999;

border-width: 2px;
border-style: solid;
border-color: #1e3a8a;

border-radius: 8px;
border-radius: 50%;                /* коло для квадратного блока */
```

### `font` / текст

```css
font-size: 16px;
font-weight: 400;   /* normal */
font-weight: 700;   /* bold */
font-style: normal;
font-style: italic;

line-height: 1.5;
text-align: left;
text-align: center;
text-transform: uppercase;
letter-spacing: 1px;
```

### `background`

```css
background: #f5f5f5;
background: linear-gradient(90deg, #e0e7ff, #ffffff);
background-color: #eef2ff;
```

### `width` / `height`

```css
width: 300px;
width: 100%;
max-width: 800px;
min-height: 120px;
height: auto;
```

### `display`

```css
display: block;
display: inline;
display: inline-block;
display: flex;
display: grid;
display: none;
```

#### `display: flex` — пояснення
`flex` вмикає **гнучкий ряд або колонку** для дочірніх елементів.
- Є контейнер (`display: flex`), а всередині — flex-елементи.
- Дуже зручно для меню, карток, кнопок у ряд.

Основні властивості:
- `flex-direction` — напрям (`row`, `column`)
- `justify-content` — вирівнювання по головній осі
- `align-items` — вирівнювання по поперечній осі
- `gap` — відстань між елементами
- `flex-wrap` — перенос на новий рядок

Приклад:

```html
<div class="flex-wrap">
  <div class="item">Картка 1</div>
  <div class="item">Картка 2</div>
  <div class="item">Картка 3</div>
</div>
```

```css
.flex-wrap {
  display: flex;
  gap: 12px;
  justify-content: space-between;
  align-items: center;
  flex-wrap: wrap;
}

.item {
  background: #fff;
  border: 1px solid #ddd;
  padding: 12px;
  border-radius: 8px;
  min-width: 160px;
}
```

---

#### `display: grid` — пояснення
`grid` вмикає **сітку (рядки + колонки)**.
- Ідеально, коли потрібна структура як “таблиця”, але гнучка.
- Добре для галерей, каталогів, дашбордів.

Основні властивості:
- `grid-template-columns` — скільки колонок і їх ширини
- `grid-template-rows` — рядки
- `gap` — відстань між комірками
- `grid-column`, `grid-row` — розтягування елемента

Приклад:

```html
<div class="grid-wrap">
  <div class="card">A</div>
  <div class="card">B</div>
  <div class="card">C</div>
  <div class="card">D</div>
</div>
```

```css
.grid-wrap {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 12px;
}

.card {
  background: #fff;
  border: 1px solid #ddd;
  padding: 16px;
  border-radius: 8px;
}
```

> `1fr` = “одна частка доступного простору”.
> `repeat(2, 1fr)` = 2 рівні колонки.

---

#### Коли flex, а коли grid?
- Якщо потрібно вирівняти елементи **в один ряд/колонку** → частіше `flex`.
- Якщо потрібна **двовимірна сітка** (і рядки, і колонки) → `grid`.

### `position` (базово)

```css
position: static;   /* за замовчуванням */
position: relative;
position: absolute;
position: fixed;
position: sticky;
```

Що означає кожен варіант:

- `position: static;`
  - стандартна поведінка елемента в потоці сторінки;
  - властивості `top/right/bottom/left` не застосовуються.

- `position: relative;`
  - елемент залишається в потоці;
  - можна зсунути його `top/left/...` від власної позиції;
  - часто використовується як опорний контейнер для `absolute`-елементів.

- `position: absolute;`
  - елемент виймається зі звичайного потоку;
  - позиціонується відносно найближчого предка з `position: relative/absolute/fixed/sticky`;
  - якщо такого предка немає — відносно вікна сторінки.

- `position: fixed;`
  - елемент прив’язаний до вікна браузера;
  - не рухається при прокрутці.

- `position: sticky;`
  - поєднує `relative` і `fixed`;
  - поки не дійшов до межі (наприклад `top: 0`) — поводиться як звичайний;
  - далі “прилипає” у межах свого контейнера.

Приклад:

```html
<div class="parent">
  <div class="abs">ABS</div>
  <p>Текст у контейнері...</p>
</div>

<div class="fixed-btn">Чат</div>

<h3 class="sticky-title">Заголовок секції</h3>
```

```css
.parent {
  position: relative;
  border: 1px solid #ccc;
  padding: 20px;
}

.abs {
  position: absolute;
  top: 8px;
  right: 8px;
  background: #ffe08a;
  padding: 4px 8px;
}

.fixed-btn {
  position: fixed;
  bottom: 16px;
  right: 16px;
  background: #0057ff;
  color: #fff;
  padding: 8px 10px;
  border-radius: 8px;
}

.sticky-title {
  position: sticky;
  top: 0;
  background: #fff;
}
```

### `box-shadow`

```css
box-shadow: 0 2px 8px rgba(0,0,0,0.1);
box-shadow: 0 6px 20px rgba(0,0,0,0.15);
```

---

## 10) Комплексні практичні завдання (4 шт.)

### Завдання 1: «Персональна сторінка-візитка»
**Що зробити:**
1. Зроби структуру: `header`, `main`, `section` (2 шт.), `footer`.
2. У першому блоці — ім’я, короткий опис, контакти.
3. У другому — список навичок (`ul > li`).
4. Стилізуй:
   - контейнер по центру (`max-width`, `margin: 0 auto`),
   - блоки з рамкою, відступами і тінню,
   - різні стилі для `h1`, `h2`, `p`.

**Бажаний результат (еталон):**

```html
<main class="cv">
  <header class="panel">
    <h1>Іван Петренко</h1>
    <p>Junior Frontend Developer</p>
    <p>Email: ivan@example.com</p>
  </header>

  <section class="panel">
    <h2>Навички</h2>
    <ul>
      <li>HTML</li>
      <li>CSS</li>
      <li>Git</li>
    </ul>
  </section>

  <footer class="panel">
    <p>© 2026</p>
  </footer>
</main>
```

```css
body { background:#f3f5ff; margin:0; font-family:Arial,sans-serif; }
.cv { max-width:700px; margin:24px auto; padding:0 16px; }
.panel { background:#fff; border:1px solid #dfe3ff; border-radius:12px; padding:16px; margin-bottom:14px; }
h1 { margin:0 0 8px; color:#203a70; }
h2 { margin:0 0 8px; color:#2f4f95; }
p, li { line-height:1.5; }
```

**Критерії:** акуратна структура, однакові відступи, читабельний текст.

---

### Завдання 2: «Секція тарифів»
**Що зробити:**
1. Створи блок з 3 картками тарифів: Basic, Pro, Team.
2. У кожній картці: назва, ціна, список переваг, кнопка.
3. Розміщення карток зроби через **Flex**.
4. Додай стани кнопки `:hover` і `:active`.
5. Одну картку виділи як “рекомендовану” (інший колір рамки/фону).

**Бажаний результат (еталон):**

```html
<section class="pricing">
  <article class="plan">
    <h3>Basic</h3><p class="price">$9</p><p>1 проєкт</p><button>Обрати</button>
  </article>
  <article class="plan featured">
    <h3>Pro</h3><p class="price">$19</p><p>10 проєктів</p><button>Обрати</button>
  </article>
  <article class="plan">
    <h3>Team</h3><p class="price">$49</p><p>Безліміт</p><button>Обрати</button>
  </article>
</section>
```

```css
.pricing { display:flex; gap:16px; flex-wrap:wrap; }
.plan { flex:1 1 200px; background:#fff; border:1px solid #ddd; border-radius:10px; padding:16px; }
.featured { border-color:#2f6bff; background:#eef3ff; }
.price { font-size:28px; font-weight:700; color:#1e40af; }
button { border:0; background:#2f6bff; color:#fff; padding:8px 12px; border-radius:8px; cursor:pointer; }
button:hover { background:#1f4fd0; }
button:active { transform:scale(0.98); }
```

**Критерії:** рівні картки, коректний `gap`, помітний акцент на одній картці.

---

### Завдання 3: «Галерея курсів» (Grid)
**Що зробити:**
1. Створи сітку з 6 карток курсів через **CSS Grid**.
2. Кожна картка: назва курсу, короткий опис, рівень складності.
3. На великому екрані — 3 колонки, на середньому — 2, на маленькому — 1.
4. Додай картці тінь, округлення, внутрішні відступи.

**Бажаний результат (еталон):**

```html
<section class="courses">
  <article class="course">HTML — Початковий</article>
  <article class="course">CSS — Початковий</article>
  <article class="course">Flex/Grid — Середній</article>
  <article class="course">Git — Початковий</article>
  <article class="course">Responsive — Середній</article>
  <article class="course">UI Основи — Початковий</article>
</section>
```

```css
.courses { display:grid; grid-template-columns:repeat(3,1fr); gap:12px; }
.course { background:#fff; border:1px solid #ddd; border-radius:10px; padding:14px; box-shadow:0 3px 10px rgba(0,0,0,.06); }

@media (max-width: 900px) {
  .courses { grid-template-columns:repeat(2,1fr); }
}
@media (max-width: 600px) {
  .courses { grid-template-columns:1fr; }
}
```

**Критерії:** адаптивність, рівні відступи, охайна типографіка.

---

### Завдання 4: «Макет статті з позиціонуванням»
**Що зробити:**
1. Створи сторінку статті: заголовок, підзаголовок, 3 абзаци.
2. Додай `sticky`-заголовок секції (`position: sticky; top: 0;`).
3. Додай `fixed`-кнопку в куті (“Вгору”).
4. Усередині одного блоку зроби `absolute`-бейдж (“NEW”) відносно `relative`-контейнера.

**Бажаний результат (еталон):**

```html
<h2 class="sticky">CSS Layout Guide</h2>
<article class="post">
  <span class="badge">NEW</span>
  <h3>Позиціонування</h3>
  <p>Relative дає опорну точку...</p>
  <p>Absolute позиціонується в межах контейнера...</p>
  <p>Fixed прив’язаний до вікна...</p>
</article>
<a href="#" class="to-top">Вгору</a>
```

```css
.sticky { position:sticky; top:0; background:#fff; padding:10px; border-bottom:1px solid #ddd; }
.post { position:relative; max-width:700px; margin:20px auto; padding:16px; border:1px solid #ddd; border-radius:10px; background:#fff; }
.badge { position:absolute; top:10px; right:10px; background:#ffef9f; padding:4px 8px; border-radius:6px; font-weight:700; }
.to-top { position:fixed; right:16px; bottom:16px; background:#2f6bff; color:#fff; padding:8px 10px; border-radius:8px; text-decoration:none; }
```

**Критерії:** правильно працюють `relative/absolute`, видно різницю `fixed` і `sticky`.

---

## 11) Підсумок

- HTML відповідає за структуру.
- CSS — за вигляд.
- Краще тримати HTML і CSS в **окремих файлах**.
- Починай з простого макета: контейнер + блоки + заголовки + абзаци.
- Для кожної властивості є кілька форматів запису: короткий (shorthand) і детальний (окремо по сторонах/параметрах).
