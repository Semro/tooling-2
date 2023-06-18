# Основное задание

## 1. Вкладка Network

1.  [Архив HAR](./network.har)
2.  Неоптимальные места:

    1.  дублирование ресурсов

        - Шрифт `fontawesome-webfont.woff2?v=4.7.0` [(Скрин)](./network_screens/1/font.png) [(Скрин 2)](./network_screens/1/font2.png)
          - Один и тот же шрифт подгружается с разных доменов
        - JS файлы [(Скрин)](./network_screens/1/js.png)
          - bootstrap.bundle.min.js
          - bootstrap.min.js
          - cast_sender.js
          - code.js
          - popper.min.js
        - CSS файлы [(Скрин)](./network_screens/1/css.png)
          - bootstrap.min.css
        - Картинки [(Скрин)](./network_screens/1/images.png)
          - system_gd-logo.png

    1.  лишний размер ресурса

        - Многие JS файлы загружаются без компрессии [(Скрин)](./network_screens/2/non-compressed-js.png)
          - sdk.js
          - sdk_review.js
          - widget.js
          - main.min.js

    1.  медленно загружающиеся ресурсы

        - Eсть недоступные ресурсы [(Скрин)](./network_screens/3/slow.png)
          - ad_status.js
          - запрос на https://googleads.g.doubleclick.net/pagead/id

## 2. Вкладка Performance

1.  [Профиль загрузки страницы](./perfomance.json)

1.  | Cобытие                        | Время в ms |
    | ------------------------------ | ---------- |
    | First Paint (FP)               | 513.3      |
    | First Contentful Paint (FCP)   | 513.3      |
    | Largest Contentful Paint (LCP) | 1381.3     |
    | DOM Content Loaded (DCL)       | 1179.2     |
    | Load                           | 31050.2    |

1.  LCP происходит на элементе `img`:

    - `<img loading="lazy" src="/images/branding/10/imageTop_1628667062.7856.jpg" data-url="/images/branding/10/imageTop_1628667062.7856.jpg" alt="-">`

    - [Скриншот из DevTools](./LCP_element.png)

1.  | Этап      | Время в ms |
    | --------- | ---------- |
    | Loading   | 41         |
    | Scripting | 2736       |
    | Rendering | 848        |
    | Painting  | 156        |

## 3. Вкладка Coverage

1.  - [Скриншот Coverage](./coverage.png)
    - На всякий случай, есть ещё экспорт вкладки [coverage.json](./coverage.json)

1.  CSS. **574 kB**

1.  JS. **2457.6 kB** (2.4 MB)
