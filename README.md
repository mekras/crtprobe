# crtprobe

Этот сценарий позволяет проверять настройки TLS, диагностировать ошибки и получать информацию об
удалённых узлах.

## Требования

- Командная оболочка совместимая с POSIX.
- Команда `openssl` (для некоторых действий).
- Команда `nmap` (для некоторых действий).

## Использование

### Проверка локальной системы

```
crtprobe local:check
```

Определяет возможности локальной системы и наличие необходимых пакетов.

Пример вывода:

```
Проверяю локальную систему…
- openssl: есть
  - Поддержка алгоритмов ГОСТ: есть
- nmap: есть
```

### Получение сведений об удалённом сервере

```
crtprobe remote:info <узел> [порт]
```

Выводит сведения об удалённом узле.

Пример:

```
crtprobe remote:info example.com
Проверяю локальную систему…
- openssl: есть
  - Поддержка алгоритмов ГОСТ: есть
- nmap: есть
Starting Nmap 7.92 ( https://nmap.org ) at 2024-12-19 18:55 MSK
Nmap scan report for example.com (93.184.215.14)
Host is up (0.11s latency).
Other addresses for example.com (not scanned): 2606:2800:21f:cb07:6820:80da:af6b:8b2c

PORT    STATE SERVICE
443/tcp open  https
| ssl-enum-ciphers: 
|   TLSv1.0: 
|     ciphers: 
|       TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA (secp256r1) - A
|       TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA (secp256r1) - A
|       TLS_DHE_RSA_WITH_AES_128_CBC_SHA (dh 2048) - A
|       TLS_DHE_RSA_WITH_AES_256_CBC_SHA (dh 2048) - A
|       TLS_DHE_RSA_WITH_CAMELLIA_256_CBC_SHA (dh 2048) - A
|       TLS_DHE_RSA_WITH_CAMELLIA_128_CBC_SHA (dh 2048) - A
|       TLS_RSA_WITH_AES_256_CBC_SHA (rsa 2048) - A
|       TLS_RSA_WITH_CAMELLIA_256_CBC_SHA (rsa 2048) - A
|       TLS_RSA_WITH_AES_128_CBC_SHA (rsa 2048) - A
|       TLS_RSA_WITH_CAMELLIA_128_CBC_SHA (rsa 2048) - A
|       TLS_DHE_RSA_WITH_SEED_CBC_SHA (dh 2048) - A
|       TLS_RSA_WITH_SEED_CBC_SHA (rsa 2048) - A
|     compressors: 
|       NULL
|     cipher preference: server
|   TLSv1.1: 
|     ciphers: 
|       TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA (secp256r1) - A
|       TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA (secp256r1) - A
|       TLS_DHE_RSA_WITH_AES_128_CBC_SHA (dh 2048) - A
|       TLS_DHE_RSA_WITH_AES_256_CBC_SHA (dh 2048) - A
|       TLS_DHE_RSA_WITH_CAMELLIA_256_CBC_SHA (dh 2048) - A
|       TLS_DHE_RSA_WITH_CAMELLIA_128_CBC_SHA (dh 2048) - A
|       TLS_RSA_WITH_AES_256_CBC_SHA (rsa 2048) - A
|       TLS_RSA_WITH_CAMELLIA_256_CBC_SHA (rsa 2048) - A
|       TLS_RSA_WITH_AES_128_CBC_SHA (rsa 2048) - A
|       TLS_RSA_WITH_CAMELLIA_128_CBC_SHA (rsa 2048) - A
|       TLS_DHE_RSA_WITH_SEED_CBC_SHA (dh 2048) - A
|       TLS_RSA_WITH_SEED_CBC_SHA (rsa 2048) - A
|     compressors: 
|       NULL
|     cipher preference: server
|   TLSv1.2: 
|     ciphers: 
|       TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256 (secp256r1) - A
|       TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384 (secp256r1) - A
|       TLS_DHE_RSA_WITH_AES_128_GCM_SHA256 (dh 2048) - A
|       TLS_DHE_RSA_WITH_AES_256_GCM_SHA384 (dh 2048) - A
|       TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256 (secp256r1) - A
|       TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA (secp256r1) - A
|       TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384 (secp256r1) - A
|       TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA (secp256r1) - A
|       TLS_DHE_RSA_WITH_AES_128_CBC_SHA256 (dh 2048) - A
|       TLS_DHE_RSA_WITH_AES_128_CBC_SHA (dh 2048) - A
|       TLS_DHE_RSA_WITH_AES_256_CBC_SHA256 (dh 2048) - A
|       TLS_DHE_RSA_WITH_AES_256_CBC_SHA (dh 2048) - A
|       TLS_RSA_WITH_AES_128_GCM_SHA256 (rsa 2048) - A
|       TLS_DHE_RSA_WITH_CAMELLIA_256_CBC_SHA (dh 2048) - A
|       TLS_DHE_RSA_WITH_CAMELLIA_128_CBC_SHA (dh 2048) - A
|       TLS_RSA_WITH_AES_256_CBC_SHA (rsa 2048) - A
|       TLS_RSA_WITH_CAMELLIA_256_CBC_SHA (rsa 2048) - A
|       TLS_RSA_WITH_AES_128_CBC_SHA (rsa 2048) - A
|       TLS_RSA_WITH_CAMELLIA_128_CBC_SHA (rsa 2048) - A
|       TLS_DHE_RSA_WITH_SEED_CBC_SHA (dh 2048) - A
|       TLS_RSA_WITH_SEED_CBC_SHA (rsa 2048) - A
|     compressors: 
|       NULL
|     cipher preference: server
|   TLSv1.3: 
|     ciphers: 
|       TLS_AKE_WITH_AES_256_GCM_SHA384 (secp256r1) - A
|       TLS_AKE_WITH_CHACHA20_POLY1305_SHA256 (secp256r1) - A
|       TLS_AKE_WITH_AES_128_GCM_SHA256 (secp256r1) - A
|     cipher preference: server
|_  least strength: A

Nmap done: 1 IP address (1 host up) scanned in 13.96 seconds
```

