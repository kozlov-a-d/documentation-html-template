##Decorators
Ссылка на файл в gitlab [decorators.util.js](https://git.darvins.ru/darvin-cms/skeleton/blob/master/assets/ds-kit/basis/decorators.util.js)

* debounce  
* throttle

###debounce
Декоратор позволяет превратить несколько вызовов функции в течение определенного времени в один вызов,
причем задержка начинает заново отсчитываться с каждой новой попыткой вызова.

#### Параметры
*@param {function}* - callback-функция  
*@param {number}* - время задержики  
*@returns {function}*

#### Пример
```
/**
 * Допустим при вводе данных в поле нужно осуществлять проверку или запрос
 * (например поле поиска) Это достаточно ресурсоёмкая операция и мы хотим 
 * выполнять её только когда пользователь закончит ввод
 * 
 * Оборачиваем логику в декоратор debounce и выставляем задержку
 */
var onInput = debounce(function(){
    // do something ...
}, 300 );
/**
 * Вешаем обработчик на поле
 */
input.addEventListener('keydown', function() {
    onInput();
});
```

###throttle
