######################################################################
**Додавання (прив'язка) типу комплекта документів до документу**
######################################################################

Для роботи з цим методом користувач повинен бути `авторизованим <https://wiki-df-bank.edin.ua/uk/latest/API_DOCflow/Methods/Authorization.html>`__ .

.. important:: 
    Для активації комплекта документів достатньо додати документ - це є обов'язковою умовою, без документа користувач отримує повідомлення про помилку з проханням додати документ.

+----------------------------------------------------------------+------------------------------------------------------------------------------------------------------------+
|                        **Метод запиту**                        |                                             **HTTPS OPTIONS**                                              |
+================================================================+============================================================================================================+
| **Content-Type**                                               | application/json (тіло запиту/відповіді в json форматі в тілі HTTPS запиту)                                |
+----------------------------------------------------------------+------------------------------------------------------------------------------------------------------------+
| **URL запиту**                                                 |   **https://doc.edin.ua/bdoc/package_document**                                                            |
+----------------------------------------------------------------+------------------------------------------------------------------------------------------------------------+
| **Параметри, що передаються в URL (разом з адресою методу)**   | В рядку заголовка (Header) "Set-Cookie" обов'язково передається **SID** - токен, отриманий при авторизації |
+----------------------------------------------------------------+------------------------------------------------------------------------------------------------------------+
| **Обов'язкові параметри, що передаються в тілі запиту (json)** | **packageId, documentId**                                                                                  |
+----------------------------------------------------------------+------------------------------------------------------------------------------------------------------------+

**JSON-параметри в тілі HTTPS запиту/відповіді**
*******************************************************************

``REQUEST``

Опис json-параметрів **запиту** метода API (об'єкт **Document2Package**)

Таблиця 1 - Опис параметрів об'єкта **Document2Package**

.. csv-table:: 
  :file: for_csv/Document2Package.csv
  :widths:  1, 12, 41
  :header-rows: 1
  :stub-columns: 0

``RESPONSE``

Опис json-параметрів **відповіді** метода API (об'єкт **PackageType**)

Таблиця 2 - Опис параметрів об'єкта **PackageType**

.. csv-table:: 
  :file: for_csv/PackageType.csv
  :widths:  1, 12, 41
  :header-rows: 1
  :stub-columns: 0

Таблиця 3 - Опис параметрів об'єкта **Company**

.. csv-table:: 
  :file: for_csv/Company.csv
  :widths:  1, 12, 41
  :header-rows: 1
  :stub-columns: 0

Таблиця 4 - Опис параметрів об'єкта **Document2Package**

.. csv-table:: 
  :file: for_csv/Document2Package.csv
  :widths:  1, 12, 41
  :header-rows: 1
  :stub-columns: 0

Таблиця 5 - Опис параметрів об'єкта **Document**

.. csv-table:: 
  :file: for_csv/Document.csv
  :widths:  1, 12, 41
  :header-rows: 1
  :stub-columns: 0

--------------

**Приклади**
*****************

Приклад тіла **запиту** (json):

.. code:: ruby

  {
    "packageId": 1485,
    "documentId": 2391,
    "needSign": 0,
    "signsCount": 0,
    "ownerSignsCount": 0,
    "maxFilesCount": 3,
    "needEncrypt": 0,
    "required": 0,
    "isRecipientAttach": 0
  }

--------------

Приклад тіла **відповіді** (json): 

.. code:: ruby

  {
    "packageId": 1485,
    "companyId": 989,
    "name": "авыаыв123",
    "type": 1,
    "code": "323222",
    "packageChainId": 244,
    "status": 3,
    "version": 1,
    "dateChanged": 1557905884,
    "autoHandle": 0,
    "document2packages": [
      {
        "packageId": 1485,
        "documentId": 2391,
        "needSign": 0,
        "signsCount": 0,
        "ownerSignsCount": 0,
        "needEncrypt": 0,
        "required": 0,
        "isRecipientAttach": 0,
        "maxFilesCount": 3,
        "document": {
          "documentId": 2391,
          "companyId": 989,
          "name": "dsfdsfs",
          "type": 2,
          "code": "2322",
          "agreementProcId": 0,
          "isActive": 1,
          "extraFields": []
        }
      }
    ],
    "package2dictionaries": [],
    "extraFields": [],
    "company": {
      "companyId": 0,
      "accountId": 0,
      "type": 0,
      "name": "dwdsss",
      "code": "433",
      "isApproved": 0,
      "isSignedOffer": 0,
      "isActive": 0,
      "ownershipTypeId": 0,
      "certificates": [],
      "dictionaries": [],
      "notifySettings": []
    }
  }


