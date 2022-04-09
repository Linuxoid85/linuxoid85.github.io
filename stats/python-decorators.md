# Декораторы в Python. Максимально краткое объяснение.

---

## Содержание

[TOC]

## Введение

Доброго времени суток! Есть люди, которые не понимают декораторов в Python. Среди таких был и я. Поначалу я избегал их использования, но теперь использую. Пусть их применение не повсеместное, но и без этого они могут упростить код и сделать его короче, например.

### Предупреждение

> Здесь я не буду объяснять, что такое декоратор. Это вы можете вычитать в интернете и литературе. Здесь я показываю на реальном примере то, для чего они предназначены и что делают.

## Определение

*Декоратор* - это функция, принимающая в качестве аргумента другую функцию и каким-либо образом изменяя её поведение.

Рассмотрим следующий код:

```
#!/usr/bin/python3

def f():
	print("Hello, World!")

f()
```

Вывод:

```
Hello, World!
```

А теперь применим к ней декоратор, который сами же и напишем:

```
#!/usr/bin/python3

def decorat(func):
	print(f"До вызова функции {func}")
	func()
	print(f"После вызова функции {func}")
	return func

@decorat
def f():
	print("Hello World!")

f()
```

Вывод:

```text
До вызова функции <function func at 0x7faf8fde2680>
Hello, World!
После вызова функции <function func at 0x7faf8fde2680>
```

Сравните выводы обоих скриптов.