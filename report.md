# Отчёт о тестировании **Credit Card Number Validator**

## Краткое описание

Дата начала тестирования 14/08/2021. 

Дата окончания тестирования 15/08/2021. 

Было проведено:

* функциональное тестирование
* тестирование критического пути
* белый ящик

Приложения:
* Credit Card Number Validator - [JAVA Codeshare](https://codeshare.io/EBoeDv) 
* git version 2.32.0.windows.2
* intelliJ IDEA 2021.02

На тестирование затрачено: 5 часов с оформлением

В результате тестирования выявлены следующие дефекты:
* [Не производиться валидация вип карт Diners Club - Carte Blanche (14 знаков в номере)](https://github.com/greengrover/Credit-Card-Number-Validator/issues/1)
* [Не производиться валидация вип карт Diners Club - International (14 знаков в номере)](https://github.com/greengrover/Credit-Card-Number-Validator/issues/2)
* [Не производиться валидация карт American Express (AMEX) (15 знаков в номере)](https://github.com/greengrover/Credit-Card-Number-Validator/issues/3)
* [Не производиться валидация карт VISA (19 знаков в номере)](https://github.com/greengrover/Credit-Card-Number-Validator/issues/4)
* [Не производиться валидация карт Discover (19 знаков в номере)](https://github.com/greengrover/Credit-Card-Number-Validator/issues/5)
* [Не производиться валидация карт JCB (19 знаков в номере)](https://github.com/greengrover/Credit-Card-Number-Validator/issues/6)

## Описание процесса тестирования

В процессе тестирования использовались следующие артефакты:
* баг-репорты
* работа с отладчиком
* Credit Card Number Generator
* отчет о тестировании


В качестве тестовых данных использовались данные сгенирированных номеров карт в сервисе [Credit Card Number Generator](https://www.freeformatter.com/credit-card-number-generator-validator.html) в разрезе каждой платежной системы:
1. VISA - 16-тизначный номер карты. Ожидаемый результат: Result is OK
1. VISA - 19-тизначный номер карты. Ожидаемый результат: Result is OK
1. Discover - 16-тизначный номер карты. Ожидаемый результат: Result is OK
1. Discover - 19-тизначный номер карты. Ожидаемый результат: Result is OK
1. Diners Club - Carte Blanche - 14-тизначный номер карты. Ожидаемый результат: Result is OK
1. Visa Electron - 16-тизначный номер карты. Ожидаемый результат: Result is OK
1. MasterCard - 16-тизначный номер карты. Ожидаемый результат: Result is OK
1. JCB - 16-тизначный номер карты. Ожидаемый результат: Result is OK
1. JCB - 19-тизначный номер карты. Ожидаемый результат: Result is OK
1. Diners Club - International - 14-тизначный номер карты. Ожидаемый результат: Result is OK
1. InstaPayment - 16-тизначный номер карты. Ожидаемый результат: Result is OK
1. American Express (AMEX) - 15-тизначный номер карты. Ожидаемый результат: Result is OK
1. Diners Club - North America - 16-тизначный номер карты. Ожидаемый результат: Result is OK
1. Maestro - 16-тизначный номер карты. Ожидаемый результат: Result is OK

*Тестирование производилось в следующем окружении:*
* Windows 10 х64
* openjdk version "11.0.11" 2021-04-20
* git version 2.32.0.windows.2
* intelliJ IDEA 2021.02

**Вывод:**

Указанный код принимает в расчет только карты с количеством символов равном 16-ти. Любые карты с меньшим или большим количеством цифр в номере Валидаром не валидируются. 