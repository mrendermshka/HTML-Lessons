# CSS-анімації та трансформації (HTML + CSS)

## Для кого цей матеріал
- Вік: 12+ років
- Рівень: початковий
- Формат: 50% туторіал (пояснення + приклади), 50% урок (практика + задачі + еталонні розв'язки)
- Технології: тільки `HTML` і `CSS` (без `JavaScript`)

---

## Частина 1. Туторіал (пояснення простою мовою)
- Формат кожного підпункту: спочатку коротке пояснення, потім окремо `index.html`, потім окремо `styles.css`.

### 1. Що таке трансформація (`transform`)
- Трансформація змінює вигляд елемента: рухає, обертає, масштабує, нахиляє.
- Вона не "ламає" документ: елемент візуально змінюється, але логіка розмітки лишається.

#### `index.html`
```html
<div class="demo-box">BOX</div>
```

#### `styles.css`
```css
.demo-box {
  width: 100px;
  height: 100px;
  display: grid;
  place-items: center;
  background: #60a5fa;
  color: white;
  border-radius: 12px;
  transition: transform 0.4s ease;
}
.demo-box:hover {
  transform: translateY(-10px) rotate(8deg) scale(1.08);
}
```

### 2. Базові функції `transform`

#### `translate(...)` - переміщення
- `translateX(20px)` - вправо на `20px`
- `translateY(-10px)` - вгору на `10px`
- `translate(20px, -10px)` - одразу по X і Y

#### `scale(...)` - масштаб
- `scale(1.2)` - збільшити в 1.2 раза
- `scale(0.8)` - зменшити
- `scale(1.2, 0.8)` - різний масштаб по X і Y

#### `rotate(...)` - обертання
- `rotate(45deg)` - повернути на 45 градусів
- `rotate(1turn)` - один повний оберт

#### `skew(...)` - нахил
- `skewX(15deg)` - нахил по X
- `skewY(10deg)` - нахил по Y
- `skew(15deg, 10deg)` - комбінований

#### `index.html`
```html
<div class="row">
  <div class="item t1">translate</div>
  <div class="item t2">scale</div>
  <div class="item t3">rotate</div>
  <div class="item t4">skew</div>
</div>
```

#### `styles.css`
```css
.row { display: flex; gap: 12px; flex-wrap: wrap; }
.item {
  width: 110px;
  height: 70px;
  display: grid;
  place-items: center;
  background: #dbeafe;
  border: 2px solid #3b82f6;
  border-radius: 10px;
  transition: transform 0.35s ease;
}
.t1:hover { transform: translateX(18px); }
.t2:hover { transform: scale(1.15); }
.t3:hover { transform: rotate(12deg); }
.t4:hover { transform: skew(-12deg, 0deg); }
```

### 3. Комбінації `transform`
- Можна писати кілька функцій в одному рядку.
- Порядок важливий.

#### `index.html`
```html
<div class="combo-wrap">
  <div class="box a">A</div>
  <div class="box b">B</div>
</div>
```

#### `styles.css`
```css
.combo-wrap { display: flex; gap: 26px; padding: 24px; }
.box {
  width: 70px;
  height: 70px;
  display: grid;
  place-items: center;
  background: #34d399;
  border-radius: 10px;
}
.a { transform: translateX(40px) rotate(45deg); }
.b { transform: rotate(45deg) translateX(40px); }
```

- Обидва квадрати мають однакові функції, але інший порядок -> різний результат.

### 4. Точка обертання `transform-origin`
- За замовчуванням: центр (`50% 50%`).
- Можна змінити:

#### `index.html`
```html
<div class="origin-wrap">
  <div class="needle center-origin">center</div>
  <div class="needle left-origin">left bottom</div>
</div>
```

#### `styles.css`
```css
.origin-wrap { display: flex; gap: 26px; }
.needle {
  width: 12px;
  height: 90px;
  background: #ef4444;
  border-radius: 10px;
  animation: spin 2s linear infinite;
}
.center-origin { transform-origin: 50% 50%; }
.left-origin { transform-origin: left bottom; }

@keyframes spin {
  from { transform: rotate(0turn); }
  to   { transform: rotate(1turn); }
}
```

---

### 5. Що таке CSS-анімація
- Анімація = зміна стилів у часі.
- Потрібно:
1. Описати кадри через `@keyframes`.
2. Прив'язати їх до елемента через `animation`.

#### `index.html`
```html
<div class="box">Пульс</div>
```

#### `styles.css`
```css
.box {
  width: 110px;
  height: 110px;
  display: grid;
  place-items: center;
  border-radius: 14px;
  background: #fb7185;
  color: #fff;
  font-weight: 700;
  animation: pulse 1s infinite;
}

@keyframes pulse {
  0%   { transform: scale(1); }
  50%  { transform: scale(1.2); }
  100% { transform: scale(1); }
}
```

---

### 6. Усі параметри анімації та значення

#### `animation-name`
- Назва `@keyframes`.

#### `animation-duration`
- Тривалість одного циклу (`0.5s`, `2s`).

#### `animation-timing-function`
- Як змінюється швидкість:
- `linear` - рівномірно
- `ease` - плавний старт/фініш
- `ease-in` - повільний старт
- `ease-out` - повільний фініш
- `ease-in-out` - повільно на старті та в кінці
- `steps(4, end)` - "сходинки", дискретний рух
- `cubic-bezier(x1, y1, x2, y2)` - власна крива

#### `animation-delay`
- Затримка перед стартом (`1s`, `-0.5s`).
- Від'ємне значення означає: анімація ніби вже йшла якийсь час.

#### `animation-iteration-count`
- Кількість повторів: `1`, `2`, `infinite`.

#### `animation-direction`
- `normal` - вперед
- `reverse` - назад
- `alternate` - вперед/назад
- `alternate-reverse` - назад/вперед

#### `animation-fill-mode`
- `none` - не зберігати стилі до/після
- `forwards` - залишити останній кадр
- `backwards` - застосувати стартовий кадр під час затримки
- `both` - `backwards + forwards`

#### `animation-play-state`
- `running` - грає
- `paused` - пауза

#### `index.html`
```html
<div class="demo-grid">
  <div class="lane"><span>name</span><div class="dot name"></div></div>
  <div class="lane"><span>duration</span><div class="dot duration"></div></div>
  <div class="lane"><span>timing</span><div class="dot timing"></div></div>
  <div class="lane"><span>delay</span><div class="dot delay"></div></div>
  <div class="lane"><span>iteration</span><div class="dot iteration"></div></div>
  <div class="lane"><span>direction</span><div class="dot direction"></div></div>
  <div class="lane"><span>fill-mode</span><div class="dot fill"></div></div>
  <div class="lane"><span>play-state (hover)</span><div class="dot state"></div></div>
</div>
```

#### `styles.css`
```css
.demo-grid { display: grid; gap: 10px; max-width: 420px; }
.lane {
  position: relative;
  display: grid;
  grid-template-columns: 130px 1fr;
  align-items: center;
  gap: 8px;
  min-height: 28px;
  background: #eef2ff;
  border-radius: 8px;
  padding: 4px 10px;
}
.dot {
  width: 18px;
  height: 18px;
  border-radius: 50%;
  background: #2563eb;
  animation-name: moveX;
  animation-duration: 2s;
  animation-timing-function: linear;
  animation-iteration-count: infinite;
}
@keyframes moveX {
  from { transform: translateX(0); }
  to   { transform: translateX(220px); }
}
@keyframes moveXAlt {
  from { transform: translateX(0); }
  to   { transform: translateX(220px) scale(1.25); background: #16a34a; }
}

.name { animation-name: moveXAlt; }
.duration { animation-duration: 0.8s; }
.timing { animation-timing-function: ease-in-out; }
.delay { animation-delay: 1s; animation-fill-mode: backwards; }
.iteration { animation-iteration-count: 3; }
.direction { animation-direction: alternate; }
.fill { animation-iteration-count: 1; animation-fill-mode: forwards; }
.state:hover { animation-play-state: paused; }
```

---

### 7. Комбінації параметрів `animation` (shorthand)

Формат shorthand:
- Повний: `animation: spin 2s linear 0s infinite normal none running;`
- Короткий: `animation: spin 2s linear infinite;`
- Кілька анімацій: `animation: floatY 2s ease-in-out infinite, colorShift 4s linear infinite;`

#### `index.html`
```html
<div class="planet"></div>
```

#### `styles.css`
```css
.planet {
  width: 64px;
  height: 64px;
  border-radius: 50%;
  background: #f59e0b;
  animation:
    orbit 2.5s linear infinite,
    pulseColor 1.4s ease-in-out infinite;
}
@keyframes orbit {
  from { transform: translateX(0) rotate(0turn); }
  to   { transform: translateX(140px) rotate(1turn); }
}
@keyframes pulseColor {
  0%, 100% { filter: brightness(1); }
  50% { filter: brightness(1.35); }
}
```

---

### 8. Важливі комбінації поведінки

#### `direction + iteration-count`
- `alternate` + `infinite` -> "туди-сюди" без стрибка в початок.
- `reverse` + `1` -> один прогін у зворотному напрямку.

#### `delay + fill-mode`
- `delay: 2s` + `backwards` -> ще до старту видно стиль `0%`.
- `forwards` -> після кінця збережеться стиль `100%`.

#### `timing-function`
- `linear` добре для годинників, конвеєрів, фону.
- `ease` добре для "живих" UI-ефектів.
- `steps(...)` добре для спрайтів і "клацань".

#### `index.html`
```html
<div class="track">
  <div class="ball combo1"></div>
  <div class="ball combo2"></div>
</div>
```

#### `styles.css`
```css
.track {
  display: grid;
  gap: 12px;
  width: 320px;
  background: #f1f5f9;
  border-radius: 10px;
  padding: 14px;
}
.ball {
  width: 18px;
  height: 18px;
  border-radius: 50%;
  background: #0ea5e9;
  animation-name: run;
  animation-duration: 1.8s;
}
.combo1 {
  animation-iteration-count: infinite;
  animation-direction: alternate;
  animation-timing-function: ease-in-out;
}
.combo2 {
  animation-delay: 1s;
  animation-fill-mode: backwards;
  animation-iteration-count: infinite;
  animation-timing-function: steps(6, end);
}
@keyframes run {
  from { transform: translateX(0); }
  to   { transform: translateX(250px); }
}
```

---

## Частина 2. Урок (структура заняття)

### План на 60 хв
1. `10 хв` - вступ: що таке `transform` і `@keyframes`
2. `15 хв` - демонстрація прикладів
3. `25 хв` - самостійні задачі
4. `10 хв` - розбір еталонних розв'язків

### Що учні мають вміти після уроку
- Застосовувати `transform` для руху, обертання, масштабу
- Створювати `@keyframes`
- Налаштовувати параметри `animation`
- Комбінувати кілька анімацій

---

## Стартовий HTML-шаблон для всіх вправ

### `index.html`
```html
<!doctype html>
<html lang="uk">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>CSS Animation Lesson</title>
  <link rel="stylesheet" href="styles.css" />
</head>
<body>
  <!-- Тут ваш елемент -->
</body>
</html>
```

### `styles.css`
```css
body {
  margin: 0;
  min-height: 100vh;
  display: grid;
  place-items: center;
  font-family: Arial, sans-serif;
  background: #f4f6fb;
}
```

---

## Практичні задачі для учнів

### Задача 1. "Пружний м'яч"
#### Умова
- Створити коло `80x80`.
- Нехай воно "підстрибує" по вертикалі без JS.
- Використати `@keyframes` + `transform: translateY(...)`.

#### Еталонний розв'язок
##### `index.html`
```html
<!doctype html>
<html lang="uk">
<head>
  <meta charset="UTF-8" />
  <link rel="stylesheet" href="styles.css" />
</head>
<body>
  <div class="ball"></div>
</body>
</html>
```

##### `styles.css`
```css
body { margin: 0; min-height: 100vh; display: grid; place-items: center; background: #eef2ff; }
.ball {
  width: 80px;
  height: 80px;
  border-radius: 50%;
  background: #ff7a59;
  animation: bounce 0.9s ease-in-out infinite;
}

@keyframes bounce {
  0%, 100% { transform: translateY(0); }
  50% { transform: translateY(-140px); }
}
```

---

### Задача 2. "Картка, що оживає при наведенні"
#### Умова
- Створити прямокутну картку.
- При `:hover` картка має трохи збільшуватись і повертатись.
- Додати плавний перехід через `transition`.

#### Еталонний розв'язок
##### `index.html`
```html
<!doctype html>
<html lang="uk">
<head>
  <meta charset="UTF-8" />
  <link rel="stylesheet" href="styles.css" />
</head>
<body>
  <div class="card"></div>
</body>
</html>
```

##### `styles.css`
```css
body { margin: 0; min-height: 100vh; display: grid; place-items: center; background: #f8fafc; }
.card {
  width: 220px;
  height: 140px;
  border-radius: 16px;
  background: linear-gradient(135deg, #60a5fa, #2563eb);
  box-shadow: 0 10px 24px rgba(37, 99, 235, 0.25);
  transition: transform 0.35s ease, box-shadow 0.35s ease;
}
.card:hover {
  transform: scale(1.08) rotate(-3deg);
  box-shadow: 0 16px 32px rgba(37, 99, 235, 0.35);
}
```

---

### Задача 3. "Вітряк"
#### Умова
- Намалювати лопаті (можна псевдоелементами).
- Крутити їх постійно з `linear`.
- Спробувати змінити `transform-origin`.

#### Еталонний розв'язок
##### `index.html`
```html
<!doctype html>
<html lang="uk">
<head>
  <meta charset="UTF-8" />
  <link rel="stylesheet" href="styles.css" />
</head>
<body>
  <div class="windmill">
    <div class="blade-wrap">
      <div class="blade b1"></div>
      <div class="blade b2"></div>
      <div class="blade b3"></div>
    </div>
    <div class="hub"></div>
  </div>
</body>
</html>
```

##### `styles.css`
```css
body { margin: 0; min-height: 100vh; display: grid; place-items: center; background: #eaf7ff; }
.windmill {
  position: relative;
  width: 220px;
  height: 220px;
}
.hub {
  position: absolute;
  inset: 0;
  margin: auto;
  width: 26px;
  height: 26px;
  border-radius: 50%;
  background: #1f2937;
  z-index: 2;
}
.blade-wrap {
  position: absolute;
  inset: 0;
  animation: spin 2.2s linear infinite;
}
.blade {
  position: absolute;
  left: 50%;
  top: 50%;
  width: 18px;
  height: 90px;
  background: #38bdf8;
  border-radius: 10px;
  transform-origin: 50% 100%;
}
.b1 { transform: translate(-50%, -100%) rotate(0deg); }
.b2 { transform: translate(-50%, -100%) rotate(120deg); }
.b3 { transform: translate(-50%, -100%) rotate(240deg); }

@keyframes spin {
  from { transform: rotate(0turn); }
  to { transform: rotate(1turn); }
}
```

---

### Задача 4. "Анімація кроками `steps(...)`"
#### Умова
- Зробити індикатор із 4 сегментів.
- Колір сегментів має змінюватися "клацаннями", не плавно.
- Використати `steps(4, end)`.

#### Еталонний розв'язок
##### `index.html`
```html
<!doctype html>
<html lang="uk">
<head>
  <meta charset="UTF-8" />
  <link rel="stylesheet" href="styles.css" />
</head>
<body>
  <div class="bar"></div>
</body>
</html>
```

##### `styles.css`
```css
body { margin: 0; min-height: 100vh; display: grid; place-items: center; background: #f8fafc; }
.bar {
  width: 320px;
  height: 24px;
  border-radius: 999px;
  background:
    linear-gradient(
      90deg,
      #22c55e 0 25%,
      #e5e7eb 25% 50%,
      #e5e7eb 50% 75%,
      #e5e7eb 75% 100%
    );
  animation: fillSteps 2s steps(4, end) infinite;
}

@keyframes fillSteps {
  0% {
    background: linear-gradient(90deg, #22c55e 0 25%, #e5e7eb 25% 100%);
  }
  25% {
    background: linear-gradient(90deg, #22c55e 0 50%, #e5e7eb 50% 100%);
  }
  50% {
    background: linear-gradient(90deg, #22c55e 0 75%, #e5e7eb 75% 100%);
  }
  75%, 100% {
    background: linear-gradient(90deg, #22c55e 0 100%, #e5e7eb 100% 100%);
  }
}
```

---

### Задача 5 (головна). Аналоговий годинник: `1 хв реального часу = 24 години на годиннику`
#### Умова
- Створити круглий циферблат.
- Додати годинну й хвилинну стрілки.
- Без JS.
- Масштаб часу:
- `60 сек` реального часу = `24 год` симульованого часу.

#### Як порахувати тривалості
- Годинна стрілка робить повне коло за `12 год` симульованого часу.
- Якщо `24 год = 60 сек`, тоді `12 год = 30 сек`.
- Отже: `hour hand -> 30s` за 1 оберт.

- Хвилинна стрілка робить повне коло за `1 год` симульованого часу.
- `1 год = 60 / 24 = 2.5 сек`.
- Отже: `minute hand -> 2.5s` за 1 оберт.

#### Еталонний розв'язок
##### `index.html`
```html
<!doctype html>
<html lang="uk">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Analog Clock CSS Only</title>
  <link rel="stylesheet" href="styles.css" />
</head>
<body>
  <div class="clock">
    <div class="mark m1"></div><div class="mark m2"></div><div class="mark m3"></div><div class="mark m4"></div>
    <div class="mark m5"></div><div class="mark m6"></div><div class="mark m7"></div><div class="mark m8"></div>
    <div class="mark m9"></div><div class="mark m10"></div><div class="mark m11"></div><div class="mark m12"></div>

    <div class="hand hour"></div>
    <div class="hand minute"></div>
    <div class="center"></div>
  </div>

  <div class="note">
    60 секунд реального часу = 24 години на цьому годиннику
  </div>
</body>
</html>
```

##### `styles.css`
```css
:root {
  --clock-size: 320px;
  --ring: #111827;
  --face: #f8fafc;
  --mark: #1f2937;
  --hour-color: #ef4444;
  --minute-color: #0f172a;
}

* { box-sizing: border-box; }
body {
  margin: 0;
  min-height: 100vh;
  display: grid;
  place-items: center;
  background: radial-gradient(circle at top, #dbeafe, #bfdbfe 45%, #93c5fd);
  font-family: Arial, sans-serif;
}

.clock {
  position: relative;
  width: var(--clock-size);
  aspect-ratio: 1;
  border: 10px solid var(--ring);
  border-radius: 50%;
  background: var(--face);
  box-shadow: 0 14px 36px rgba(15, 23, 42, 0.25);
}

.center {
  position: absolute;
  left: 50%;
  top: 50%;
  width: 14px;
  height: 14px;
  border-radius: 50%;
  background: #111827;
  transform: translate(-50%, -50%);
  z-index: 10;
}

.mark {
  position: absolute;
  left: 50%;
  top: 50%;
  width: 6px;
  height: 16px;
  background: var(--mark);
  border-radius: 3px;
  transform-origin: 50% calc(100% + (var(--clock-size) / 2 - 20px));
}
.m1  { transform: translate(-50%, -50%) rotate(0deg); }
.m2  { transform: translate(-50%, -50%) rotate(30deg); }
.m3  { transform: translate(-50%, -50%) rotate(60deg); }
.m4  { transform: translate(-50%, -50%) rotate(90deg); }
.m5  { transform: translate(-50%, -50%) rotate(120deg); }
.m6  { transform: translate(-50%, -50%) rotate(150deg); }
.m7  { transform: translate(-50%, -50%) rotate(180deg); }
.m8  { transform: translate(-50%, -50%) rotate(210deg); }
.m9  { transform: translate(-50%, -50%) rotate(240deg); }
.m10 { transform: translate(-50%, -50%) rotate(270deg); }
.m11 { transform: translate(-50%, -50%) rotate(300deg); }
.m12 { transform: translate(-50%, -50%) rotate(330deg); }

.hand {
  position: absolute;
  left: 50%;
  top: 50%;
  transform-origin: 50% 100%;
  animation-timing-function: linear;
  animation-iteration-count: infinite;
}

.hour {
  width: 8px;
  height: 90px;
  background: var(--hour-color);
  border-radius: 6px;
  transform: translate(-50%, -100%) rotate(0deg);
  animation-name: spinHour;
  animation-duration: 30s; /* 12h симульованого часу */
}

.minute {
  width: 5px;
  height: 130px;
  background: var(--minute-color);
  border-radius: 6px;
  transform: translate(-50%, -100%) rotate(0deg);
  animation-name: spinMinute;
  animation-duration: 2.5s; /* 1h симульованого часу */
}

@keyframes spinHour {
  from { transform: translate(-50%, -100%) rotate(0turn); }
  to   { transform: translate(-50%, -100%) rotate(1turn); }
}

@keyframes spinMinute {
  from { transform: translate(-50%, -100%) rotate(0turn); }
  to   { transform: translate(-50%, -100%) rotate(1turn); }
}

.note {
  position: fixed;
  left: 50%;
  bottom: 20px;
  transform: translateX(-50%);
  background: rgba(255, 255, 255, 0.9);
  border: 1px solid #cbd5e1;
  border-radius: 10px;
  padding: 10px 14px;
  font-size: 14px;
  color: #0f172a;
}
```

---

## Міні-шпаргалка для вчителя

### Типові помилки учнів
- Забули `@keyframes` або помилились у назві `animation-name`.
- Написали `animation-duration: 2` без `s`.
- Переплутали порядок у `transform`.
- Не поставили `transform-origin`, тому стрілка крутиться "не з того місця".

### Що перевіряти під час оцінювання
1. Чи працює без `JavaScript`.
2. Чи використано `transform` і `@keyframes`.
3. Чи правильно підібрані параметри `duration`, `timing-function`, `iteration-count`.
4. Чи акуратний код (`class`-назви, відступи, зрозуміла структура).

---

## Домашнє завдання (додатково)
- Змінити стиль годинника під свою тему (космос, футбол, Minecraft-стиль тощо).
- Додати плавну зміну фону сторінки (`background` + `@keyframes`).
- Створити 2 різні версії однієї анімації: `linear` і `ease-in-out`; порівняти візуально.

---

## Підсумок
- `transform` змінює форму/позицію елемента.
- `@keyframes` описує кроки анімації.
- `animation` керує часом, швидкістю, напрямком і повторами.
- Навіть без JS можна створювати живі й цікаві інтерфейси.




