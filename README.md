# Aray Bereket — contact page

Одна страница на белом фоне: имя слева, вертикальная черта, справа
email / LinkedIn / город. Телефона нет. Всё на английском.

---

## Посмотреть

Двойной клик по `index.html` или:

```bash
open index.html
```

---

## Что где лежит

```
index.html                 текст и ссылки
styles.css                 белый фон, типографика, пунктирные линии
favicon.svg                иконка вкладки
fonts/inter.woff2          Inter 400–500 (запасной шрифт)
fonts/inter-bold.woff2     Inter 700 (жирные подписи)
CNAME                      домен arayb.me для GitHub Pages
```

Основной шрифт — системный Helvetica Neue. Если его нет (Windows/Android),
подключается Inter. Интернет для шрифтов не нужен.

---

## Поменять данные

**Имя** — в `index.html`:

```html
<h1 class="name" id="name">Aray<br>Bereket</h1>
```

`<br>` переносит фамилию на вторую строку. Убери его, если нужно в одну.

**Email**:

```html
<a href="mailto:contact@arayb.me">contact@arayb.me</a>
```

**LinkedIn**:

```html
<a href="https://www.linkedin.com/in/arayb" target="_blank" rel="noopener">
  linkedin.com/in/arayb
</a>
```

**Город**:

```html
<dd>Prague, Czech Republic</dd>
```

Email также указан в `<meta name="description">` и в JSON-LD в начале файла.
Лучше найти `contact@arayb.me` и заменить везде.

---

## Добавить или убрать строку

Один блок = подпись + значение + пунктирная линия:

```html
<div class="item">
  <dt>email</dt>
  <dd><a href="mailto:contact@arayb.me">contact@arayb.me</a></dd>
</div>
```

Скопируй блок целиком и поменяй `dt` / `dd`. Подписи можно писать с большой
буквы — стиль от этого не сломается. Последняя строка в списке не имеет
линии снизу (`.item:last-child`).

---

## Цвета и шрифт

В начале `styles.css`:

```css
--bg:    #ffffff;  /* фон */
--ink:   #111111;  /* имя и подписи */
--value: #1b1b1b;  /* email, ссылка, город */
--dot:   #c9c9c9;  /* пунктирные линии */
```

Размер имени:

```css
.name { font-size: clamp(3.6rem, 7.2vw, 7rem); }
```

Первое число — минимум, второе — зависимость от ширины экрана,
третье — максимум.

На экранах уже 900px имя и контакты встают в колонку, вертикальная
черта становится горизонтальной.

---

## Опубликовать на arayb.me

`CNAME` уже содержит `arayb.me`.

**GitHub Pages:** залей содержимое папки в репозиторий.

**Netlify / Cloudflare Pages:** перетащи папку, домен привязывается в настройках.

**Заменить текущий сайт в `~/arayb.me`:**

```bash
cp -R ~/arayb.me ~/arayb.me-backup   # копия старого сайта
cp -R ~/visiting-card/* ~/arayb.me/  # новые файлы
```

Старый сайт я не трогал. Скажи, если нужно заменить его самому.
