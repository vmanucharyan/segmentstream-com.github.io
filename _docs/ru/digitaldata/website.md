---
layout: page
section: digitalDataRU
title: "website"
order: 1
---

Объект `digitalData.website` содержит в себе переменные, которые описывают сайт в целом: язык, регион, валюту и т.д.

### Навигация по странице
------
<ul class="page-navigation">
  <li><a href="#0">Введение</a></li>
  <li><a href="#1">website.region</a></li>
  <li><a href="#2">website.regionId</a></li>
  <li><a href="#3">website.type</a></li>
  <li><a href="#4">website.language</a></li>
  <li><a href="#5">website.currency</a></li>
  <li><a href="#6">website.environment</a></li>
</ul>


### <a name="0"></a>Введение
------
Объект `digitalData.website` должен быть объявлен и заполнен в исходном коде каждой страницы сайта.

> Мы не рекомендуем заполнять объект асинхронно после загрузки страницы. Это может значительно снизить качество работы системы.

Пример заполнения:
```javascript
  window.digitalData = {
    ...,
    website: {
      region: "Москва",
      regionId: "12",
      type: "desktop",
      language: "ru",
      currency: "RUB",
      environment: "production"
    },
    ...
  }
```

### <a name="1"></a>website.region
------
`website.region` - содержит в себе название города или региона, например "Москва". Переменная объявляется и заполняется только если на сайте есть возможность выбора региона.

### <a name="2"></a>website.regionId
------
`website.regionId` - содержит в себе уникальный идентификатор региона, например "77". Переменная объявляется и заполняется только если на сайте есть возможность выбора региона.

### <a name="3"></a>website.type
------
`website.type` - содержит в себе версию отображаемго сайта:
 - "mobile" - версия для мобильных телефонов / смартфонов;
 - "tablet" - версия для планшетов;
 - "desktop" - классический сайт (доступ через стандартный компьютер);
 - "responsive" - адаптивный шаблон сайта, который подстраивается под ширину экрана без перезагрузки страницы.

>Если пользователь загружает "десктопную" версию сайта на мобильном телефоне, переменная все равно должна принимать значение "desktop".

### <a name="4"></a>website.language
------
`website.language` - содержит в себе выбранный пользователем язык. Должен быть представлен IETF-совместимой строкой, к примеру 'en-US', 'en-GB', 'ru'. EITF код начинается с ISO 639-1 представления языка и дополняется регионом.

### <a name="5"></a>website.currency
------
`website.currency` - содержит в себе валюту, выбранную пользователем в формате ISO 4217 (USD, EUR, RUB).
>Если на сайте нельзя выбрать валюту передайте в переменную `website.currency` валюту по умолчанию.

### <a name="6"></a>website.environment
------
`website.environment` содержит в себе название среды, в которой загружается сайт, например:
 - "development" - среда для разработчика,
 - "testing" - среда для тестировщика,
 - "production" - основная среда, доступная всем посетителям сайта.