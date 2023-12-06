## Интеграция с AlfaCRM <br />

Решение позволяет передавать в наш кабинет данные по лидам/платежам в качестве сделок, для дальнейшего построения Сквозной аналитики. <br />

**Какие данные передаются** <br />

- сделки: лиды, статусы , платежи и тд ;
- 2 воронки: "Первая продажа" (лиды) и "Допродажи" (платежи после перехода лида в клиента);
- контакты;
- дополнительные поля: учитель, филиал.  <br />


## Подключение интеграции <br />

1. Нажмите "Активен" на этой странице. <br />
2. Настройте **Webhook** в AlfaCRM <br />

<details>
  <summary style="font-weight:bold;"> Подробнее </summary> <br />

ЛК AlfaCRM -> Настройки -> Автодействия и рассылки -> Триггеры и вебхуки (настраивается по каждому филиалу отдельно)  <br />

- Необходимо добавить 2 триггера по Клиенту и Платежу (Целевая сущность).
  - Выбираете все события.
  - Затронутые поля - любые.
  - Реакция - Webhook.
  - Webhook URL - берете из настроек интеграции.
  - Нажмите "Сохранить".

![image](alfa_hook.gif)

</details> 

<br />  

3. **Авторизация** в AlfaCRM <br />

<details>
  <summary style="font-weight:bold;"> Подробнее </summary> <br />

- **Название**  — укажите название авторизации.
- **hostname**  —  YOURDOMAIN замените на домен, от своего кабинета в AlfaCRM.
- **api_key**  — укажите Ключ API (v2api), из личного кабинета AlfaCRM. (Профиль -> Ключ API (v2api) , от админского ЛК)
- **email**   — укажите email, из личного кабинета AlfaCRM. (Профиль -> E-mail , от админского ЛК)

![image](alfa_auth.gif)

</details> 
<br /> 

4. Заполните настройки воронки продаж "Первая продажа": 

- **Успешный этап**  — выберете этап(ы) воронки , которые считаются завершающими успешными в AlfaCRM (в нашем сервисе они будут объединены в один этап).
- **Отказной этап**  — выберете этап(ы) воронки , которые считаются завершающими неуспешными(отказными) в AlfaCRM (в нашем сервисе они будут объединены в один этап).
<br />

5. Нажмите сохранить. <br />


После подключения интеграции сделки будут попадать в  Сырые данные -> Сделки.  <br />
Для проверки корректности работы интеграции создайте тестовый лид в AlfaCRM.