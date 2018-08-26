## Modal HTML
> Ссылка на файлы в gitlab [modal-html.jquery.js](https://git.darvins.ru/darvin-cms/skeleton/blob/master/assets/ds-kit/plugins/modal-html/modal-html.jquery.js)

#### Пример

html:
```
<button class="btn js-modal-html">Modal HTML</button>
```

javascript:
```
$('.js-modal-html').modalHtml({
	title: 'Test', // заголовок всплывашки
	html: '' +     // содержимое всплывашки
        '<p>Тут какой то текст</p>' +
        '<a class="btn btn-center" href="contacts.html">Контактная информация</a> ',
	minResolution: 2880 // минимальное разрешение, на котором сработает клик
});  
```