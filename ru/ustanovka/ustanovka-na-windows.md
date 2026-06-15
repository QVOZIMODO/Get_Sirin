# Установка на Windows

{% hint style="info" %}
**Перед началом**

* Windows 10 или 11
* Права администратора для первой установки (чтобы добавить VPN-драйверы)
* Активная подписка Sirin — см. [Быстрый старт](../nachalo-raboty/bystryi-start.md)
* QR-код и ссылка на подписку из бота [@getsirin\_bot](https://t.me/getsirin_bot)
{% endhint %}

## Выберите приложение

Sirin выдаёт вам **все четыре протокола в одной подписке**. Ни одно приложение для Windows не понимает их все сразу, поэтому выбирайте по своим задачам — большинство начинает с AmneziaVPN.

{% tabs %}
{% tab title="AmneziaVPN (рекомендуется)" %}
Лучше всего подходит для **WireGuard + AmneziaWG** — протоколов, которые выдерживают самую жёсткую фильтрацию. Это тот QR-код, который бот показывает первым (со ссылкой `vpn://`).

{% stepper %}
{% step %}
### Установите AmneziaVPN

Скачайте установщик `.exe` с [amnezia.org](https://amnezia.org). Windows SmartScreen может предупредить _«Система Windows защитила ваш компьютер»_ — нажмите **Подробнее → Выполнить в любом случае**. Установщик запросит права администратора; разрешите и следуйте шагам мастера.

<figure><img src=".gitbook/assets/windows-amnezia-install.png" alt="Установщик AmneziaVPN с предупреждением SmartScreen"><figcaption>[РЕАЛЬНЫЙ СКРИНШОТ] Установщик AmneziaVPN + SmartScreen «Выполнить в любом случае»</figcaption></figure>
{% endstep %}

{% step %}
### Разрешите установку VPN-драйверов

При первом запуске Windows попросит разрешение на установку драйверов WireGuard/TAP. Нажмите **Разрешить**.

<figure><img src=".gitbook/assets/windows-vpn-driver.png" alt="Диалог установки VPN-драйвера в Windows"><figcaption>[РЕАЛЬНЫЙ СКРИНШОТ] Диалог установки драйвера в Windows</figcaption></figure>
{% endstep %}

{% step %}
### Импортируйте ключ Sirin

Откройте [@getsirin\_bot](https://t.me/getsirin_bot) в Telegram Desktop и найдите запись **AmneziaVPN** (со ссылкой `vpn://`). Скопируйте ссылку, затем в AmneziaVPN выберите **+ → Вставить из буфера обмена**.

_Предпочитаете камеру? Выберите **+ → Сканировать QR** и поднесите телефон с открытым QR-кодом `vpn://` из бота к веб-камере._

<figure><img src=".gitbook/assets/windows-amnezia-import.png" alt="Импорт ключа в AmneziaVPN на Windows"><figcaption>[РЕАЛЬНЫЙ СКРИНШОТ] AmneziaVPN — вставить из буфера / сканировать QR</figcaption></figure>
{% endstep %}

{% step %}
### Подключитесь

Нажмите большую кнопку подключения. Подключение занимает 1–3 секунды. Чтобы позже попробовать другой протокол или сервер, переключитесь прямо в приложении — это делается в одно касание.

<figure><img src=".gitbook/assets/windows-amnezia-connected.png" alt="Активное подключение в AmneziaVPN на Windows"><figcaption>[РЕАЛЬНЫЙ СКРИНШОТ] Активное подключение в AmneziaVPN</figcaption></figure>
{% endstep %}
{% endstepper %}
{% endtab %}

{% tab title="Hiddify / Sing-Box (для VLESS + Shadowsocks)" %}
Лучше всего подходит для **VLESS + Reality** и **Shadowsocks** — быстрых и незаметных протоколов. Используйте **QR-код со ссылкой на подписку** (тот, что `https://sub.sirin.one/…`), а не `vpn://`. На десктопе **Hiddify и Sing-Box одинаково хороши** — выбирайте любой.

{% stepper %}
{% step %}
### Установите Hiddify или Sing-Box

Скачайте Hiddify (или Sing-Box) для Windows с официального сайта или воспользуйтесь ссылкой на [sirin.one](https://sirin.one). Запустите установщик.
{% endstep %}

{% step %}
### Импортируйте подписку

В приложении выберите **Добавить профиль → из буфера обмена** и вставьте ссылку `https://sub.sirin.one/…` (или отсканируйте **QR-код подписки** из бота). Приложение подтянет VLESS + Shadowsocks и само будет обновлять список серверов.

<figure><img src=".gitbook/assets/windows-hiddify-import.png" alt="Импорт подписки в Hiddify на Windows"><figcaption>[РЕАЛЬНЫЙ СКРИНШОТ] Hiddify / Sing-Box — добавление подписки</figcaption></figure>
{% endstep %}

{% step %}
### Подключитесь

Нажмите «Подключить», подтвердите VPN-конфигурацию, когда Windows попросит, — и вы в сети.
{% endstep %}
{% endstepper %}
{% endtab %}
{% endtabs %}

## Проверьте, что всё работает

Откройте браузер и зайдите на [icanhazip.com](https://icanhazip.com). IP должен принадлежать серверу Sirin, а не вашей домашней сети.

{% hint style="success" %}
Хотите заодно убедиться, что регион выглядит правильно? Любой сайт «what's my IP» покажет страну, из которой выходит ваш трафик.
{% endhint %}

<details>

<summary>Другие клиенты (только если вы понимаете, что делаете)</summary>

* **Официальный WireGuard для Windows** — только WireGuard; не умеет импортировать VLESS или Shadowsocks. Бот может выдать вам `.conf` для WG-профиля по запросу.
* **v2rayN** ([GitHub](https://github.com/2dust/v2rayN)) — VLESS + Reality и Shadowsocks для продвинутых пользователей.

Это однопротокольные или инструменты для продвинутых пользователей — для полного набора Sirin на Windows оставайтесь на AmneziaVPN и/или Hiddify выше.

</details>

## Если не работает

* **SmartScreen блокирует установщик** — нажмите **Подробнее → Выполнить в любом случае**.
* **Драйверы не устанавливаются** — запустите AmneziaVPN от имени администратора.
* **Подключено, но интернета нет** — проверьте, что антивирус/брандмауэр не блокирует AmneziaVPN, затем попробуйте сменить протокол или сервер.
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
