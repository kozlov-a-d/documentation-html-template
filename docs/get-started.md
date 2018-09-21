## Getting Started
> Ссылка на  gitlab [skeleton](https://git.darvins.ru/darvin-cms/skeleton)

>####Dependence:
> [nodejs](https://nodejs.org/en/)  
>  [yarn](https://yarnpkg.com/lang/en/) — опционально

### How to:
1. cкачиваем шаблон ( *git clone * )
2. устанавливаем пакеты ( *npm i* или *yarn* )

1. идём в репозиторий с шаблоном https://git.darvins.ru/darvin-cms/skeleton
2. копируем SSH ( git@git.darvins.ru:darvin-cms/skeleton.git ) http://prntscr.com/k60al8
3. на своём компе открываем папку, где храним проекты запускаете консоль и пишем *git clone git@git.darvins.ru:darvin-cms/skeleton.git*
4. переименовываем появившуюся папку skeleton по названию проекта ( например my-awesome-project ) 
5. возвращаемся в гитлаб https://git.darvins.ru/  там нужно создать новый проект http://prntscr.com/k60d88
6. указываем Project name по домену и *обязательно выбираем следующие настройки*
  - Project path — client-projects
  - Visibility Level — Internal
7. жмём создать проект и гитлаб предложит варианты, что засунуть в репозиторий, нас интересует *Existing Git repository* http://prntscr.com/k60ey0
8. копируем команды и идём в консоль, вставляем их туда и запускаем.
    - обратите внимание, что в первой строке надо заменить имя папки на ваше ( наприме  *cd my-awesome-project* )

Теперь скаченый шаблон привязан к новому репозиторию и можно верстать =)

Не забываем устанавливаем пакеты ( *npm i* или *yarn* )

### Команды
**gulp build-html** - билдятся вендеры/стили/скрипты + хтмлка  
**gulp watch-html** - билдятся вендеры/стили/скрипты + хтмлка + вотчер,  
**gulp serve-html** - билдятся вендеры/стили/скрипты + хтмлка + вотчер + browserSync,  
**gulp build**      - билдятся вендеры/стили/скрипты,  
**gulp watch**      - билдятся вендеры/стили/скрипты,  
**gulp build-prod** - билдятся вендеры/стили/скрипты на продашкен  