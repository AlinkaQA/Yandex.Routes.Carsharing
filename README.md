# <a name="up" />Проект Яндекс Маршруты. Каршеринг



Яндекс.Маршруты - это онлайн-сервис от компании Яндекс, предоставляющий пользователям возможность быстро и удобно планировать путешествия и маршруты. Сервис предлагает подробную информацию о дорожной ситуации, различные варианты маршрутов для пешеходов, велосипедистов и водителей, а также прокладывает оптимальные маршруты с учетом текущего движения, пробок и других факторов.
Теперь в приложении можно заказать каршеринг. 

## Содержание
- [Задачи тестировщика](#задачи-тестировщика)
- [Требования к проекту](#требования-к-проекту)
- [Инструменты](#инструменты)
- [Процесс работы](#процесс-работы)
  - [1 спринт](#1-спринт)
## Задачи тестировщика

<details>
<summary> 1-спринт </summary> 

#### Задачи для 1 спринта

1. Подготовить чек-лист на вёрстку полей.
- Изучить требования и макеты. Выбрать один тариф. Если требования и макеты не сходятся — ориентироваться на требования. 
- Составить чек-лист на вёрстку следующих блоков:
  форма бронирования;
  элементы на навигационной карте: это иконки автомобилей и действия с ними.
2. Подготовить чек-лист и тест-кейсы на логику работы окон
- Составить следующую тестовую документацию: 
чек-лист на логику окон «Способ оплаты» и «Добавление карты»,
тест-кейсы на кнопку «Забронировать»
3. Протестировать приложение и завести баг-репорты.
  
  ***

</details>

## Требования к проекту

<details>
<summary>Требования к сервису Яндекс Маршруты 2.0 </summary>

### Общее описание
Пользователю нужно открыть Яндекс.Маршруты и корректно заполнить поля «Откуда» и «Куда». Приложение построит маршрут, а под полями «Откуда» и «Куда» отобразятся режимы поездки: «Оптимальный», «Быстрый», «Свой».

- Если выбрать режим «Оптимальный» или «Быстрый», система автоматически назначит способ передвижения: на авто, пешком, на такси, на самокате, на велосипеде, на каршеринге. Выбрать его самостоятельно нельзя — иконки неактивны.
- Если выбрать режим «Свой», способ передвижения можно поменять — иконки активны.

### Макеты
<img width="1484" alt="главная" src="https://github.com/user-attachments/assets/f24c5c53-9e01-49c9-be0e-3efac7ef7797" />
<img width="1171" alt="каршеринг 1" src="https://github.com/user-attachments/assets/328e1fb2-bc09-4f2b-9a46-be2f4a01073e" />
<img width="650" alt="каршеринг 2" src="https://github.com/user-attachments/assets/a485e8b7-ccba-4d0d-8838-133a270706fe" />
<img width="650" alt="оплата" src="https://github.com/user-attachments/assets/ca724e3e-472b-45ac-b3b4-765b4a301cea" />
<img width="1376" alt="добавление" src="https://github.com/user-attachments/assets/675186c5-7532-492a-bde2-9f2da4d02f3d" />
<img width="1094" alt="бронь" src="https://github.com/user-attachments/assets/61e76de7-6245-4bd9-ba04-4ee74713eedd" />
<img width="1132" alt="отмена" src="https://github.com/user-attachments/assets/779fa0cb-6645-4525-9457-d2076a4661f6" />

### Аренда машины

Арендовать машину можно в двух случаях:

- Если приложение предлагает тип транспорта «Каршеринг» в режиме «Оптимальный» или «Быстрый».
- Если пользователь выбирает тип транспорта «Каршеринг» в режиме «Свой».

Под названиями режимов появится информация о стоимости и продолжительности поездки, а также кнопка «Забронировать».

<img width="720" alt="Снимок экрана 2025-01-22 в 18 44 48" src="https://github.com/user-attachments/assets/104578b1-bf49-4f30-b757-664a06e932e4" />

Если нажать кнопку «Забронировать», вместо панели с названиями режимов появится форма бронирования. В форме нужно выбрать тариф, добавить информацию о водительских правах, указать способ оплаты. Дополнительно можно перечислить требования к заказу.Под «Требованиями к заказу» расположена кнопка «Забронировать». См. таблицу «Состояние кнопки».Если пользователь передумал арендовать машину, он может вернуться назад — это иконка со стрелкой влево. На экране снова откроется блок, где нужно выбрать способ передвижения.

### Форма бронирования
На экране бронирования можно удалять адреса — они необязательны для заказа каршеринга. Пользователь может выбрать нужную машину на карте.

<img width="588" alt="Снимок экрана 2025-01-22 в 18 46 43" src="https://github.com/user-attachments/assets/26959f8c-6974-458d-8769-cda47c5897b1" />
<img width="571" alt="Снимок экрана 2025-01-22 в 18 47 02" src="https://github.com/user-attachments/assets/abbc5e1a-560c-4118-8915-d5d733887d76" />

По умолчанию выбран тариф «Повседневный», поля «Добавить права» и «Способ оплаты» не заполнены.

Выбранный тариф подсвечивается серым. Под ним расположен блок с деталями тарифа и информацией о ближайшей машине:

- марка;
- описание тарифа;
- время в пути от пункта «Откуда» до машины — не будет отображаться, если пользователь удалит адрес в поле «Откуда»;
- время бесплатного ожидания;
- изображение машины;
- дополнительные параметры.

Система автоматически выбирает ту машину, которая находится ближе всего к пользователю. На карте иконка ближайшей машины увеличивается, над ней появляется чёрная плашка с маркой машины.

Остальные свободные машины продолжают отображаться на карте в виде иконок. При этом показываются автомобили всех тарифов. Пользователь может выбрать машину на карте и забронировать: он нажимает на иконку, она увеличивается, над ней появляется чёрная плашка с маркой, а на левой панели — обновлённая информация о машине.

Если пользователь ещё не привязал банковскую карту, вместо слова «Карта» стоит слово «Добавить». Без карты забронировать машину нельзя.

По умолчанию приложение показывает точную стоимость поездки. Она рассчитывается по формуле — см. пункт «Формула расчёта тарифов». Если удалить хотя бы один адрес из полей «Откуда» или «Куда», отобразится стартовая цена за минуту.

<img width="383" alt="Снимок экрана 2025-01-22 в 18 47 59" src="https://github.com/user-attachments/assets/4393f2e3-0ec6-4d7e-a9b3-b55dec17b8e4" />

### Панель «Выбор тарифа
Есть три тарифа. Каждый элемент состоит из иконки автомобиля, названия тарифа, цены.
Один из тарифов всегда выбран. По умолчанию это тариф «Повседневный», но его можно изменить.

### Описания тарифов
Под списком тарифов есть блок с подробным описанием выбранного тарифа

<img width="670" alt="Снимок экрана 2025-01-22 в 18 49 07" src="https://github.com/user-attachments/assets/596b3984-24a9-432d-bb89-983146a9e664" />
<img width="724" alt="Снимок экрана 2025-01-22 в 18 49 13" src="https://github.com/user-attachments/assets/2513904d-7ee3-4169-9bf1-ec74f4d5e4f7" />

### Формула расчёта стоимости тарифов
Стоимость тарифа рассчитывается по формуле:
*фиксированная стоимость аренды в рублях + (60 * стоимость минуты поездки в рублях * продолжительность поездки в часах) * коэффициент тарифа = стоимость поездки*
Например, стоимость поездки по тарифу «Повседневный»:
*150 + (60 * 6 * 1.25) * 1.5 = 825*
Пояснения к формуле:
- **150** — фиксированная стоимость аренды в рублях;
- **60** — минут в одном часе;
- **6** — стоимость минуты поездки на каршеринге в рублях;
- **1.25** — продолжительность поездки в часах;
- **1.5** — коэффициент тарифа «Повседневный».
**Коэффициенты:**
- Повседневный: 1.5.
- Походный: 2.
- Роскошный: 3.
**Продолжительность поездки** **в часах** рассчитывается так: расстояние / скорость.
- Расстояние — см. таблицу с адресами в общих требованиях.
- Скорость — см. таблицу со скоростями в общих требованиях.

### Поле «Добавить права»

<img width="537" alt="Снимок экрана 2025-01-22 в 18 52 01" src="https://github.com/user-attachments/assets/1c2776f6-d396-4c21-bf18-051a09cc9591" />

Если не добавить водительское удостоверение, забронировать машину не получится.
По умолчанию поле «Добавить права» не заполнено. Когда пользователь нажимает на поле, появляется окно «Добавление прав». В нём нужно ввести имя, фамилию, дату рождения и номер водительского удостоверения.
Текст, который вводит пользователь, чёрного цвета.
Когда пользователь внёс все данные, появляется сообщение: «Спасибо! Документы отправлены на проверку. Скоро расскажем о результатах». Под сообщением — кнопка «Понятно».
Если нажать кнопку «Понятно», окно закроется, а в поле «Добавить права» появится таймер на 30 секунд. Через 30 секунд система сообщает, прошли ли документы верификацию.

<img width="627" alt="Снимок экрана 2025-01-22 в 18 52 49" src="https://github.com/user-attachments/assets/b47ebf2c-c037-42f2-841f-17c4abd9ec7b" />

### **После верификации**
Если документы прошли верификацию, рамка поля подсвечивается зелёным, у правого края внутри поля появляется зелёная галочка. Пользователь больше не сможет редактировать данные водительского удостоверения. Несколько водительских удостоверений добавить нельзя.
Если документы не прошли верификацию, рамка поля подсвечивается красным, у правого края внутри поля появляется красный крестик. Если нажать на поле, снова откроется форма «Добавление прав». Над формой — текст сообщения: «Ваши документы не прошли верификацию. Попробуйте ещё раз».

### Поле «Способ оплаты»
По умолчанию поле не заполнено. Чтобы забронировать машину, нужно ввести реквизиты хотя бы одной карты и нажать кнопку «Привязать». Можно добавить неограниченное количество карт. 
При нажатии на поле «Способ оплаты» открывается окно «Способ оплаты» с возможностью привязать новую карту или выбрать уже привязанную.
Чтобы добавить новую, нужно нажать на кнопку «Добавить карту». После этого откроется окно «Добавление карты».
При успешном добавлении новой карты и нажатии на кнопку «Привязать» происходит переход обратно на форму выбора карт.
Чтобы выбрать карту, её нужно отметить и нажать на кнопку выхода из формы. Если карта одна, она выбирается автоматически.
После выхода из формы поле «Способ оплаты» заполнено данными выбранной карты.

### Окно «Добавление карты»

<img width="636" alt="Снимок экрана 2025-01-22 в 18 53 57" src="https://github.com/user-attachments/assets/7ce88abe-80ea-4066-b04d-3ba764d1b12c" />
<img width="622" alt="Снимок экрана 2025-01-22 в 18 54 03" src="https://github.com/user-attachments/assets/f5675ae9-dce1-4b65-91ce-ce6287c7801f" />

Когда карта добавлена, в интерфейсе отображаются последние 4 цифры её номера. Так пользователь может узнавать и отличать свои карты.

## Панель «Требования к заказу»
Это выпадающий список. Он свёрнут, если выбран тариф по умолчанию — «Повседневный». Если пользователь выбирает другой тариф, список автоматически раскрывается. И наоборот: если вернуться к тарифу «Повседневный», панель «Требования к заказу» свернётся.
У каждого тарифа содержимое панели разное.
Панель можно скроллить.

<img width="626" alt="Снимок экрана 2025-01-22 в 18 55 02" src="https://github.com/user-attachments/assets/6f3b8867-7460-48c7-8aab-0c4858bf94bb" />

### Кнопка «Забронировать»
Кнопка закреплена в левом нижнем углу экрана.

<img width="629" alt="Снимок экрана 2025-01-22 в 18 55 56" src="https://github.com/user-attachments/assets/16acd9b0-f21f-4d0d-baab-fc5eb4c08c02" />

### Бронь машины
Если пользователь корректно заполнил все поля и нажал кнопку «Забронировать», в центре экрана появится окно с заголовком «Машина забронирована». Внутри — марка, номер, иконка и адрес машины, а также стоимость поездки и таймер, который отсчитывает время бесплатного ожидания.
Если поля «Откуда» и «Куда» заполнены, отображается точная стоимость поездки. Если нет — стоимость за минуту.

### Таймер
- Таймер начинает отсчитывать время бесплатного ожидания, когда пользователь нажимает кнопку «Забронировать».
- Пока таймер работает, можно бесплатно отменить заказ.
- Когда время бесплатного ожидания заканчивается, таймер начинает отсчитывать время пользования каршерингом.









