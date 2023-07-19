Описание

Этот скрипт Python предназначен для взаимодействия с определенным контрактом на сети Optimism (слое 2 Ethereum), позволяя пользователю выпустить произвольное количество NFT (токенов) в одной транзакции. Для уменьшения риска обнаружения и блокировки, скрипт использует ряд функций рандомизации, включая количество выпускаемых токенов, время ожидания между действиями и цену газа.

Использование

Клонируйте репозиторий в вашем локальном окружении.
Установите необходимые зависимости с помощью команды pip install -r requirements.txt.
Поместите свои приватные ключи в текстовый файл под названием private_keys.txt, каждый приватный ключ должен быть на новой строке в текстовом файле.
Запустите скрипт. Если файл конфигурации (config_user.json) отсутствует, скрипт запросит их у вас. Эти данные будут сохранены в config_user.json для последующего использования и могут быть измененны в любой момент.
Каждый раз при запуске скрипта он будет случайно выбирать количество монет для выпуска (в пределах заданного диапазона), а также задержку перед следующей операцией(в пределах заданного диапазона).
Если транзакция успешна, скрипт записывает адрес аккаунта и хэш транзакции в файл success.txt. Если транзакция не удалась, эти данные записываются в failure.txt.
Рандомизация

Скрипт использует следующие функции рандомизации для уменьшения риска обнаружения:
Выбор количества NFT: Количество выпускаемых NFT в каждой транзакции выбирается случайно в пределах заданного пользователем диапазона.
Задержка между действиями: После каждой транзакции скрипт ждет случайное количество времени в пределах заданного диапазона, прежде чем переходить к следующей.
Цена газа: Максимальная цена газа и максимальная приоритетная цена газа для каждой транзакции выбираются случайно в пределах заданного диапазона.
Порядок ключей: Скрипт случайным образом переставляет приватные ключи перед их использованием, таким образом меняя порядок транзакций.
Удаление ключек: Скрипт удаляет ключ после успешной транзакции во избежание повторного минта.
Примечания
Этот скрипт предназначен для образовательных целей и не должен использоваться для выполнения незаконных действий.
