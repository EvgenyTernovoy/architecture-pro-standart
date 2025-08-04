### <a name="_b7urdng99y53"></a>**Название задачи:**  MVP открытия депозитов
### <a name="_hjk0fkfyohdk"></a>**Автор:** Терновой Евгений
### <a name="_uanumrh8zrui"></a>**Дата:** 02.08.2025
### <a name="_3bfxc9a45514"></a>**Функциональные требования**

|**№**|**Действующие лица или системы**|**Use Case**|**Описание**|
| :-: | :- | :- | :- |
| UC1 | Пользователь, сайт, система кол-центра | Подача заявки на депозит с сайта | 1. Клиент заходит на сайт и заполняет форму, указав номер телефона и ФИО 2. Заявка регистрируется в системе кол-центра |
| UC2 | Пользователь, менеджер кол-центра, система кол-центра | Обработка заявки на депозит из кол-центра | 1.Менеджер изучает заявку в системе кол-центра  2. Менеджер связывается с клиентом и может предложить особые условия |
| UC3 | Пользователь, интернет-банк | Просмотр ставок депозитов | 1. Пользователь заходит в интернет банк под своей учетной записью  2. Пользователь видит список доступных депозитов с актуальными ставками и персонализированные ставки лично для него |
| UC4 | Пользователь, интернет-банк | Подача заявки на депозит из интернет банка | 1. Пользователь заходит в интернет банк под своей учетной записью  2. Указав счёт и сумму депозита в интернет-банке, пользователь подает заявку на открытие депозита 3. Пользователь подтверждает операцию с помощью СМС-кода |
| UC5 | Пользователь, АБС, менеджер бэк-офиса | Обработка заявки на депозит из интернет банка | 1. Менеджер видит заявку в бэк-обфисе АБС  2. Менеджер подтверждает условия депозита в АБС 3. Клиент получает СМС-уведомление о подтверждении ставки и открытии депозита |
| UC5 | Пользователь, АБС, менеджер бэк-офиса | Обработка заявки на депозит из интернет банка | 1. Менеджер видит заявку в бэк-обфисе АБС  2. Менеджер подтверждает условия депозита в АБС 3. Клиент получает СМС-уведомление о подтверждении ставки и открытии депозита |
### <a name="_u8xz25hbrgql"></a>**Нефункциональные требования**
Опишите здесь нефункциональные требования и архитектурно значимые требования.

|**№**|**Требование**|
| :-: | :- |
| +R1 | Фронтенд интернет банка (депозиты) на React.js, бэкэнд - на Java Spring Boot |
| +R2 | Фронтенд сайта на React.js, бэкэнд - на PHP Laravel |
| +R3 | Функциональность ведения ставок по депозитам должна быть реализована в АБС |
| +R4 | В интернет-банке данные при передаче надо защитить каким-то механизмом шифрования |
| P1 | Предусмотреть равномерное горизонтальное масштабирование и распределение запросов между серверами, приложениями и ЦОД, АБС может масштабироваться только вертикально из-за своей базы данных  |
| P2 | Избежать прямой работы интернет-банка с API АБС  |
| P3 | Отклик по всем операциям должен быть максимально быстрым и занимать миллисекунды  |
| R1 | Сервисы должны работать 24/7 и быть доступны в 99,9% случаев  |

