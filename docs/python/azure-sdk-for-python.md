---
title: Azure SDK pro Python | Microsoft Docs
ms.custom: 
ms.date: 03/07/2017
ms.reviewer: 
ms.suite: 
ms.technology: devlang-python
ms.devlang: python
ms.tgt_pltfrm: 
ms.topic: article
caps.latest.revision: "11"
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload:
- python
- azure
ms.openlocfilehash: 647b07e3816551e60e176280199ad5298db53200
ms.sourcegitcommit: 9357209350167e1eb7e50b483e44893735d90589
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/05/2018
---
# <a name="azure-sdk-for-python"></a>Azure SDK pro Python

Sada Azure SDK pro Python usnadňuje využívat a spravovat služby Microsoft Azure z aplikací, které běží na systému Windows, Mac OSX a Linux.

## <a name="installation"></a>Instalace

Azure SDK je nainstalovat z [indexu balíčků Pythonu](https://pypi.python.org/pypi/azure).

Nainstalujte **nejnovější stabilní verze** (podporuje Python 2.7 a 3.3 +) následujícím způsobem:

```command
pip install azure
```

Můžete také provést [instalaci Pythonu a sady SDK](https://azure.microsoft.com/documentation/articles/python-how-to-install/) v dokumentaci k Azure.

## <a name="documentation"></a>Dokumentace

Dokumentaci můžete najít na [azure sdk pro python.readthedocs.org](http://azure-sdk-for-python.readthedocs.org/en/latest/index.html).

[Azure SDK pro středisku pro vývojáře Python](http://azure.microsoft.com/develop/python/) má také počet užitečné zdroje, včetně počtu kurzy, jako například:

- Vytvoření webové aplikace s [Django](/azure/app-service-web/web-sites-python-create-deploy-django-app) [Flask](/azure/app-service-web/web-sites-python-create-deploy-flask-app), a [Bottle](/azure/app-service-web/web-sites-python-create-deploy-bottle-app).
- [Úložiště objektů BLOB](/azure/storage/storage-python-how-to-use-blob-storage)
- [Úložiště Table](/azure/storage/storage-python-how-to-use-table-storage)
- [Fronty úložiště](/azure/storage/storage-python-how-to-use-queue-storage)
- [DocumentDB](/azure/documentdb/documentdb-python-application)
- [Fronty služby Service Bus](/azure/service-bus-messaging/service-bus-python-how-to-use-queues)
- [Předplatné témata sběrnice služeb](/azure/service-bus-messaging/service-bus-python-how-to-use-topics-subscriptions)
- [Správa služeb](/azure/cloud-services/cloud-services-python-how-to-use-service-management)

Pro veřejná rozhraní API bez dokumentaci, jednotka testů v [sady SDK úložiště GitHub](https://github.com/Azure/azure-sdk-for-python) jsou dobrou zdroje informací:

- [Testy jednotek](https://github.com/Azure/azure-storage-python/tree/master/tests)
- [Testování částí Service Bus](https://github.com/Azure/azure-sdk-for-python/tree/master/azure-servicebus/tests)
- [Správa služeb testování částí](https://github.com/Azure/azure-sdk-for-python/tree/master/azure-servicemanagement-legacy/tests)
- [Testování částí správy prostředků](https://github.com/Azure/azure-sdk-for-python/tree/master/azure-mgmt/tests)

## <a name="support"></a>Podpora

Se nachází v úložišti Git sady SDK [https://github.com/Azure/azure-sdk-for-python](https://github.com/Azure/azure-sdk-for-python).

[Soubor problémy v úložišti](https://github.com/Azure/azure-sdk-for-python/issues) -li vyhledat potíže nebo máte otázky týkající se použití sady SDK.
