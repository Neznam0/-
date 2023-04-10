## CSS
- Переменные

Создать переменную:

```css
element {
  --main-bg-color: brown;
}
```
Использование:
```css
element {
  background-color: var(--main-bg-color);
}


Окрасит элементы разных классов одинаковым цветом:
```css
.{
  color: white;
  background-color: brown;
  margin: 10px;
  width: 50px;
  height: 50px;
  display: inline-block;
}
```

Приминение к HTML:
```html
<div>
    <div class="one"></div>
    <div class="two">Text <span class="five">- more text</span></div>
    <input class="three">
    <textarea class="four">Lorem Ipsum</textarea>
</div>
```

Для некоторых CSS объявлений можно указать цвет выше в каскаде и наследование CSS решит эту проблему. Но для нетривиальных проектов это не всегда возможно. Объявив переменную в псевдоклассе :root, автор CSS может избежать ненужных повторений, используя эту переменную:
```css
:root {
  --main-bg-color: brown;
}

.one {
  color: white;
  background-color: var(--main-bg-color);
  margin: 10px;
  width: 50px;
  height: 50px;
  display: inline-block;
}

.two {
  color: white;
  background-color: black;
  margin: 10px;
  width: 150px;
  height: 70px;
  display: inline-block;
}
.three {
  color: white;
  background-color: var(--main-bg-color);
  margin: 10px;
  width: 75px;
}
.four {
  color: white;
  background-color: var(--main-bg-color);
  margin: 10px;
  width: 100px;
}

.five {
  background-color: var(--main-bg-color);
}
```

____________________________________________________________________________

## CSS
- Функции


функции - это именованная часть кода, которая выполняет определенную задачу.


Базовые CSS функции:


- url()

Позволяет ссылаться на другие ресурсы, чтобы загрузить их. Это могут быть изображения, шрифты и даже другие css файлы. По соображениям производительности рекомендуется ограничивать объем загружаемых данных с помощью url (), поскольку каждое объявление является дополнительным HTTP-запросом.
~~~css
src: url('fantasticfont.woff');
background-image: url("star.gif");
border-image-source: url(/media/diamonds.png);

_______________________________________________
~~~

- attr()

Эта функция позволяет нам проникать в HTML, брать содержимое атрибута и передавать его в свойство содержимого CSS.

~~~css
/* Пример простого использования */
attr(data-count);
attr(title);

/* С типом */
attr(src url);
attr(data-count number);
attr(data-width px);

