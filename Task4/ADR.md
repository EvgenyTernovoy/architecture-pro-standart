### <a name="_b7urdng99y53"></a>**Название задачи:** Передача ставок в кол-центр
### <a name="_hjk0fkfyohdk"></a>**Автор:** Терновой Евгений
### <a name="_uanumrh8zrui"></a>**Дата:** 03.08.2025
### <a name="_3bfxc9a45514"></a>**Функциональные требования**

|**№**|**Действующие лица или системы**|**Use Case**|**Описание**|
| :-: | :- | :- | :- |
| UC1 | Клиент, менеджер кол-центра, система кол-центра, сервис депозитов | 1. Клиент звонит в кол-центр 2. Менеджер кол-центра открывает страницу с текущими ставками по депозитам в системе кол-центра 3. Система кол-центра делает запрос за текущими ставками в сервис депозитов 4. Менеджер видит текущие ставки и консультирует клиента |  |
| UC2 | АБС, Партнерский кол-центр | 1. Ставки по депозитам обновляются в АБС 2. АБС формирует письмо с текущими ставками и отправляет его в партнерский кол-центр  | Так в рамках MVP не можем предоставить API для получения ставок, то будем отправлять письмо |
| UC3 | Клиент, менеджер партнерского кол-центра | 1. Клиент звонит в партнерский кол-центр 2. Менеджер кол-центра открывает файл с текущими ставками по депозитам 3. Менеджер видит текущие ставки и консультирует клиента |  |
### <a name="_u8xz25hbrgql"></a>**Нефункциональные требования**

|**№**|**Требование**|
| :-: | :- |
| +R1 | Партнерский кол-центр не может использовать API банка |
### <a name="_qmphm5d6rvi3"></a>**Решение**

[Диаграмма контекста](https://www.planttext.com?text=fPFDJkCm58NtVWfFLo0DPCDgLa350WbG1MADJ6f1X6D7pes0NGlI85OiHngDfk8Dma-Xz8zNk7uZhjDMfGG14ZidEkVpFUScooa82rci64IW9CSMjbq3stYFkRl0dBkcEyCSRt68NOwt7BjqwYsutwGPk3FNO0nCmi7mVGDWObwFh0mXCfgn7v4ELLQNcLNy4219VmM15SUB1n4SPljPAcreD4WDYw69W-qe5BPkjYAPI1LKbnPgIcZOtTm8Of62jFHghshYn6ZlIFpCh2PjQlJSBg5-yWh-nHvsHeDLwBaoFn5KXLARGek3aUwVrnGX7tpSSYZCP_rh9_0PufaAQr1N0__ecWNo3eSViDdEAUMAvrQ5FXeTFVWQEqHfOv_AnnkgVa24YMNiyBDKgGLfPttDgVEpM_SeqYJM2EKXhLA83ZwLOHFKjbJZxj-qywVuO0O-2kccidAFPUMCuFsaVHmMcSZ4YyXTT-uk_UgdtokDxfT22xWd0HtmiMWsn_xuehV3bDfuTT4thYb7c5ruovTBOFhRgFKl15gfhO_Hhq6bwV-JxzaldhmzT_Krjen5fFng6LkMkau_sGi0)

[Диаграмма контейнеров](https://www.planttext.com?text=ZLJBRXf14BplLtGuOSd09QUSRDO-EFA3c3oErdXt36FFxgnc1oTM50aJEGz5YP9RRf7_02mS4uZnByp-KReNZ34iLWuWckckhgwkcPNOC6qQWNICC9B3riiAhF58nSA0fpapGeNWgj0m4N8Dlc0rpGB7CIe2es1V6QC2_5jpZr8Tvv48FTdmUKDBg1iJnKzA9SrU5sl2r1lxZPXh3z5uQ8gU2agxmcFQLzk2HroMtCU5YcIXUR6rMGfORBZ6l_PS5KGgf8g8U3eJDdjbrGXzfa_oBfFInGokgoTO5Yn3pfxRNdAQjEob_MlROFjsQ0U5v0F6rqahQTfsRWdUEd0tt3GAryV2u_y7Wrcxd7ccU1WlmrDspA0QQH7MeAoKeTFSqdIRjVsfHcjbwl73jkqLeNVnnpK2VqdE5hMggDZKDAy-snn3lvjI9B-jZ3X0JMaNTqEi1qp8GlB93f9lzWfhCaNS848XDsKM7YsKyITniPV8vXg_MmNRIIdtC-GiC--8X_uqB04kGW3RIRuY44vhkpJRQhLIt5v_ZfPqARI_i6HeBp2XcoRrY1FO6pkmxPJWR_py0Ti3EyIudpHHnnQbGNhSJzuddt6QCy21Fb9lWeDy2jUvZM-rRsDvQ-d-wlBZct7F7ZJ91Oa4AT0DWbnXc88Hxon7t2_34g3r8WaYZdJdiDgeVY-RZCkyEb6Pt5gAHwRqHJmn2K3MpbVBLQBp7IruFhT0F7IbG9zEKaYOGIeyxZ2NDfLHNMIQ7AiVSlUe9PxlQEP9VcVcaVNsrj-OFFbs9-AQ6QLJ1uosaXgdcPmYcHukd9ExSUSe5ubANXWcpJ6WiyjbriMUs-GME-8nh5OsK40fOtpS225zmPRXC5OXWYt0chdE-1ZuSUcL5WO1VMROk79ApknhMiNRCffcN96PDYFAND7iPBTxM4HhDd_6LdDbSA3nnH-vR6wmXvevpWfonIVy7m00)

1. Так как в системе уже заложена реализация сервиса депозитов, система кол-центра может вызывать его по API внутри банковской системы
2. Так как партнерский API не может вызывать банковские сервисы, мы настраивает автоматическую отправку файла со ставками депозитов при изменении ставок в АБС.
3. 
### <a name="_bjrr7veeh80c"></a>**Альтернативы**
1. Ставки в партнерский кол-центр можно было передавать вручную раз в день

**Недостатки, ограничения, риски**

- Передача ставок по депозитам по email имеет недостатки, например в партнерском кол-центре могут обновлять данные для менеджеров не своевременно. 

