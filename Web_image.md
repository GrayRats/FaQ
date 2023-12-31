Краткое сравнение основных форматов изображений для Web'a

Все форматы изображений, которые используются в вебе, можно разделить на две большие группы: векторные и растровые. Из векторных форматов сейчас используется только SVG. Он отлично подходит для изображений с простыми геометрическими формами, например, пиктограмм или логотипов, и они одинаково хорошо выглядят как на обычных экранах, так и на устройствах с HiDPI-дисплеями, что делает SVG идеальным для адаптивной вёрстки под различные устройства. Но он не годится для изображений с большим количеством деталей, например фотографий, из-за размера файла, плюс браузеру потребуются немалые вычислительные ресурсы CPU/GPU для отрисовки.


Для фотографий на сайте лучше всего подходят растровые форматы. Самые известные и проверенные временем — JPEG и PNG. Есть ещё GIF для анимированных изображений, но он теряет актуальность, и всё чаще его рекомендуют заменить на HTML5-видео. 
С развитием веб-технологий JPEG и PNG всё чаще стали использоваться как fallback'и (фолбеки-резервный вариант) для браузеров, которые не поддерживают современные форматы растровых изображений, такие как WebP и AVIF. 
Сейчас в вебе JPEG отходит на второй план и уступает своё место новым форматам, так как они во многих аспектах его превосходят.

WebP В Google 2010 году Google как альтернативу PNG и JPEG. Он использует алгоритм сжатия ключевых кадров из видеокодека VP8.
Сжатие WebPсостоит из двух этапов: На 1-первом этапе предсказывается содержимое блоков по уже декодированным, на 2-втором — кодируется ошибка предсказания (Википедия https://ru.wikipedia.org/wiki/WebP#%D0%90%D0%BB%D0%B3%D0%BE%D1%80%D0%B8%D1%82%D0%BC).

WebP оставляет чёткие края фотографии, *но* сжатие с потерями ухудшает детализацию и текстуру. 
Статиска и Поддежка WebP [https://caniuse.com/webp] 
WebP объединяет все достоинства форматов JPEG, PNG и GIF: сжатие с потерями и без потерь, прозрачности и анимации. Это позволяет использовать его для разных изображений, что упрощает подготовку и обработку графики на сайте. 
Кроме того, WebP обладает рядом преимуществ:

   1) сжатие изображения без потерь на 26% лучше, чем у PNG;

   2) сжатие изображения с потерями лучше JPEG на 25-34% при одинаковом индексе структурного сходства (SSIM);

   3) Поддержка прозрачности без потерь при увеличении размера всего на 22%.

AVIF. Статиска и Поддежка [https://caniuse.com/avif]
Это свободный формат сжатия *с потерями качества*, основанный на библиотеке для сжатия кадров AV1 (Википедия). Первая версия спецификации была выпущена в начале 2019 года
    В Google Chrome 85+ и Firefox 93+ загрузится AVIF;

Особенности
 1) значительное уменьшение размера файла при сохранении визуального качества изображения;

 2) Поддержка анимированных изображений;

 3)  Поддержка прозрачности.

***JPEG XL***

И к концу 2021 получило обновление в виде формата *JPEG XL*. Это бесплатный формат с открытым исходным кодом.
Особенностью JPEG XL является возможность повторного сжатия существующих JPEG (которых существует очень много!) в файл JPEG XL, который в среднем на 20% меньше, без потерь. 
Фактически из файла JPEG XL можно восстановить точно такой же файл JPEG.

***Прогрессивное декодирование***

Старый формат JPEG поддерживает прогрессивное декодирование: после передачи всего 15% данных изображения возможен его предварительный просмотр в низком качестве, которое улучшается по мере получения данных. 
Это свойство появилось уже во времена «колёсного» интернета по телефонной линии, но осталось полезным и в наши дни, когда возросли не только скорость соединения, но и разрешение изображений и вариативность сетевых условий. При быстром кабельном соединении или 5G прогрессивное декодирование лишь создаёт ощущение загрузки «шустрее», а вот на более слабом 3G-соединении, которым все мы нередко пользуемся вне дома, разница состоит уже в том, увидите ли вы что-то или не увидите ничего.
Отчасти благодаря популярности MozJPEG в качестве JPEG-кодера «progressive JPEG» стал развиваться быстрее других форматов

Ни один из форматов изображений, возникших из видеоформатов (WebP, HEIC, AVIF) не поддерживает прогрессивное декодирование на уровне кодека, так как это свойство характерно именно для неподвижных изображений. В видеоформатах предварительный просмотр одного кадра малополезен — если не хватает пропускной способности для буферизации видеоданных на много кадров, воспроизвести видео бесполезно даже пытаться. Видеоформаты имеют собственные решения для работы с различными сетевыми условиями (например, HLS).

Для сравнения: JPEG XL не только поддерживает прогрессивное декодирование, но и выходит за рамки возможностей старого JPEG, например, предоставляет прогрессирование по значимости (saliency-based progression). Это довольно интересно и полезно как для разработчика (отпадает необходимость в сложных «ритуалах с заглушками»), так и для конечного пользователя.


***Параметры сжатия без потер***

JPEG XL позволяет сжимать изображения без потерь лучше, чем это умеют существующие форматы (в частности PNG). Причём лучше по всем параметрам: он быстрее кодируется, создаёт меньшие по размеру файлы и даёт больше возможностей (например, CMYK, слои и 32-битные образцы с плавающей точкой). 

**Мы рассмотрели 6 аспектов, в которых JPEG XL показывает себя значительно лучше других форматов:**

    Повторное сжатие JPEG без потерь.
    Прогрессивное декодирование.
    Параметры сжатия без потерь.
    Параметры сжатия с потерями.
    Развёртываемый кодер.
    Работа со всей последовательностью выполняемых действий.


Насколько эти преимущества «достаточны», пусть каждый рассудит сам. На мой взгляд, уже одного из них было бы достаточно. Но самое главное — JPEG XL вносит эти дополнительные преимущества не в ущерб другим характеристикам, по крайней мере не в ущерб основным техническим преимуществам. Разумеется, с точки зрения совместимости и признания каждый формат должен пройти долгий путь, чтобы догнать JPEG и PNG, существующие дольше


Во время JPEG были более технолоничные форматы сжатия с потерями MozJPEG. JXL технологичней кодирования ключевых кадров из VP8. 
Про убогий GIF ,я вообще молчу. А мозилла продвигала APNG
Да и PNG недалеко ушёл — о божечки, мы придумали жать изображение в ZIP!! 
