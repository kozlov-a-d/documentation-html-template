## LocalStorage Component
Компонент для работы с localStorage
>Ссылка на файл в gitlab [localstorage.component.js](https://git.darvins.ru/darvin-cms/skeleton/blob/master/assets/ds-kit/basis/localstorage.component.js)


###Методы:
####state
Добавляем или получаем значение из LocalStorage
```
/**
 * @param {string} название 
 * @param {string|number|json|array|*} новое значение, 
 *                                     если пустое - фукнция возвращает текущее
 */
localStorageComponent.state('fieldName', 'value');
localStorageComponent.state('fieldName'); // 'value'
```

####exist
Проверка существовует ли значение в LocalStorage
```
/**
 * @param {string} название 
 * @returns {boolean}
 */
 localStorageComponent.exist('fieldName'); 
```

####resizeForce
Удаляет значение из LocalStorage с заданным именем
```
/**
 * @param {string} название 
 */
 localStorageComponent.remove('fieldName'); 
```
