# Организация защищенного доступа к контенту в Yandex Cloud CDN

Создайте веб-сайт, который будет генерировать подписанные ссылки с [защищенным токеном](https://yandex.cloud/ru/docs/cdn/concepts/secure-tokens) на контент, распространяемый через [Cloud CDN](https://yandex.cloud/ru/docs/cdn/). Доступ к контенту по такой ссылке будет разрешен только в течение пяти минут с момента получения ссылки и только тому пользователю, для которого ссылка была сгенерирована.

Веб-сайт будет развернут на [виртуальной машине](https://yandex.cloud/ru/docs/compute/concepts/vm), созданной из публичного образа [LAMP](https://yandex.cloud/ru/marketplace/products/yc/lamp) с предустановленным веб-сервером [Apache HTTP Server](https://httpd.apache.org/). Сайт будет доступен по доменному имени, делегированному в [Yandex Cloud DNS](https://yandex.cloud/ru/docs/dns/), для которого в [Yandex Certificate Manager](https://yandex.cloud/ru/docs/certificate-manager/) будет выпущен TLS-сертификат.

Настройка описана в [практическом руководстве](https://yandex.cloud/ru/docs/cdn/tutorials/protected-access-to-content). В репозитории хранятся конфигурационные файлы для развертывания инфраструктуры с помощью Terraform:
* `yc-cdn-secure-token.tf` — манифест Terraform для создания облачной инфраструктуры.
* `yc-cdn-secure-token.tfvars` — файл c пользовательскими данными.
