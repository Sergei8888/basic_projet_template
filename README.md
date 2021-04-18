Перед началом работы вызвать npm i для установки всех зависимостей, а также npm i -g gulp для работы gulp`а

soft сборка - сборка при которой происходит include для html, если таковые прописаны. 
Sass компилируется. Сss переносится без изменений. JS переносится без изменений.
Img растр конвертится в webp, сжимается и с изначальным файлом jpg и оптимизированным вектором переносится в папку.
Папка components со всем содержимым переносится без изменений.
Все указанные выше файлы переносятся с заменой в папку dist.

hard сборка - выполняется, если hard принимает значение true. Html(см. soft). Sass проходит через autoprefixer и минифкацию, помимо компиляции.
Сss минифицируется. Все js файлы проходят через babel(см. описание require('gulp-babel'), минифицируются и собираются в общий bundle.js).
Img обрабатываются аналогично soft сборки. Папка components со всем содержимым переносится без изменений.
Все указанные выше файлы переносятся с заменой в папку ProdBuild(создается при первом запуске gulp build --hard).

В данной сборке доступно 2 таска - gulp dev и gulp build
При вызове gulp dev производится soft сборка, а так же запуск browsersync и слежка за файлами
При вызове gulp build производится soft сборка
При вызове gulp build --hard производится hard сборка

P.S Вы также можете отдельно вызывать gulp css/html/js/sass/clear/server
