## Goals

> Цель — это действие посетителя, в котором заинтересован владелец сайта: посещение конкретной страницы, нажатие кнопки или телефоны, оформление заказа и т.д.

Каждый счётчик (gtag, я.метрика и др.) содержит механизмы для отслеживания целей. Они представляют собой обычную js-функцию, которую нужно запустить в определённый момент. Всем этим функциям в качестве аргумента можно передать название цели (список стандартных названий, которые мы используем приведён ниже), также некоторые из них поддерживают дополнительные параметры, например категория цели. 

Разберём на примере Gtag:

#### Клик на телефон
```
$('body').on('click', 'a[href^="tel:"]', function(){
    // если объект gtag существует (счётчик добавлен на страницу)
    if(typeof gtag !== "undefined"){ 
        // тогда срабатывает цель Phone с категорией Click
        gtag('event', 'Phone', {'event_category': 'Click'});
    }
});
```


#### Отправка формы
```
<!-- в шаблоне успеха -->
<script>
    // если форма отправляется аяксом
    if(typeof gtag !== "undefined"){ gtag('event', 'Feedback', {'event_category': 'Enquiry'}); }
    // ...
    // если при отправке формы перезагружается страница,
    // то скрипту необходимо дождаться полной загрузки страницы.
    // т.к. некоторые из счётчиков могут быть добавлены перед закрывающим </body>
    window.onload = function() {
        if(typeof gtag !== "undefined"){ gtag('event', 'Feedback', {'event_category': 'Enquiry'}); }
    }
</script>
```

### Cтандартные названия целей

#### Category: Ecommerce

- *ViewProduct* — Просмотр продукта
- *AddToCart* — Добавление в корзину
- *RemoveFromCart* — Удаление из корзины
- *Purchase* — Покупка

- *GetPriceList* — Получить прайс
- *Enquire* — Отправить запрос
- *QuickOrder* — Заказ без корзины
- *ReviewProduct* — Отзыв к товару

#### Category: Enquiry

- *Feedback* — ФОС
- *Callback* — Заказ звонка
- *Review* — Добавление отзыва
- *Specialist* — Вызов специалиста (например замерщик)

#### Category: Click

- *Phone* — Клик на телефон
- *Whatsapp* — Клик на whatsapp
- *Email* — Клик на почту

> в некоторых случаях 

### Как проверить

#### Gtag / GA

расширение для хрома Tag Assistant (by Google)

#### Facebook Pixel

расширение для хрома Facebook Pixel Helper


#### Я.метрики

Выполнение целей яндекс.метрики можно проверять добавив *?_ym_debug=1*  к урлу.
например 
> http://norma-l.ru/sdelat_zakaz.html?_ym_debug=1

Если всё хорошо, то при выполении цели в консольке должно появиться примерно такое сообщение
> Reach goal. Counter: 27355607. Goal id: ZAJAVKA.

### Отправка форм, на нашей CMS (v5.x)

На наших сайтах все формы отправляются аяксом благодаря этому скрипту это скрипт [form.js](https://git.darvins.ru/darvin-cms/skeleton/blob/master/assets/scripts/form.js)
При успехе там выстреливает событие app.form.success, которое содержит информацию о форме. Это событие прослушивается в скрипте для целей [goals.js](https://git.darvins.ru/darvin-cms/skeleton/blob/master/assets/scripts/goals.js)

Если форме задать название и категорию цели через дата атрибут, тогда в goals.js автоматически отработает цель с таким именем и категорией
```
<form class="ajax" data-goal-name="Feedback" data-goal-category="Enquiry"> 
```

Подбробней о goals.js будет в раздели про стандартные скрипты

### WP ContactForm7

Простой способо отследить успешную отправку цели в плагине ContactForm7 для WP

```
document.addEventListener('wpcf7submit', function (event) {
    if ('369' == event.detail.contactFormId) {
        // успешная отправка
    }
}, false);
```

Может не работать в старых версиях плагина, в таком случае цели нужно делать в админке в настройках формы.
