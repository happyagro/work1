# Отчёт о тестировании Credit Card Number Validator

## Краткое описание

30.03.2021 - 31.03.2021 было проведено тестирование функциональности приложения Credit Card Number Validator.

На тестирование затрачено: 24 часа

В результате тестирования выявлены следующие дефекты:

**Карты с длинной номера меньше чем 16 символов не работают** [скрин кода](https://monosnap.com/file/hQSR3tdjCWjI98fRvcENf6601w3fJC)
## Пример:
* Ошибка при попытке валидации номера карты American Express - [Issue#1](https://github.com/happyagro/work1/issues/1#issue-845299750)
* Ошибка при попытке валидации номера карты Diners Club - Carte Blanche - [Issue#2](https://github.com/happyagro/work1/issues/2#issue-845299880)


## Описание процесса тестирования

В процессе тестирования использовались следующие артефакты:

* Тестовый сценарий:

1. Взять код из [задачи](https://github.com/netology-code/javaqa-homeworks/tree/master/intro)
```java
public class Main {
  public static void main(String[] args) {
    // TODO: подставлять номер карты нужно сюда между двойными кавычками, без пробелов
    String number = "5351719427810741";
    System.out.println(String.format("Result is %s", isValidCardNumber(number) ? "OK" : "FAIL"));
  }

  public static boolean isValidCardNumber(String number) {
    if (number == null) {
      return false;
    }

    if (number.length() != 16) {
      return false;
    }

    long result = 0;
    for (int i = 0; i < number.length(); i++) {
      int digit;
      try {
        digit = Integer.parseInt(number.charAt(i) + "");
      } catch (NumberFormatException e) {
        return false;
      }

      if (i % 2 == 0) {
        digit *= 2;
        if (digit > 9) {
          digit -= 9;
        }
      }
      result += digit;
    }

    return (result != 0) && (result % 10 == 0);
  }
}
```
2. Произвести ввод данных карт с сайта [freeformatter](https://www.freeformatter.com/credit-card-number-generator-validator.html)
2. В четвертой строке "String number" в ковычках вставлять номера карт и запускать код сочетанием клавиш Shift+F10
2. Зафиксировать результат теста в репорте




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

Тестирование производилось в следующем окружении:
* Windows 10 Pro x64
* Java "11.0.10" 2021-01-19
* IntelliJ IDEA Community Edition "2020.3.3"
