##Resize Component
Компонент для упрощения работы с событием resize и отслеживания размеров окна
>Ссылка на файл в gitlab [resize.component.js](https://git.darvins.ru/darvin-cms/skeleton/blob/master/assets/ds-kit/basis/resize.component.js)

>####Dependence:
>basis/decorators.util.js (throttle)
 
###Методы:
####setFreezeTime
 Устанавливаем время задержки между вызовами обработчиков resize 
```
/**
 * @param {number} ms - время задержики
 */
resizeComponent.setFreezeTime(200);
```

####addMediaQuery
```
resizeComponent.addMediaQuery({
    min: 0,    // начало интервала
    max: 1023, // конец интервала
    onEnter: function(){
        // функция выполнится при каждом входе в интервал
    }, 
    onEach: function(){
        // функция выполнится при каждом ресайзе внутри интервала  
    }, 
    onExit: function(){
        // функция выполнится при выходе из интервала
    }
});
```

####resizeForce
Принудительно вызывает срабатывание актуальных обработчиков
```
resizeComponent.resizeForce();
```
