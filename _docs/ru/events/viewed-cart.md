---
layout: page
section: eventsRU
title: "Viewed Cart"
order: 2
---
`Viewed Cart` - это событие, которое должно быть добавлено в `digitalData.events` при загрузке страницы корзины. В случае, если по клику на ссылку с корзиной не происходит загрузка новой страницы, а открывается попап с содержимым корзины - также следует отправить событие `Viewed Cart`.

### Из кода сайта / при использовании AJAX
```javascript
digitalData.events.push({
  category: 'Ecommerce',
  name: 'Viewed Cart'
});
```

### Из интерфейса SegmentStream
**Триггер**: событие `Viewed Page`
```javascript
if (_digitalData('page.type') === 'checkout') {
  return {
    category: 'Ecommerce',
    name: 'Viewed Cart'
  };
}
```

### Необходимо для работы интеграций:
* Adwords
* Criteo
* MyTarget
* RTB House
* Sociomantic
* Segmento