### <a name="_qmphm5d6rvi3"></a>**Решение**
[Диаграммы контекста](https://www.planttext.com?text=jLNBJjj05DtdAwPPWTIGJLTT0MaNIAMAe7IBZ3C22yUEd8dQxfBGXofeQLT5LLMQVe492J4Xc5-uyqSzT-m470WIYouisPvx7lVXwyMwiWBLgBevvIXNYjNNPV5CrloweuGTI4ivlfVBARycb2-sVANyggWuWRIJWqUEPxkDYcm4hjXHgbP_MYm6rfk5RKVjDBOQTHdOlgUafnPilrfSSsmhgFWl7LcJRh7qf51sBKzjhBueLgswaW5URPRyQitt655ZLxco3Eg-DxS1giSYJp_fWYBgqwLkv_6Sdny7b2pNNRKyQpk9-yKnk7fqHdtT53Iac2uA-cE2rKqAi_Xbozwz3t-Ylz2mGB5-Jv5kJT3hxs2yEhVkACcm3eLqhji8nyqbHAVYLb2Cm9DgsV9sEVw8pR00Y-bsOOpBefQMrpdu6tsdJlQ4iov99arU91vWa5bfHE4zYUTIaitdRzNSA-dANT_W_oBo0XS3HyYOhep149InRex1Qz9DcpBE_GUiNx4OT0uv6q43e0wfIqEz9v0MtFH0p443c6o3XsaIWbkfvEaFWa_1r3A-8ztKUxTuKuvC---WEgA1tjEVOF41nZAa9bckRXV8WTu7sf31tQ5Wg30rH-Km8Z5g0EO81t3EOyHrEKtbuQI5nnWK4OCpskZF_8tgPYR655b_G6YFGuqizGJOkhZfqxamIK83ISLuv4GHn0DneByQGz1CqMPAGgw2COeCfftGAFMIdLkUnpmTSqutYngYd6sqACJh0nHWd_ftQ2oLL-vByDWaDxDDCUZmLM4Kzd67JJ2hUfE1JljcU77UDSDyDgqnOn3InhPef5ifSMPHN5VYuTp_YU-kn3Djwc2vTGheKpSTp97vt2-JQiRfK6NaazDegfjHsev9Cw9PpJ0BR6miJxznnDy5Cx6qiHKR76j-ldOpl5xtF8qSTG9Xq8_I1PqOcqnAZDs9xRGelGf-7_y0)

[Диаграмма контейнеров](https://www.planttext.com?text=dLPBRzD04BxxLmmzfLBJN3XneabHUJGbr3oErTRPfaisNckzALG82O9u2V6wSK12vHUaLKD3qfQ_iFv7pDXEwoHEGOtaP1ypttupy-qurqF3j6ctf6E4aHog3skmp0CL2WEUvim8vKD5-OO9dske2zRGhEKuHWLW56mgOrGBbpNtoDHnhWZVa-qwRsi9syO4uRLIIRCdYmrXjjkRxP1h3z6uRnOzrIgj2u_fkbeJFE2oLBbQh4dccmVLrLABXOPhNDgeg5QWVF88Y2T-plWKN67u0ipPFTkrlwCEs7qSdDY1xSxXyZfddbby72v0xMODLfbcErpIXlrXJ-sXxKPlRHVi4Gu-smDS6W0wuygXxTa_E3-o_QWpDvyvi285Chc54MYVcpBpcmJtpPv47TkBNg1xB-eKHpG0KNjs7v3GqFPnY6PPOWZj06JWbmAnmWn_mdRH2YUGpiZfZl8RzBl2qP99G1vw5m8bV3CtdqNPAAksNsTwjr1XKbOuaNLtCPsj95Nzw2MnjSSKwW3371QZDmavZA2BOC-GLIRcSnIkTuJ7_mzch02tsGu3Dz32Rq1PAKEx67tccENDp47BPJhZAsRnAAa7fVCa-X2zddLKJOMceRbxRpM5VawPpQIsoiEGDVYzDczJ0EaKudcSNhRLPAdlkTUQCc8BHKhY7el-kzqhHk_iCFfaZo3Emn0VudPSnAy_iHgwk76Qv3Ghs_C2POKqiqIpr9LJgZBpcjol_xy-zwEF28IPj8SK-v9RMroxSH_RG2Mv9-Xo6eluC3OY3Hy3HZUCO-lPN_Zy1ji7ZBDZ1z4Bh567p9AS3A9NqNkCvZLWG6_fR8A3GWotFvgFwjf5zyxyk2mAQJSQIpv5Sa19chYg14QyyzGsxeOkG8L14aGSwKvXTJ7x_Nmo5UPj4vMpJadpHF1r4MO5c5FpfR9BTBwWlFUc2eYRIOivCvbg7ijS1jiYzmAXzqKt9paIz-zgvab-njD9fBTnuwaftEUIDrKimvyNYZhrTjQvJDlmMFEgiYOFOQbs2vCZPOWl2tA8tmWBy3XKFlgIQrv3lHHGrYclOrq69_ywNGPfIiK9o4X05uF5Q9C84_qCMsqzB3tIM8aGwfDlSBw3sGXJNfD88zMCGp33PjXFN88fDzZI-9yWkHDfaQVhCT7hPvsTkG__efanpU_QBfOItAgRskSQdSi_O-rSnp7-z_WB)

Также опишите, какой логикой вы руководствовались в ходе принятия решений и выбора технологий. Не забывайте, что необходимо учесть все функциональные и нефункциональные требования.

- **Требование +R1** В качестве технологий для реализации сервиса депозитов выбираем Java Spring Boot + React.js для интерфейсов.
- **Требование +R2** Для реализации функциональности подачи заявок на депозиты с сайта используем текущий стек PHP Laravel + React.js
- **Требование +R3** В АБС добавляем функциональность ведения ставок по депозитам и храним данные о ставках в базе данных АБС
- **Требование +R4** Для передачи данных между интернет банком и другими системами используем https протокол
- **Требование +R5** Используем современные практики девопс, для горизонтального масштабирования сервисов. Для этого используем Kubernetes кластеры. Учитываем, что база данных АБC масштабируется только вертикально. Возможно, задача по модернизации системы потребует отдельного архитектурного решения с определением требований
- **Требование P1** Используем современные практики девопс, для горизонтального масштабирования сервисов. Для этого используем Kubernetes кластеры. Учитываем, что база данных АБC масштабируется только вертикально.
- **Требование P2** Что бы избежать прямых запросов к базе данных АБС, и снизить нагрузку принято внедрить брокер сообщения Kafka для хранения очереди сообщения на создания депозитов, что позволит боле гибко управлять нагрузкой на бд со стороны интернет банка. 
- **Требование P3** Для более быстрого отклика и отдачи справочной информации по депозитам был добавлен слой кэширования. Так же за счет внедрения брокера сообщений, скорость отклика на запросы создания заявок на депозиты будет высокой.
- **Требование R1** Благодаря внедрению новых девопс практик мы сможем поддерживать работу 24/7 и доступность в 99,9% случаев

### <a name="_bjrr7veeh80c"></a>**Альтернативы**
1. Не добавлять новый сервис для депозитов и обрабатывать заявки в существующем сервисе

**Недостатки, ограничения, риски**
1. Внедрение новых технологий требует специалистов с определенными навыками. 
2. Большую часть платформы надо разрабатывать на целевом стеке Java — могут быть проблемы с загрузкой команды, можно было бы больше функций выделить в микросервисы на PHP

