---
tags:
  - practice
permalink: false
---

🛠 В атрибуте `src` не всегда обязательно нужно указывать адрес конкретной картинки. Например, можно прописать исходный код этого изображения. Обычно так делают, с маленькими иконками в формате PNG: просто прописываешь код изображения в формате base64, который состоит всего из двух строчек. Это чтобы браузер не качал лишний раз откуда-то сторонний элемент. Ведь у браузера есть ограничения. Если ты запустишь сайт, где много картинок и каждая подгружается извне, то он будет грузиться долго.

🛠 Точно так же можно подгружать SVG-картинки. Иконки лучше подгружать в векторе: они так весят меньше и сжимаются хорошо, и под любое разрешение экрана подстраиваются без всяких дополнительных атрибутов.

🛠 Очень важен атрибут `srcset`: в нём прописываются варианты картинки для других экранов. Допустим, если ты на обычном Windows-экране откроешь картинку с разрешением 72dpi, она по умолчанию в таком разрешении и откроется. Но на Mac та же картинка будет выглядеть размыто, потому что Mac по умолчанию использует разрешение в два раза больше — 144dpi. Поэтому ты можешь указать, например, для больших экранов 2k или 4k более крупную картинку. Или даже вертикальную картинку для отображения на мобильных, чтобы она красивее отображалась и не обрезалась. Всё это надо указывать именно в `<img>`.