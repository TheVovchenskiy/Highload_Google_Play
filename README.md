# Highload Google Play

**Автор - [Коноплюк Владимир](https://park.vk.company/profile/ko.vladimir/)**

## Содержание
### [1. Тема, целевая аудитория](#1)
### [2. Расчет нагрузки](#2)
### [Список используемых источников](#sources)

## 1. Тема и целевая аудитория <a name="1"></a>

**Google Play** - магазин приложений, позволяющий сторонним компаниям предлагать владельцам устройств с операционной системой Android устанавливать и приобретать различные приложения.

### MVP
- основные страницы (главная, страницы приложений, каталог)
- поисковая система для нахождения приложений
- регистрация и аутентификация пользователей
- система загрузки приложений
- административная панель управления приложением
- система управления версиями приложений
- система отзывов и рейтинга приложений

### Целевая аудитория
- 2.5 млрд пользователей в месяц [^1]
- более 190 рынков по всему миру [^1]
- 49% - женщины, 51% - мужчины [^2]
- количество авторов в магазине: 1.2 млн [^2]

#### Распределение пользователей по возрасту [^4]
| Возрастная группа |	Проведено часов в месяц |
| --------- | --------------------------- |
| 18-24 |	112.6 |
| 25-34 |	102.4 |
| 35-44 |	93.6 |
| 45-54 |	75.6 |
| 55-64 |	69.3 |
| 65+ |	51.4 |

#### Распределение пользователей по странам [^4]
| Страна | 	Количество часов проведено, млрд ч |
| ------- | ------------- |
| China | 	1,182 |
| India  |	669 |
| United States |	194 |
| Brazil |	193 |
| Indonesia |	155 |
| Pakistan |	133 |
| Philippines | 	109 |
| Russia |	108 |
| Mexico |	99 |
| Vietnam |	79 |

### Статистика контента
- количество скачиваний приложений: 63 млрд в год [^2]
- количество скачиваний игр: 50 млрд в год [^2]
- количество приложений в магазине: 3.7 млн [^5]
- 97% приложений - бесплатные [^3]
- соотношение количества игр к приложениям - игры: 12.69%, приложения: 87.31% [^6]
- соотношение приложений с рейтингом и без - с рейтингом: 49.54%, без рейтинга: 50.46% [^6]
- среднее количество отзывов на приложение: 967 [^10]

## 2. Расчет нагрузки <a name="2"></a>

### Продуктовые метрики
- MAU - 2.5 млрд. пользователей [^1]
- DAU - (?)

#### Среднее количество действий пользователя по типам в день
- количество скачиваний приложений: 63 млрд в год [^2] => 172.6 млн скачиваний приложений в сутки
- количество скачиваний игр: 50 млрд в год [^2] => 137.0 млн скачиваний игр в сутки
- среднее количество выпускаемых приложений в день - 2 166 [^2]
- среднее количество выпускаемых игр в день - 314.8 (?)

#### Средний размер хранилища пользователя
| Данные | Оценочный размер |
| ------ | ---------------- |
| Данные профиля (с аватаром) | `50 KB` |
| Размер приложения | `11.5 MB` [^7] |
| Размер игры | `465 MB` [^8] |
| Размер отзыва | `1 KB` |

### Технические метрики
В качестве значения количества пользователей возьмем следующее значение: 70% от 7.1 млрд пользователй всех мобильных устройств [^9]. Получим значение `4.97 млрд пользователй`.

Тогда общий размер хранилища:

`4.97 млрд * 50 KB + 0.87 * 3.7 млн * 11.5 MB + 0.13 * 3.7 млн * 465 MB + 967 * 3.7 млн * 1 KB = 483.3 TB`

#### RPS
| Тип запроса | RPS |
| ----------- | --- |
| Скачивание приложения | 1997 |
| Скачивание игр | 1586 |
| Загрузка нового приложения | 0.025 |
| Загрузка новой игры | 0.004 |

#### Сетевой трафик
Примем среднюю скорость сети `10 Мбит/с` 

| Тип запроса | Пиковое потребление в теченнии суток (в Гбит/с) |
| ----------- | --- |
| Скачивание приложения | `19.97` |
| Скачивание игр | `15.86` |
| Загрузка нового приложения | `0.00025` |
| Загрузка новой игры | `0.00004` |

Суммарный суточный: `0.360 Пбайт/сутки`

## Список используемых источников <a name="sources"></a>
[^1]: [How Google Play works](https://play.google/howplayworks/)
[^2]: [Google Play Store Revenue, Ratings & Subscription Stats 2024](https://prioridata.com/data/google-play-revenue-statistics/)
[^3]: [Key Google Play Store Statistics in 2024](https://www.pagetraffic.in/blog/google-play-store-statistics/)
[^4]: [Google Play Store Statistics and Trends in 2022- 2023](https://www.emizentech.com/blog/google-play-store-statistics.html)
[^5]: [How Many Apps In Google Play Store? (Feb 2024) (Source: https://www.bankmycell.com/blog/number-of-google-play-store-apps/)](https://www.bankmycell.com/blog/number-of-google-play-store-apps/)
[^6]: [Google Play Statistics and Trends 2024](https://42matters.com/google-play-statistics-and-trends#apps-released-per-day)
[^7]: [Average App File Size: Data for Android and iOS Mobile Apps](https://sweetpricing.com/blog/index.html%3Fp=4250.html#:~:text=Average%20Android%20and%20iOS%20file,file%20size%20is%2034.3MB.)
[^8]: [Average mobile game file size increased 76% over last five years](https://www.businessofapps.com/news/average-mobile-game-file-size-increased-76-over-last-five-years/#:~:text=According%20to%20research%20from%20SensorTower,compared%20to%20465MB%20in%202020.)
[^9]: [Top Google Play Store Statistics 2023 – Exploring The Key Insights]([https://appinventiv.com/blog/google-play-store-statistics/](https://bigohtech.com/google-play-store-statistics/#8_Global_usage_of_play_store_apps)https://bigohtech.com/google-play-store-statistics/#8_Global_usage_of_play_store_apps)
[^10]: [Mobile App Ratings and Reviews: 2022 Benchmarks](https://www.alchemer.com/resources/blog/mobile-app-ratings-and-reviews-2022-benchmarks/)
