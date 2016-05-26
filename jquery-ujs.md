#### Cкриптинг с jquery-ujs
Все это есть в [wiki](https://github.com/rails/jquery-ujs) jquery-ujs

Библиотека jquery-ujs позволяет перехватывать и назначать события для элементов при помощи data-атрибутов:  

**data-confirm** - позволяет перехватить нажатие на ссылку или отправку формы и вызвать JavaScript диалог `confirm()`. Можно повесить на кнопку `submit`, но тогда нужно убрать его с самой формы. Можно кастомизировать, прослушивая событие `confirm`. 
```html
<form data-confirm="Are you sure you want to submit?">...</form>
```
**data-disable-with** - позволяет показать что кнопка отправки или ссылка отключены пока форма отправляется. Это предотвращает дабл-клики от пользователя в результате которых произойдет дублирование запросов на сервер. Значение атрибута это новый текст для кнопки в отключенном состоянии.  
```html
<input type="submit" value="Save" data-disable-with="Saving...">
```
**data-method** - позволяет заставить ссылку "использовать" метод отправки отличный от GET.
```html
<a href="..." data-method="delete" rel="nofollow">Delete this entry</a>
```
**data-remote** - указывает что ссылка или форма работают асинхронно - без перезагрузки страницы. Если бекенд возвращает фрагменты JS, они будут выполнены когда запрос завершится.
```html
<form data-remote="true" action="...">
  ...
</form>
```
**data-type** - позволяет явно указать `dataType` атрибут для AJAX
```html
<form data-remote="true" data-type="json">...</form>
```
**data-url и data-remote** - позволяют отправить AJAX запрос на указанный URL после события `change` элемента. Подходит для `textarea`, `input`, `select`.
```html
<input type="checkbox" name="task" id="task" value="1" data-url="/tasks/1" data-remote="true" data-method="post">
```
**data-params** - позволяет передавать дополнительные параметры в запросе
```html
<a data-remote="true" data-method="post" data-params="param1=Hello+server" href="/test">AJAX action with POST request</a>
```
