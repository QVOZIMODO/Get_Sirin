# Установка на macOS

{% hint style="info" %}
**Перед началом**

* macOS 12 (Monterey) или новее
* Активная подписка Sirin — см. [Быстрый старт](../nachalo-raboty/bystryi-start.md)
* QR-код и ссылка на подписку из бота [@getsirin\_bot](https://t.me/getsirin_bot)
{% endhint %}

## Выберите приложение

Sirin выдаёт вам **все четыре протокола в одной подписке**. Ни одно приложение для macOS не понимает их все сразу, поэтому выбирайте по своим задачам — большинство начинает с AmneziaVPN.

{% tabs %}
{% tab title="AmneziaVPN (рекомендуется)" %}
Лучше всего подходит для **WireGuard + AmneziaWG** — протоколов, которые выдерживают самую жёсткую фильтрацию. Это тот QR-код, который бот показывает первым (со ссылкой `vpn://`).

{% stepper %}
{% step %}
### Установите AmneziaVPN

Скачайте `.dmg` с [amnezia.org](https://amnezia.org), откройте его и перетащите приложение в папку **Applications**.

При первом запуске macOS может спросить: _«Вы уверены, что хотите открыть приложение, скачанное из интернета?»_ — нажмите **Открыть**.

<figure><img src=".gitbook/assets/macos-amnezia-install.png" alt="Установка AmneziaVPN из .dmg"><figcaption>[РЕАЛЬНЫЙ СКРИНШОТ] Установка AmneziaVPN — перетаскивание в Applications + диалог Gatekeeper</figcaption></figure>
{% endstep %}

{% step %}
### Разрешите VPN

AmneziaVPN запросит разрешение на установку системной VPN-конфигурации. Введите пароль администратора.

<figure><img src=".gitbook/assets/macos-vpn-permission.png" alt="Запрос пароля администратора в macOS для VPN-конфигурации"><figcaption>[РЕАЛЬНЫЙ СКРИНШОТ] Запрос пароля администратора в macOS</figcaption></figure>
{% endstep %}

{% step %}
### Импортируйте ключ Sirin

Откройте [@getsirin\_bot](https://t.me/getsirin_bot) в Telegram (десктоп) и найдите запись **AmneziaVPN** (со ссылкой `vpn://`). Скопируйте ссылку, затем в AmneziaVPN выберите **+ → Вставить из буфера обмена**.

_Предпочитаете камеру? В AmneziaVPN выберите **+ → Сканировать QR** и поднесите телефон с открытым QR-кодом `vpn://` из бота к камере Mac._

<figure><img src=".gitbook/assets/macos-amnezia-import.png" alt="Импорт ключа в AmneziaVPN на macOS"><figcaption>[РЕАЛЬНЫЙ СКРИНШОТ] AmneziaVPN — вставить из буфера / сканировать QR</figcaption></figure>
{% endstep %}

{% step %}
### Подключитесь

Нажмите большую кнопку подключения. Подключение занимает 1–3 секунды. Чтобы позже попробовать другой протокол или сервер, переключитесь прямо в приложении — это делается в одно касание.

<figure><img src=".gitbook/assets/macos-amnezia-connected.png" alt="Активное подключение в AmneziaVPN на macOS"><figcaption>[РЕАЛЬНЫЙ СКРИНШОТ] Активное подключение в AmneziaVPN</figcaption></figure>
{% endstep %}
{% endstepper %}
{% endtab %}

{% tab title="Hiddify / Sing-Box (для VLESS + Shadowsocks)" %}
Лучше всего подходит для **VLESS + Reality** и **Shadowsocks** — быстрых и незаметных протоколов. Используйте **QR-код со ссылкой на подписку** (тот, что `https://sub.sirin.one/…`), а не `vpn://`. На десктопе **Hiddify и Sing-Box одинаково хороши** — выбирайте любой.

{% stepper %}
{% step %}
### Установите Hiddify или Sing-Box

Скачайте Hiddify (или Sing-Box) для macOS с официального сайта или воспользуйтесь ссылкой на [sirin.one](https://sirin.one). Откройте `.dmg` и перетащите приложение в папку **Applications**.
{% endstep %}

{% step %}
### Импортируйте подписку

В приложении выберите **Добавить профиль → из буфера обмена** и вставьте ссылку `https://sub.sirin.one/…` (или отсканируйте **QR-код подписки** из бота). Приложение подтянет VLESS + Shadowsocks и само будет обновлять список серверов.

<figure><img src=".gitbook/assets/macos-hiddify-import.png" alt="Импорт подписки в Hiddify на macOS"><figcaption>[РЕАЛЬНЫЙ СКРИНШОТ] Hiddify / Sing-Box — добавление подписки</figcaption></figure>
{% endstep %}

{% step %}
### Подключитесь

Нажмите «Подключить», подтвердите VPN-конфигурацию, когда macOS попросит, — и вы в сети.
{% endstep %}
{% endstepper %}
{% endtab %}
{% endtabs %}

## Проверьте, что всё работает

Откройте Safari и зайдите на [icanhazip.com](https://icanhazip.com). IP должен принадлежать серверу Sirin, а не вашей домашней сети.

{% hint style="success" %}
Хотите заодно убедиться, что регион выглядит правильно? Любой сайт «what's my IP» покажет страну, из которой выходит ваш трафик.
{% endhint %}

<details>

<summary>Другие клиенты (только если вы понимаете, что делаете)</summary>

* **Официальное приложение WireGuard** (Mac App Store) — только WireGuard; не умеет импортировать VLESS или Shadowsocks. Бот может выдать вам `.conf` для WG-профиля по запросу.
* **Sing-Box** — надёжная альтернатива Hiddify для VLESS + Shadowsocks на десктопе.

Это однопротокольные или инструменты для продвинутых пользователей — для полного набора Sirin на macOS оставайтесь на AmneziaVPN и/или Hiddify выше.

</details>

## Если не работает

* **macOS блокирует запуск** — Системные настройки → Конфиденциальность и безопасность → **Открыть всё равно**.
* **QR-код не сканируется** — скопируйте ссылку из Telegram Desktop и вставьте её вручную.
* **Не подключается на одном протоколе** — переключитесь на другой (в этом и весь смысл четырёх протоколов). VLESS/Shadowsocks живут в Hiddify или Sing-Box, WireGuard/AmneziaWG — в AmneziaVPN.
* **Всё равно не получается** — см. [Устранение неполадок](../podderzhka/ustranenie-nepoladok.md) или отправьте `/support` в боте.

{% content-ref url="../nachalo-raboty/bystryi-start.md" %}
[bystryi-start.md](../nachalo-raboty/bystryi-start.md)
{% endcontent-ref %}

{% content-ref url="../podderzhka/ustranenie-nepoladok.md" %}
[ustranenie-nepoladok.md](../podderzhka/ustranenie-nepoladok.md)
{% endcontent-ref %}

{% hint style="warning" %}
Пытаетесь импортировать ключ **VLESS** напрямую в **AmneziaVPN**? Сейчас это может работать нестабильно — используйте **Hiddify** (или Sing-Box) для VLESS + Shadowsocks, а AmneziaVPN оставьте для WireGuard + AmneziaWG.
{% endhint %}
