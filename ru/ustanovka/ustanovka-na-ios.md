# Установка на iOS (iPhone, iPad)

{% hint style="info" %}
**Перед началом**

* iOS 14 или новее
* Активная подписка Sirin — см. [Быстрый старт](../nachalo-raboty/bystryi-start.md)
* QR-код и ссылка на подписку из бота [@getsirin\_bot](https://t.me/getsirin_bot)
{% endhint %}

## Выберите приложение

Sirin выдаёт вам **все четыре протокола в одной подписке**. Ни одно приложение для iOS не понимает их все сразу, поэтому выбирайте по своим задачам — большинство начинает с AmneziaVPN.

{% tabs %}
{% tab title="AmneziaVPN (рекомендуется)" %}
Лучше всего подходит для **WireGuard + AmneziaWG** — протоколов, которые выдерживают самую жёсткую фильтрацию. Это тот QR-код, который бот показывает первым (со ссылкой `vpn://`).

{% stepper %}
{% step %}
### Установите AmneziaVPN

Из App Store: [apps.apple.com/app/amneziavpn](https://apps.apple.com/app/amneziavpn/id1600529900)

<figure><img src=".gitbook/assets/ios-amnezia-appstore.png" alt="AmneziaVPN в App Store"><figcaption>[РЕАЛЬНЫЙ СКРИНШОТ] Страница AmneziaVPN в App Store</figcaption></figure>
{% endstep %}

{% step %}
### Разрешите VPN

При первом запуске iOS попросит разрешение на добавление VPN-конфигурации. Нажмите **Разрешить**.

<figure><img src=".gitbook/assets/ios-vpn-permission.png" alt="Диалог iOS с запросом разрешения на VPN"><figcaption>[РЕАЛЬНЫЙ СКРИНШОТ] Диалог iOS с запросом разрешения на VPN</figcaption></figure>
{% endstep %}

{% step %}
### Импортируйте ключ Sirin

В боте [@getsirin\_bot](https://t.me/getsirin_bot) откройте сообщение с доставкой и найдите **QR-код AmneziaVPN** (код со ссылкой `vpn://`). В AmneziaVPN нажмите **+ → Сканировать QR** и наведите камеру на код.

_Нет камеры? Зажмите ссылку `vpn://` в Telegram, чтобы скопировать её, а затем в AmneziaVPN выберите **Вставить из буфера обмена**._

<figure><img src=".gitbook/assets/ios-amnezia-import.png" alt="Импорт ключа в AmneziaVPN"><figcaption>[РЕАЛЬНЫЙ СКРИНШОТ] AmneziaVPN — добавить + сканировать QR</figcaption></figure>
{% endstep %}

{% step %}
### Подключитесь

Нажмите большую кнопку в центре. Подключение занимает 1–3 секунды. Чтобы позже попробовать другой протокол или сервер, снова откройте приложение и переключитесь — это делается в одно касание.

<figure><img src=".gitbook/assets/ios-amnezia-connected.png" alt="Активное подключение в AmneziaVPN"><figcaption>[РЕАЛЬНЫЙ СКРИНШОТ] Активное подключение в AmneziaVPN</figcaption></figure>
{% endstep %}
{% endstepper %}
{% endtab %}

{% tab title="Hiddify (для VLESS + Shadowsocks)" %}
Лучше всего подходит для **VLESS + Reality** и **Shadowsocks** — быстрых и незаметных протоколов. Используйте **QR-код со ссылкой на подписку** (тот, что `https://sub.sirin.one/…`), а не `vpn://`.

{% stepper %}
{% step %}
### Установите Hiddify

Из App Store: найдите **Hiddify** или воспользуйтесь ссылкой на [sirin.one](https://sirin.one).
{% endstep %}

{% step %}
### Импортируйте подписку

В Hiddify нажмите **+ → Добавить из QR-кода** и отсканируйте **QR-код подписки** из бота (или вставьте ссылку `https://sub.sirin.one/…`). Hiddify подтянет VLESS + Shadowsocks и сам будет обновлять список серверов.

<figure><img src=".gitbook/assets/ios-hiddify-import.png" alt="Импорт подписки в Hiddify"><figcaption>[РЕАЛЬНЫЙ СКРИНШОТ] Hiddify — добавить из QR / по ссылке на подписку</figcaption></figure>
{% endstep %}

{% step %}
### Подключитесь

Нажмите «Подключить», разрешите VPN-конфигурацию, когда iOS попросит, — и вы в сети.
{% endstep %}
{% endstepper %}

{% hint style="info" %}
**Sing-Box на iOS** тоже работает с VLESS + Shadowsocks, но сборка в App Store отстаёт от Android-версии — если какой-то совсем новой функции нет, причина в этом. На iPhone Hiddify работает плавнее и подходит по умолчанию.
{% endhint %}
{% endtab %}
{% endtabs %}

## Проверьте, что всё работает

Откройте Safari и зайдите на [icanhazip.com](https://icanhazip.com). IP должен принадлежать серверу Sirin, а не вашему домашнему или мобильному провайдеру.

{% hint style="success" %}
Хотите заодно убедиться, что регион выглядит правильно? Любой сайт «what's my IP» покажет страну, из которой выходит ваш трафик.
{% endhint %}

<details>

<summary>Другие клиенты (только если вы понимаете, что делаете)</summary>

* **Официальное приложение WireGuard** — только WireGuard; не умеет импортировать VLESS или Shadowsocks. Годится как запасной вариант для WG-профиля.
* **Shadowrocket** (платное) — хорошая поддержка VLESS + Shadowsocks, если оно у вас уже есть.

Это однопротокольные или инструменты для продвинутых пользователей — для полного набора Sirin на iOS оставайтесь на AmneziaVPN и/или Hiddify выше.

</details>

## Если не работает

* **Приложение не запускается** — удалите и переустановите из App Store.
* **QR-код не сканируется** — скопируйте ссылку из Telegram и вставьте её вручную.
* **Не подключается на одном протоколе** — переключитесь на другой (в этом и весь смысл четырёх протоколов). VLESS/Shadowsocks живут в Hiddify, WireGuard/AmneziaWG — в AmneziaVPN.
* **Всё равно не получается** — см. [Устранение неполадок](../podderzhka/ustranenie-nepoladok.md) или отправьте `/support` в боте.

{% content-ref url="../nachalo-raboty/bystryi-start.md" %}
[bystryi-start.md](../nachalo-raboty/bystryi-start.md)
{% endcontent-ref %}

{% content-ref url="../podderzhka/ustranenie-nepoladok.md" %}
[ustranenie-nepoladok.md](../podderzhka/ustranenie-nepoladok.md)
{% endcontent-ref %}

{% hint style="warning" %}
Пытаетесь импортировать ключ **VLESS** напрямую в **AmneziaVPN**? Сейчас это может работать нестабильно — используйте **Hiddify** для VLESS + Shadowsocks, а AmneziaVPN оставьте для WireGuard + AmneziaWG.
{% endhint %}
