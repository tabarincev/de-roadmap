<table border="1" cellspacing="0" cellpadding="6">
  <thead>
  </thead>
  <tbody>
    <tr>
      <td>Слой</td>
      <td colspan="2">Staging</td>
      <td>Core</td>
      <td colspan="2">Presentation</td>
    </tr>
    <tr>
      <td>Медальон</td>
      <td colspan="2">Bronze</td>
      <td>Silver</td>
      <td>Gold</td>
      <td>Platinum</td>
    </tr>
    <tr>
      <td>Подслой</td>
      <td>Raw</td>
      <td>ODS</td>
      <td>DDS</td>
      <td>Data Mart</td>
      <td>Report</td>
    </tr>
    <tr>
      <td>Описание</td>
      <td>
        - Зона загрузки сырых данных различных форматов (tsv, csv, xml, json и т.д.) из внешних источников As-Is<br>
        - Действует CDC (Change Data Capture)
      </td>
      <td>
        - Данные приведены в единый формат (стандартизованы) и загружены в общий слой хранилища<br>
        - Загрузка данных NRT<br>
        - Начальная очистка данных и применение DQ
      </td>
      <td>
        - Создается модель данных<br>
        - Трансформация данных<br>
        - Добавление мета-данных<br>
        - Финальная очистка данных<br>
        - Поддержка историчности (SCD2)<br>
        - Интеграция с мастер-данными<br>
        - Оптимизация под запись
      </td>
      <td>
        - Создается модель данных<br>
        - Готовый “дата-продукт” для бизнеса<br>
        - Применена бизнес-логика в трансформации данных<br>
        - Данные семантически сгруппированы<br>
        - Действует BI self-service<br>
        - Оптимизация под чтение
      </td>
      <td>
        - Готовый отчет/визуализация<br>
        - Данные агрегированы и объединены в один data set для целостного представления
      </td>
    </tr>
    <tr>
      <td>Владельцы / пользователи</td>
      <td>Data Engineers</td>
      <td>Data Engineers, Data Scientists</td>
      <td>Operational Analysts, Data Scientists</td>
      <td>BI Analysts, Managers, Data Scientists</td>
      <td>Executives, Top Management</td>
    </tr>
    <tr>
      <td>Модель данных</td>
      <td>As-Is</td>
      <td>As-Is / Raw Data Vault</td>
      <td>Data Vault / Business Data Vault / 3NF</td>
      <td>Dimensional Modelling (Kimball’s approach)</td>
      <td>One big table</td>
    </tr>
  </tbody>
</table>
