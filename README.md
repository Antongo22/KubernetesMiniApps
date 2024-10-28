# <center>MiniAppsK8s</center>

<p align="center">
    <img src="https://yastatic.net/naydex/yandex-search/tLD6kU938/94f76b7wU/lMuqIAyPLbeEMXIgZdL_dW8_SV9sBLa12JSTBP_-_qN6ZYEeZ1z0LCkRb5m1wCxWb7tHhPCClywq6y0tk6vBSERvUvSMT5wzeIWjvLmyw11rShBfMAF2V" alt="Kubernetes" width="300"/>
</p>

## <center>Описание</center>
<p align="center">
    Проект развертывает приложения FastAPI для вычисления факториала и чисел Фибоначчи с пользовательским интерфейсом, используя Kubernetes и Minikube.
</p>

## <center>Стек технологий</center>
<ul>
    <li><strong>FastAPI</strong>: для создания API</li>
    <li><strong>Pydantic</strong>: для валидации данных</li>
    <li><strong>Uvicorn</strong>: ASGI сервер для FastAPI</li>
    <li><strong>Kubernetes</strong>: оркестрация контейнеров</li>
    <li><strong>Minikube</strong>: локальная разработка Kubernetes</li>
</ul>

## <center>Установка и запуск</center>

### <center>Шаги для запуска</center>
<ol>
    <li><strong>Запустите Minikube:</strong>
        <pre><code>minikube start</code></pre>
    </li>
    <li><strong>Постройте Docker-образы:</strong>
        <pre><code>docker build -t factorial_api:latest ./factorial_api</code></pre>
        <pre><code>docker build -t fibonacci_api:latest ./fibonacci_api</code></pre>
        <pre><code>docker build -t user_interface:latest ./user_interface</code></pre>
    </li>
    <li><strong>Загрузите образы в Minikube:</strong>
        <pre><code>minikube image load factorial_api:latest</code></pre>
        <pre><code>minikube image load fibonacci_api:latest</code></pre>
        <pre><code>minikube image load user_interface:latest</code></pre>
    </li>
    <li><strong>Примените конфигурацию Kubernetes:</strong>
        <pre><code>kubectl apply -f kubernetes-deployment.yaml</code></pre>
    </li>
    <li><strong>Проверьте состояние подов:</strong>
        <pre><code>kubectl get pods</code></pre>
    </li>
    <li><strong>Откройте пользовательский интерфейс:</strong>
        <pre><code>minikube service user-interface-service</code></pre>
    </li>
</ol>

## <center>Структура проекта</center>
<pre>
├── factorial_api
│   ├── app.py
│   ├── requirements.txt
│   └── Dockerfile
├── fibonacci_api
│   ├── app.py
│   ├── requirements.txt
│   └── Dockerfile
├── user_interface
│   ├── app.py
│   ├── requirements.txt
│   └── Dockerfile
└── kubernetes-deployment.yaml
</pre>

## <center>Связанное</center>
<p align="center">
    <a href="https://github.com/Antongo22/DockerMiniApps">Этот же проект на docker-compose</a>.
</p>
