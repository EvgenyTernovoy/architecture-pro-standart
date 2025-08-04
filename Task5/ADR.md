### <a name="_b7urdng99y53"></a>**Название задачи:** Заявка на кредит онлайн
### <a name="_hjk0fkfyohdk"></a>**Автор:** Терновой Евгений
### <a name="_uanumrh8zrui"></a>**Дата:** 04.08.2025
### <a name="_3bfxc9a45514"></a>**Функциональные требования**

|**№**|**Действующие лица или системы**|**Use Case**|**Описание**|
| :-: | :- | :- | :- |
| UC1 | Клиент, сервис кредитов, смс-шина, АБС | Подача заявки на кредит с сайта | 1. Клиент заходит на сайт и заполняет форму, указав номер телефона, ФИО, паспортные данные 2. Заявка по API передается в сервис кредитов 3. Сервис кредитов регистрирует заявку в бд АБС и параллельно делает запрос в бюро кредитных историй 4. После принятия решения сервис кредитов обновляет данные заявки и отправляет смс клиенту |
| UC2 | Клиент, интернет-банк | Клиент видит условия кредитования и предодобренные предложения по кредиту | 1. Клиент заходит в интернет банк и видит условия кредитования и предодобренные предложения по кредиту |
| UC3 | Клиент, интернет-банк, сервис кредитов | Повторная подача заявки на кредит | 1. Клиент заходит в интернет-банк, у него есть предоодбренны предложения 2. Клиент подает новую заявку указав сумму и счет зачисления 3. Клиент подтверждает подачу заявки по смс 4. Заявка обрабатывается в течении одного дня|
### <a name="_u8xz25hbrgql"></a>**Нефункциональные требования**
Опишите здесь нефункциональные требования и архитектурно значимые требования.

