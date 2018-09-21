## Links

### Общее

Внутрь ссылки нельзя размещать блочные элементы, только картинку или текст, причём что то одно.
Если блок с ссылкой имеет картинку и текст их нужно обернуть в разные теги **<a>**.

#### Плохо
```
<a class="subsection" href="#">
    <div class="subsection__img">
        <img src="/upload/subsection-preview.jpg" alt="Name" title="Name">
    </div>
    <div class="subsection__title">Name</div>
</a>
```
```
<p>
    <a href="#">
        <img src="/upload/img.jpg" alt="text anchor" title="text anchor">
        text anchor
    </a>
</p>
```
#### Хорошо
```
<div class="subsection" href="#">
    <a class="subsection__img" href="#">
        <img src="/upload/subsection-preview.jpg" alt="Name" title="Name">
    </a>
    <a class="subsection__title" href="#">Name</a>
</div>
```
```
<p>
    <a href="#"><img src="/upload/img.jpg" alt="text anchor" title="text anchor"></a>
    <a href="#">text anchor</a>
</p>
```



Допускается вкладывать инлайн-блочные элементы, если это необходимо для стилизации части ссылки

```
<a class="phone" href="tel:+79207777777">+7 (920) <span>777-77-77</span></a>
```

### Ссылки *Read More*

Если в блоке (например в превьюшке новости) есть кнопка *подробнее* или аналогичная, то она должна быть 
сделана отдельной ссылкой с атрибутом **rel="nofollow"**

#### Пример
```
<div class="new-item" href="#">
    <a class="new-item__title" href="#">Name</a>
    <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.</p>
    <a class="new-item__btn-more" href="#" rel="nofollow">Read more</a>
</div>
```

### Ссылки на внешние ресурсы

Ссылкам на стороние ресурсы (например соц. сети) нужно добавлять атрибуты **target="_blank"** и **rel="noreferrer noopener"**

> Подробней о проблеме с безопасностью можно почитать [тут](https://habr.com/post/282880/)

#### Пример
```
<div class="social-link">
    <a href="#" target="_blank" rel="noreferrer noopener"><img src="//images/icon-facebook.svg" alt="facebook" title="facebook"></a> 
    <a href="#" target="_blank" rel="noreferrer noopener"><img src="//images/icon-twitter.svg" alt="twitter" title="twitter"></a> 
    <a href="#" target="_blank" rel="noreferrer noopener"><img src="//images/icon-instagram.svg" alt="instagram" title="instagram"></a> 
    <a href="#" target="_blank" rel="noreferrer noopener"><img src="//images/iconlinkedin.svg" alt="linkedin" title="linkedin"></a> 
</div>
```

### Ссылки на месседжеры, телефоны и тд.

Все ссылки на месседжеры, телефоны, почты расположеные в шапке, подвале, на странице контактов и в шаблонных блоках должны быть кликабельными

```
<a class="phone" href="tel:XXXXXXXXXXXX">XXXXXXXXXXXX</span></a>
<a class="email" href="mailto:XXXXXXXX@gmail.com">XXXXXXXX@gmail.com</span></a>
<a class="whatsapp" href="whatsapp://send?text=&amp;phone=XXXXXXXX&amp;abid=XXXXXXXX">whatsapp</a>
<a class="viber" href="viber://chat?number=XXXXXXXX">viber</a>
```







