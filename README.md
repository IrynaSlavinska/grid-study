\*\*First block
display: grid
column-gap, row-gap, gap
grid-template-columns
grid-template-rows

Технологія CSS Grid дає можливість створювати рядки і колонки всередині нашого сайту та розміщувати елементи всередині клітинок, які утворились внаслідок перетину цих рядків і колонок.

За допомогою різних інструментів CSS Grid ми можемо контролювати скільки клітинок буде займати певний елемент по горизонталі та по вертикалі.

Крок 1 - будь-якому елементу, який виступає в ролі контейнера задати властивість display зі значенням grid (display: grid;).

Властивість display зі значенням inline-grid (display: inline-grid;) дає можливість застосовувати інструменти CSS Grid, при цьому елемент має властивості інлайн-блочних елементів.

Тобто різниця між grid та inline-grid полягає в різниці розміщення елементів в потоці документа.

.grid-item{$}\*10 - створює 10 дівів з класом grid-item, які нумеруються від 1 до 10

Для того, щоб задати певну конфігурацію колонкам, потрібно грід-контейнеру задати властивість grid-template-columns. Ця властивість розказує контейнеру на скільки частинок потрібно розділити його по вертикалі. Можна задавати числовим значенням (наприклад grid-template-columns: 4). Крім того, в значенні одразу можна задавати розміри цих колонок (наприклад grid-template-columns: 100px 200px 400px auto; - перша колонка - 100, друга - 200, третя - 400, четверта - все що лишається з ширини)
Якщо явно не задати розмір рядка, тоді його розміри задаються по розміру контенту

Для того, щоб задати висоту рядів, використовується властивість grid-template-rows, де значенням ми передаємо висоту рядків

Властивості column-gap і row-gap задають відстані між колонками і рядками відповідно.

\*\*Second block
grid-auto-rows
Явна сітка - сітка, яку розробник прописав властивості. Неявна сітка - сітка, створена браузером. Ми задаємо кількість колонок, їхній розмір, висоту. Якщо не вистачає колонок, то наступні елементи браузер переносить на наступний рядок.

Тобто, усі рядки, які створює браузер самостійно - це неявна сітка. Можна контролювати висоту рядків за допомогою властивості grid-auto-rows. Якщо задати одне значення - то всі створені браузером рядки будуть мати однакову висоту. Відповідно, якщо задати значення два числа через пробіл - то висота рядків буде чергуватись.

\*\*Third block
grid-auto-flow

Властивість grid-auto-flow в CSS визначає, як автоматично розміщувати елементи в сітці (grid), якщо вони не явно розташовані за допомогою властивостей, таких як grid-row та grid-column.

За замовчуванням наступні елементи додаються в нові рядочки, коли клітинки (рядки) поточного ряду закінчуються. За замовчування значення даної властивості - row.

При значенні column наступні елементи будуть створювати нові колонки в ряду. Зручно для слайдерів, наприклад.

\*\*Fourth block
1fr (фракція, частинка)

При таких даних grid-template-columns: 100px 100px 200px, сітка не буде займати всю ширину контейнера.

1fr (фракція) — це одиниця виміру в CSS Grid Layout, яка означає "одну частину доступного простору" (fraction of available space). На відміну від пікселів (px), fr не має фіксованого розміру і динамічно визначає частину доступної площі.

Скільки пікселів буде дорівнювати 1fr залежить від контексту, тобто від розміру контейнера, в якому знаходиться Grid, та від кількості інших фракцій, які використовуються.

1fr — це не фіксована величина в пікселях, а частка доступного простору, яка може змінюватись залежно від контексту.

fr можна комбінувати з пікселями.

grid-template-columns: 100px auto 2fr 1fr -- перша колонка ширина 100рх, друга колонка буде займати ширину найбільшого контенту колонки, третя ширина двух фракцій, четверта ширина одна фракція.

\*\*Fifth block
функція repeat()

Для того, щоб зменшити кількість повторень коду, якщо в нас є багато однаковий колонок, можна використати функцію repeat()

grid-template-columns: repeat(number, width)
першим аргументом (number) передаємо скільки колонок необхідно створити, другим аргументом (width) передаємо ширину кожної колонки

Після коми можна передати будь-яку кількість величин
grid-template-columns: repeat(4, 100рх 150рх)
такий запис браузер буде розуміти наступним чином: створи 4 рази комбінацію пар 100рх і 150рх. Тобто, загалом в рядку буде 8 колонок.

repeat() можна комбінувати з іншими записами