|**№**|**Требование**|
| :-: | :- |
| +R1 | Ускорить обмен между базами АБС и Кредитного конвейера и проводить его чаще невозможно |
| +R2 | Кредитный конвейер и система кредитного скоринга разработаны с учётом возможного роста нагрузки и поддерживают горизонтальное масштабирование с работой 24/7 |
| +R2 | Система кредитного скоринга не нужно нагружать дополнительными процессами по предрасчетам кредитов |
### <a name="_qmphm5d6rvi3"></a>**Решение**
[Диаграмма контекста](https://www.planttext.com?text=XLJBRjD05DtxAuQiWaIQ3IjMVGY9Ie2YXguhDnbHgxR7SYP0Tssg2YIgbgwA4A8AN-16DSsZINxXpXznvjf9wv2AHH8_xZdtt7FkPBMbtLYt0z_HdlQbs8XbqzF2ZIBVQxZQKw7ZQ1K9hSIkqbe5ekd5if6zUEA53R_TbEtO5tjQHwqNrMhiVbnvx-czzcwx9UE62hKCzKf31TKj4CPDzTQJaVIh6yyhDTyDzVQRrzN0RMaPuz7EXWeY5Lf4P3KvDHctL5ZU1jKpKQ8VDA8-fJGsdHBkIq-T-W6WGRdkQMaBkfJGm7G4NUDYJ4DAYdMRa1E7Kg-xuRwj_swfA3M7A4vDfpB35L5hwtLR_8qkg5jyazbLb_47hv4Bi6GzwfiZGKDSfdI3cmvDg9T3S-pEoq-w_4xwSby55laRfIDyXYYzg-1hobI9nPh3Gbk6PgrVUIsjuWDBS67EK3yfjXsRh-P4M3aP3-mRp7HiIJztTcRV9QQVelK8k7DhYA1RA3Z7G4DpBE1CKg07YoN9u4KlIlGB7QTs0g17I-dGAjkRd6V1pUA4kJgsv0l6wE6EAMyuCWnAgU3nxvU4qkNCDb08HDfZ6yozl4MkkLpydYpdcaNuoC1T-adTYZd6CsiQikMKnrOYMj0rma6REtwMFUyBJWl9csDpP2sVoPXWCn7SW-GA2yqMcHEKSJfiCDs0ZQ4f3GG8FrjTFFU0YL5aj-FKd469iAkRexdvYFtfc_D_jfcTmelP9XMFrk8oNDcjukvvQWduC1z-H-OqTtonezsFjTfcxllIWQzusEInNPtEsyujVpX6abFFZo7tMABsFodcJeEnnuVs3sgAMV8EzTdX2UuX0WUpmmLSQ_6tSqsEioh39lu1_m80)

[Диаграмма контейнеров](https://www.planttext.com?text=dLRBRjj65DtpAswriW7RsdJLLIJPo5EkQkQnDCRaM9w8uX33aLAXAD0e298WoCEx80WGE5yWkrOjFwJyml2FUk-GiaXPDjfu8SuCvvmvzznxXxuLQwPqfnquMkY0GqrnNsYeH54WFAQ53A4cGyr4o1NuWZKLQpkEbX5e2JjIQzd6PSKzskeuFudG2pe-xwW0zhIEub_APSMUhJM5tkliT6AkF6JZeLxpPBkyXKSeNsuA7l6WNFjvjH6mK3-gFoYtMQovmgNjccn7CYH4H2hnxrBFaYiqNu6IEJ03SvhqmHpYO6pEpA24orkSUNhjQRm2ZJiDUC0Kw_A0NfYlPcAEpI1vPGPWJd3mmHpXqXaW65VEah_C43UCadvfENTSBH2euoxgLo7NLHQsYEoJ6ITzCqJC67_xgrCHW9n3SuXqvjoCS8ZRyhAGsW78qLSYSPjf_eprS1TE89iHwBuCc_IypN4d2m1rg1v4KeIwj8mi1Q8wZsFMvBzrU8VioQPWvvQCxROO3GhHRKejThESkrnrXPTv-yKSh2QlpNdotfm0XOhn336gYRbOnP_lDlO1lfZGi-YOhIQSTtbFAgBxFFCM3NbhJi4oZQrPfqG51GRNaqg4JRU7zT1EzI0qUMvrN62sakT4WAmZcu6_hO9SaMnNPIVqcUejvHDNv9knNPjDeeK_qEUPj2hpMZpq_tiz72Rla0WBmHoJ-nMtiRQvyH3gZsjfLI9aOdqujfkePYu0_JstxWxDFsGHc15Wl7sgqkGjFd5RcfMpv4No1gDvYPvWQGyf8-O8bYpTuNIEc9Va-G3X_MNqAXzIcgz2zYcG8_Aeq1V4HABliIu3Dw8KGLLANRe2-cucG7M12aWrQfrZ6g3neuKwQipR8nNPdUJHDEqWNyHP_VvPAFrPiYjLbwHyDFlcu4hcy6NQovTRhdJfEW-YFP4TaiEkxn1wlKh8VTH-GaLpR3CyJgrDZyJtlohc1VnIfvFMtFR6xthf8GzuIzhw-tPZFsNe73Gruuw8jLGzgo9vJuLJD3NJafQsxGvpcd4vMpp8Rix2ZLDdBHv3fN4NZGw26Ezt0jXBV0MUnZ94B44NtO8_H9G7BUwb7s6QB-6KO_fPkv4g3Q-8dxSRRsy_1izw05xAwZFDfkOKqNCtiGMNdoWqFvw2MUvBoxl86Y-ccbPTWUFwauiTT0K4kme_t6b7tOIVtTmBSh4GE7zXNulBDU7_Z6tnbyh5-W6txcQOXPjcVPVRxTp2CVvlyIy0)

- **Требование +R1** Делаем запросы повторных заявок из Сервиса кредитов напрямую в Кредитный конвейер.
- **Требование +R1** При необходимости можем масштабировать сервисы.
- **Требование +R1** Предрасчеты производятся вне рабочее время автоматически, что снижает нагрузку на сервис скоринга.
### <a name="_bjrr7veeh80c"></a>**Альтернативы**

1. Для сервиса кредитов можно было бы завести отдельную базу данных что бы снизить нагрузку на базу данных АБС, но тогда это задело бы часть фукнциональности АБС, что замедлило бы разработку.  

**Недостатки, ограничения, риски**

1. Сейчас отправка смс-сообщений происходит как из АБС так и из сервиса кредитов. В будущем нужно сделать единый механизм оповещения при смене статуса заявок

