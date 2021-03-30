# Отчёт о тестировании Credit Card Number Validator

## Краткое описание

30.03.2021 - 31.03.2021 было проведено тестирование функциональности приложения Credit Card Number Validator.

На тестирование затрачено: 24 часа

В результате тестирования выявлены следующие дефекты:
* Ошибка при попытке валидации номера карты American Express - https://github.com/happyagro/work1/issues/1#issue-845299750
* Ошибка при попытке валидации номера карты Diners Club - Carte Blanche - https://github.com/happyagro/work1/issues/2#issue-845299880
* Ошибка при попытке валидации номера карты Diners Club - Carte Blanche - https://github.com/happyagro/work1/issues/3#issue-845299985

## Описание процесса тестирования

В процессе тестирования использовались следующие артефакты:
* Тест-кейс



В качестве тестовых данных использовались данные с сайта [freeformatter](https://www.freeformatter.com/credit-card-number-generator-validator.html#validate)
* VISA: 4485043088436171
* VISA: 4024007110646378
* MASTERCARD: 5390407634700573
* MASTERCARD: 5422677190892806
* MASTERCARD: 5444973267710672
* AMERICAN EXPRESS: 340841853970974
* MAESTRO: 5018826143335880
* MAESTRO: 0604705992323489
* MAESTRO: 6762969906331310
* DINERS CLUB - CARTE BLANCHE: 30128287441748
* DINERS CLUB - CARTE BLANCHE: 30219204824163

Тестирование производилось в следующем окружении:
* Windows 10 Pro x64
* Java "11.0.10" 2021-01-19
* IntelliJ IDEA Community Edition "2020.3.3"