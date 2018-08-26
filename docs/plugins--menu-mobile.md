## Menu Mobile
> Ссылка на файлы в gitlab [menu-mobile](https://git.darvins.ru/darvin-cms/skeleton/tree/master/assets/ds-kit/plugins/menu-mobile)

#### Пример
html:

```
<nav class="js-menu-mobile">
    <button data-menu-mobile--switcher-btn><span>menu</span></button>
    <ul class="is-root" data-menu-mobile--root>
        <li class="-has-dropdown">
            <a>Пунк 1</a>
            <div>
                <ul>
                    <li><a>Пунк 1.1</a></li>
                    <li><a>Пунк 1.2</a></li>
                    <li><a>Пунк 1.3</a></li>
                    <li><a>Пунк 1.4</a></li>
                    <li><a>Пунк 1.5</a></li>
                </ul>
            </div>
        </li>
        <li><a>Пунк 2</a></li>
        <li><a>Пунк 3</a></li>
        <li><a>Пунк 4</a></li>
        <li><a>Пунк 5</a></li>
        <li><a>Пунк 6</a></li>
    </ul>
</nav>
```
javascript:

```
$('.js-menu-mobile').menuMobile({
    text: {
        rootTitle: 'Меню'
    }
});
```