# Домашнее задание к занятию 2.1 Массивы одномерные
## Задача 1. Покупка товаров

### Описание
Вы пишете программу, планирующую продуктовую корзину.  
У вас есть список доступных продуктов в одном массиве и соответствующая им цена в другом массиве.
Пользователь вводит номер продукта из первого списка и количество продуктов этого вида, которое хочет купить. 
Программа добавляет стоимость продукта, умноженную на его количество, в итоговую сумму продуктовой корзины. 
Действие повторяется до тех пор, пока пользователь не введет команду "end".

### Функционал программы
1. Создание массива продуктов внутри программы (без пользовательского ввода);
2. Создание массива цен на продукты (без пользовательского ввода);
3. Вывод списка доступных для покупки продуктов на экран;
4. Возможность ввода пользователем номера продукта и количества для добавления в корзину;
5. Вывод всех покупок, их общую стоимость и количество на экран.

### Пример
```
Список возможных товаров для покупки
1. Молоко
2. Хлеб
3. Гречневая крупа
Выберите товар и количество или введите `end`
1 10 <enter>
Выберите товар и количество или введите `end`
3 1 <enter>
Выберите товар и количество или введите `end`
end <enter>
Ваша корзина:
Наименование товара   Количество  Цена/за.ед  Общая стоимость
Молоко                10          60          600
Гречневая крупа       1           50          50
                                  Итого       650
```

### Пример реализации
Итак, у нас есть список доступных продуктов в одном массиве:
```  
String[] products = new String[]{"Хлеб", "Яблоки", "Молоко"}; 
```
и соответствующие цены в другом массиве:
```  
int[] prices = new int[]{100, 200, 300};
```
1. При запуске программы необходимо вывести продукты и цены на экран пользователя:
 ```
 System.out.println(Arrays.toString(products));
 System.out.println(Arrays.toString(prices));
```
2. Нужно создать переменную, в которой сохранятся значения, вводимые пользователем. Допустим, что:

для номера продукта — это переменная: ```  int productNumber = 0;```

для количества это — переменная:```   int productCount = 0;```

По номеру нужно найти цену продукта в массиве цен. 
 ```
  int currentPrice = prices[productNumber];
 ```
3. Ввод данных нужно организовать, используя цикл while. Для проверки на ввод end использовать inputString.equals("end"), оператор == со строками не работает.

4. Необходимо вывести понятные пользователю приглашения на ввод требуемых данных.

5. Нужно привести введенное значение к числовому типу.
```
    Integer.parseInt(inputString)
```
6. Далее нужно создать переменную, которая будет хранить в себе итоговою сумму. 
 ```
    int sumProducts = 0;
 ``` 
К сумме переменной надо добавлять сумму желаемого товара после каждого ввода. 
7. После того как пользователь введет `end`, программа выйдет из цикла. На экран нужно вывести итоговую сумму продуктовой корзины.