### Проверка подключения к удалённому серверу

```
crtprobe remote:test <узел> [порт]
```

Проверяет возможности по использованию TLS/SSL при работе с указанным узлом.

Пример:

```
crtprobe remote:test example.com
Проверяю локальную систему…
- openssl: есть
  - Поддержка алгоритмов ГОСТ: есть
- nmap: есть

Проверяю возможности по взаимодействию локальной системы с «example.com:443»…

TLS 1.0
━━━━━━━
Подключение успешно.

TLS 1.1
━━━━━━━
Подключение успешно.

TLS 1.2
━━━━━━━
Подключение успешно.

TLS 1.3
━━━━━━━
Подключение успешно.
```

Пример с неполной цепочкой:

```
crtprobe remote:test incomplete-chain.badssl.com
Проверяю локальную систему…
- openssl: есть
  - Поддержка алгоритмов ГОСТ: нет
- nmap: есть

Проверяю возможности по взаимодействию локальной системы с «incomplete-chain.badssl.com:443»…

TLS 1.0
━━━━━━━
Недоверенный сертификат.

Некоторые возможные причины:
• Не сервере не настроена полная цепочка сертификатов.
• Используется самоподписанный сертификат, и для работы с узлом надо установить дополнительный сертификат.

TLS 1.1
━━━━━━━
Недоверенный сертификат.

Некоторые возможные причины:
• Не сервере не настроена полная цепочка сертификатов.
• Используется самоподписанный сертификат, и для работы с узлом надо установить дополнительный сертификат.

TLS 1.2
━━━━━━━
Недоверенный сертификат.

Некоторые возможные причины:
• Не сервере не настроена полная цепочка сертификатов.
• Используется самоподписанный сертификат, и для работы с узлом надо установить дополнительный сертификат.

TLS 1.3
━━━━━━━
Сервер закрыл соединение.

Сервер немедленно закрывает соединение после его установления, что препятствует любой дальнейшей коммуникации.
Некоторые возможные причины:
• Неправильная конфигурация сервера: сертификаты TLS/SSL могут быть просрочены или неправильно настроены.
• Брандмауэр или политика безопасности могут принимать соединения, но сразу же их закрывать. Сервер может быть настроен на приём соединений только с определённых адресов IP или сетей.
• Сервер может поддерживать только определённые версии TLS/SSL или шифры, которые не совместимы с настройками клиента OpenSSL.
```