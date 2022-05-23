Предварительно должен быть скачен и запущен Docker. Скачаны образы для докера Node.js, mysql, postgresql.
1. Выполнить в терминале команду `docker-compose up`
2. Открыть новую консоль.
Работа с MySQL
1. Запускаем приложение командой `java -jar artifacts/aqa-shop.jar`
2. После подъема приложений запускаем автотесты командой gradlew clean test allureReport
Работа с Postgre
1. В файле `application.properties` раскомментировать 4 строку 
и закомментировать 3 строку. (удалить # перед третьей строкой и 
поставить перед 3).
2. После подъема приложений запускаем автотесты командой gradlew clean test allureReport.

После прохождения тестов, в последнем терминале остановить 
работу приложения сочетанием клавиш ctrl + C.

<!--
docker-compose up
java -jar artifacts/aqa-shop.jar  -P:jdbc.url=jdbc:mysql://localhost:3306/app -P:jdbc.user=app -P:jdbc.password=pass
docker-compose exec notmysql psql -U app -d rand -W
docker-compose exec mysql mysql -u app app -p
show tables;
SELECT * FROM payment_entity;
SELECT * FROM order_entity;
SELECT * FROM credit_request_entity;

gradlew allureReport
gradlew allureServe

cd gate-simulator
docker image build -t node-app:1.0 .
docker image ls

git init
git remote add origin https://github.com/netology-git/demo.git
git add .gitignore
git add -f artifacts/app-deadline.jar
git add *
git commit -am "Initial commit"
git push --set-upstream origin master
-->