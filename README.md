# Домашнее задание к занятию «SQL. Часть 1» - Кощеев Иван

### Задание 1

Получите уникальные названия районов из таблицы с адресами, которые начинаются на “K” и заканчиваются на “a” и не содержат пробелов.

### Ответ

<details>
  
```

SELECT DISTINCT district
FROM address
WHERE district LIKE 'K%a'
  AND district NOT LIKE '% %';

```

![image1](https://github.com/SirSeoPro/11-03/blob/main/1.png)

</details>
  
### Задание 2

Получите из таблицы платежей за прокат фильмов информацию по платежам, которые выполнялись в промежуток с 15 июня 2005 года по 18 июня 2005 года **включительно** и стоимость которых превышает 10.00.

### Ответ

<details>
  
```

SELECT *
FROM payment
WHERE DATE(payment_date) BETWEEN '2005-06-15' AND '2005-06-18'
  AND amount > 10.00;

```

![image5](https://github.com/SirSeoPro/11-03/blob/main/5.png)

</details>
  
### Задание 3

Получите последние пять аренд фильмов.

### Ответ

<details>
  
```

SELECT *
FROM rental
ORDER BY rental_date DESC
LIMIT 5;

```

![image3](https://github.com/SirSeoPro/11-03/blob/main/3.png)

</details>
  
### Задание 4

Одним запросом получите активных покупателей, имена которых Kelly или Willie. 

Сформируйте вывод в результат таким образом:
- все буквы в фамилии и имени из верхнего регистра переведите в нижний регистр,
- замените буквы 'll' в именах на 'pp'.

### Ответ

<details>
  
```

SELECT 
  LOWER(REPLACE(first_name, 'll', 'pp')) AS first_name_transformed,
  LOWER(last_name) AS last_name_transformed
FROM customer
WHERE active = 1
  AND first_name IN ('Kelly', 'Willie');

```

![image4](https://github.com/SirSeoPro/11-03/blob/main/4.png)

</details>

![image4](https://github.com/SirSeoPro/11-03/blob/main/4.png)
