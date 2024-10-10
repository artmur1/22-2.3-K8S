# Домашнее задание к занятию «Конфигурация приложений» - `Мурчин Артем`

### Цель задания

В тестовой среде Kubernetes необходимо создать конфигурацию и продемонстрировать работу приложения.

------

### Чеклист готовности к домашнему заданию

1. Установленное K8s-решение (например, MicroK8s).
2. Установленный локальный kubectl.
3. Редактор YAML-файлов с подключённым GitHub-репозиторием.

------

### Инструменты и дополнительные материалы, которые пригодятся для выполнения задания

1. [Описание](https://kubernetes.io/docs/concepts/configuration/secret/) Secret.
2. [Описание](https://kubernetes.io/docs/concepts/configuration/configmap/) ConfigMap.
3. [Описание](https://github.com/wbitt/Network-MultiTool) Multitool.

------

### Задание 1. Создать Deployment приложения и решить возникшую проблему с помощью ConfigMap. Добавить веб-страницу

1. Создать Deployment приложения, состоящего из контейнеров nginx и multitool.
2. Решить возникшую проблему с помощью ConfigMap.
3. Продемонстрировать, что pod стартовал и оба конейнера работают.
4. Сделать простую веб-страницу и подключить её к Nginx с помощью ConfigMap. Подключить Service и показать вывод curl или в браузере.
5. Предоставить манифесты, а также скриншоты или вывод необходимых команд.

### Решение 1

Создал Deployment приложения, состоящего из контейнеров nginx и multitool

https://github.com/artmur1/22-2.3-K8S/blob/main/files/deployment.yaml

![](https://github.com/artmur1/22-2.3-K8S/blob/main/img/22-2_3-01-01.png)

Создал ConfigMap - указал переменные со значениями порта и страницы:

https://github.com/artmur1/22-2.3-K8S/blob/main/files/configmap.yaml

![](https://github.com/artmur1/22-2.3-K8S/blob/main/img/22-2_3-01-02.png)

Создал Service:

https://github.com/artmur1/22-2.3-K8S/blob/main/files/svc-ngmu.yaml

![](https://github.com/artmur1/22-2.3-K8S/blob/main/img/22-2_3-01-03.png)

Под стартовал

![](https://github.com/artmur1/22-2.3-K8S/blob/main/img/22-2_3-01-04.png)

Под, Service работают. Демонстрация вывода curl:

![](https://github.com/artmur1/22-2.3-K8S/blob/main/img/22-2_3-01-05.png)

------

### Задание 2. Создать приложение с вашей веб-страницей, доступной по HTTPS 

1. Создать Deployment приложения, состоящего из Nginx.
2. Создать собственную веб-страницу и подключить её как ConfigMap к приложению.
3. Выпустить самоподписной сертификат SSL. Создать Secret для использования сертификата.
4. Создать Ingress и необходимый Service, подключить к нему SSL в вид. Продемонстировать доступ к приложению по HTTPS. 
4. Предоставить манифесты, а также скриншоты или вывод необходимых команд.

### Решение 2

Создал Deployment приложения, состоящего из контейнеров Nginx:

https://github.com/artmur1/22-2.3-K8S/blob/main/files/zadanie2/deployment2.yaml

![](https://github.com/artmur1/22-2.3-K8S/blob/main/img/22-2_3-02-1.png)

Создал ConfigMap:

https://github.com/artmur1/22-2.3-K8S/blob/main/files/zadanie2/configmap2.yaml

![](https://github.com/artmur1/22-2.3-K8S/blob/main/img/22-2_3-02-2.png)

Создал Service:

https://github.com/artmur1/22-2.3-K8S/blob/main/files/zadanie2/svc-ngmu2.yaml

![](https://github.com/artmur1/22-2.3-K8S/blob/main/img/22-2_3-02-3.png)

Создал Ingress:

https://github.com/artmur1/22-2.3-K8S/blob/main/files/zadanie2/ingress2.yaml

![](https://github.com/artmur1/22-2.3-K8S/blob/main/img/22-2_3-02-4.png)

Выпустил самоподписной сертификат SSL:

![](https://github.com/artmur1/22-2.3-K8S/blob/main/img/22-2_3-02-5.png)

Создать Secret web-tls для использования сертификата:

![](https://github.com/artmur1/22-2.3-K8S/blob/main/img/22-2_3-02-6.png)

Демонстрация доступа к приложению по HTTPS:

![](https://github.com/artmur1/22-2.3-K8S/blob/main/img/22-2_3-02-7.png)

------

### Правила приёма работы

1. Домашняя работа оформляется в своём GitHub-репозитории в файле README.md. Выполненное домашнее задание пришлите ссылкой на .md-файл в вашем репозитории.
2. Файл README.md должен содержать скриншоты вывода необходимых команд `kubectl`, а также скриншоты результатов.
3. Репозиторий должен содержать тексты манифестов или ссылки на них в файле README.md.

------
