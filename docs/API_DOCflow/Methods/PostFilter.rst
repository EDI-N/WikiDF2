#############################################################
**Створення / редагування ярлика фільтра**
#############################################################

Для роботи з цим методом користувач повинен бути `авторизованим <https://wiki-df-bank.edin.ua/uk/latest/API_DOCflow/Methods/Authorization.html>`__ .

.. important:: 
    Вибір дії (створення або редагування). В разі якщо в тілі запиту (json) присутній **filterId**, то запис з зазначеним **filterId** підлягає редагуванню.

+----------------------------------------------------------------+--------------------------------------------------------------------------------------------------------+
|                        **Метод запиту**                        |                                            **HTTPS POST**                                              |
+================================================================+========================================================================================================+
| **Content-Type**                                               | application/json (тіло запиту/відповіді в json форматі в тілі HTTPS запиту)                            |
+----------------------------------------------------------------+--------------------------------------------------------------------------------------------------------+
| **URL запиту**                                                 |   **https://doc.edin.ua/bdoc/filter**                                                                  |
+----------------------------------------------------------------+--------------------------------------------------------------------------------------------------------+
| **Параметри, що передаються в URL (разом з адресою методу)**   | В рядку заголовка (Header) "Set-Cookie" обов'язково передається SID - токен, отриманий при авторизації |
+----------------------------------------------------------------+--------------------------------------------------------------------------------------------------------+
| **Обов'язкові параметри, що передаються в тілі запиту (json)** | **filterName; periodType; dateFrom; dateTo;**                                                          |
+----------------------------------------------------------------+--------------------------------------------------------------------------------------------------------+

**JSON-параметри в тілі HTTPS запиту/відповіді**
*******************************************************************

``REQUEST``

Опис json-параметрів **запиту** метода API (об'єкт **PackageFilter_**)


``RESPONSE``

Опис json-параметрів **відповіді** метода API (об'єкт **PackageFilter**)

Таблиця 2 - Опис параметрів об'єкта **PackageFilter**

.. csv-table:: 
  :file: for_csv/PackageFilter.csv
  :widths:  1, 12, 41
  :header-rows: 1
  :stub-columns: 0


--------------

**Приклади**
*****************

Приклад тіла **запиту** (json):

.. code:: ruby

  {
    "folder": 1,
    "packageStatuses": [
      2,
      3,
      4,
      6,
      5,
      7,
      8
    ],
    "dateFrom": 0,
    "dateTo": 0,
    "senderCompaniesIds": [],
    "recipientCompaniesIds": [],
    "packageChainIds": [],
    "periodType": 1,
    "filterName": "альбус",
    "packageTagIds": []
  }

--------------

Приклад тіла **відповіді** (json): 

.. code:: ruby

  {
    "filterId": 129,
    "filterName": "альбус",
    "ownerCompaniesIds": [],
    "clientCompaniesIds": [],
    "senderCompaniesIds": [],
    "recipientCompaniesIds": [],
    "dateFrom": 0,
    "dateTo": 0,
    "packageTypesIds": [],
    "packageChainIds": [],
    "contractIds": [],
    "packageStatuses": [
      2,
      3,
      4,
      6,
      5,
      7,
      8
    ],
    "packageTagIds": [],
    "folder": 1,
    "periodType": 1,
    "dateShift": 0
  }



