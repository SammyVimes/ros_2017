Космический корабль *spaceship.Spaceship* состоит из модулей *spaceship.Module*. Корабль может периодически получать повреждения, при этом ущерб наносится случайному его модулю. При сильном повреждении модуль начинает отправлять сообщения с просьбой о ремонте, для этого он отправляет свое имя в топик *damaged*. Корабль также обладает сервисом ремонта *repair_service*, который получает на вход строку - имя модуля для ремонта и возвращает 0, если ремонт прошел успешно, 1 - если модуль не подлежит ремонту и -1 - если такого модуля вовсе нет. При полном отказе нескольких модулей (по умолчанию 3х) корабль отключается.

Терминал *terminal.Terminal* при запуске ожидает запуска сервиса ремонта на корабле, а также подписывается на топик *damaged* и выводит оператору терминала информацию о повреждениях. Основной командой оператора является

```repair <module_name>```

которая вызывает сервис ремонта на корабле и передает ей заданное имя модуля.