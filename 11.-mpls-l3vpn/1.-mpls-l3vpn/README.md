# MPLS L3VPN

MPLS VPN позволяет избавиться от вот этих неприятных шагов:  
1\) Настройка VRF на каждом узле между точками подключения  
2\) Настройка отдельных интерфейсов для каждого VRF на каждом узле.  
3\) Настройка отдельных процессов IGP для каждого VRF на каждом узле.  
4\) Необходимость поддержки таблицы маршрутизации для каждого VRF на каждом узле.

Да как так-то?

Рассмотрим, что такое MPLS L3VPN на примере такой сети:

![](https://img-fotki.yandex.ru/get/6831/83739833.52/0_10708a_a688eb04_orig.png)

Итак, это три филиала нашего клиента TARS' Robotics: головной офис в Москве и офисы в Новосибирске и Красноярске — весьма удалённые, чтобы дотянуть до них своё оптоволокно. А у нас туда уже есть каналы.

Центральное облако — это мы — linkmeup — провайдер, который предоставляет услугу L3VPN.

Вообще говоря, TARS Robotics как заказчику, совершенно без разницы, как мы организуем L3VPN — да пусть мы хоть на поезде возим их пакеты, лишь бы в [SLA](http://lookmeup.linkmeup.ru/#term433) укладывались. Но в рамках данной статьи, конечно, внутри нашей сети работает MPLS.