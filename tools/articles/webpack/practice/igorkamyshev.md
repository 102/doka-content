---
tags:
  - practice
permalink: false
---

### HtmlWebpackPlugin

На практике не очень удобно вручную создавать html-файлы и вставлять туда файлы сгенерированные Webpack — число и имена файлов могут меняться в зависимости от сборки, поддерживать это вручную довольно сложно. Часто используют `HtmlWebpackPlugin`.

В первую очередь, нужно установить пакет с плагином в проект:

```bash
npm install --save-dev html-webpack-plugin
```

```js
const { HtmlWebpackPlugin } = require("html-webpack-plugin")

module.exports = {
  plugins: [new HtmlWebpackPlugin()]
}
```

При сборке плагин сгенерирует пустой `index.html` в папку с собранным проектом и добавит туда ссылки на финальные JS и CSS файлы. При необходимости плагин [можно кастомизировать](https://github.com/jantimon/html-webpack-plugin).

### path

`path` — это встроенный в Node.js модуль для работы с путями. Чтобы не беспокоиться об особенностях разных операционных систем, лучше всегда при работе с путями в файловой системе использовать модуль `path`.

:::callout 🤓

Например, в разных операционных системах используется разных разделитель путей — косая черта `/` или обратная косая черта `\`.

:::

В нём есть несколько полезных для конфигурации Webpack функций:

- `path.resolve` — функция, которая принимает любое число сегментов пути и возвращает абсолютный путь, работает так:

```js
path.resolve("/foo/bar", "./baz") // "/foo/bar/baz"
path.resolve("/foo/bar", "/tmp/file/") // "/tmp/file"

// Если текущая рабочая директора /home/user
path.resolve("www", "static_files/png", "../gif/image.gif")
// "/home/use/www/static_files/gif/image.gif"
```

- `path.sep` — строка разделителя путей в текущем окружении (`/` или `\`);

- `path.extname` — функция, которая принимает строку с именем файла и возвращает расширение этого файла.

[Подробная документация по модулю `path`](https://nodejs.org/docs/latest-v14.x/api/path.html).