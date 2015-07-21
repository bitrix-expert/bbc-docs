# Компоненты

## elements

Компонент-пример.

Комплексный компонент, обеспечивающий роутинг страниц.

## elements.list

Компонент-пример.

Выводит список элементов инфоблоков, устанавливает 404-й статус, генерирует строку постраничной навигации и предоставляет функционал трейта `Elements`.

На каждой итерации обработки результатов выборки элементов инфоблока вызывается метод `processingElementsResult()`, в котором можно модифицировать записываемый элемент в массив `arResult`, либо вовсе пропустить итерацию. Для этого необходимо создать дочерний компонент.

```php
<?php

namespase Myproject\Components;

use Bex\Bbc\Components\ElementsList;

class TestList extends ElementsList
{
	protected function processingElementsResult($element)
	{
		// Зададим другое значение названию элемента
		$element[‘NAME’] = ‘Тест’; 
		
		return $element;

		// Или пропустим итерацию, вернув «ложь»:
		return false;
	}
}
```

## elements.detail

Компонент-пример.

Выводит элемент инфоблока, устанавливает 404-й статус и предоставляет функционал трейта `Elements`.

На каждой итерации обработки результатов выборки элементов инфоблока вызывается метод `processingElementsResult()`, в котором можно модифицировать записываемый элемент в массив `arResult`. Для этого необходимо создать дочерний компонент.

```php
<?php

namespase Myproject\Components;

use Bex\Bbc\Components\ElementsDetail;

class TestDetail extends ElementsDetail
{
	protected function processingElementsResult($element)
	{
		// Зададим другое значение названию элемента
		$element[‘NAME’] = ‘Тест’; 
		
		return $element;
	}
}
```
