---
description: 'Dowiedz się więcej o: Testowanie dostawcy'
title: Testowanie dostawcy
ms.date: 10/29/2018
helpviewer_keywords:
- testing, OLE DB providers
- testing providers
- OLE DB providers, testing
ms.assetid: bf824fe4-81af-4ffb-beb3-4fa2928dc450
ms.openlocfilehash: de9ba1b6cb66df8041cc6a94f357d52fc2194553
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97272659"
---
# <a name="testing-your-provider"></a>Testowanie dostawcy

Przed zwolnieniem dostawcy należy wykonać następujące testy w podanej kolejności. Te testy pokazują, że dostawca działa prawidłowo dla większości potencjalnych użytkowników.

1. Przetestuj dostawcę przy użyciu aplikacji [konsumenckiej](../../data/oledb/creating-an-ole-db-consumer.md) zapisaną przy użyciu szablonów konsumentów OLE DB. Konsument testowy powinien obejmować wszystkie obszary funkcjonalne dostawcy (cały kod, który został dodany lub zmodyfikowany).

1. Przetestuj dostawcę przy użyciu aplikacji konsumenta zapisaną przy użyciu modelu ADO. Większość deweloperów (zwłaszcza Microsoft Visual Basic i deweloperów Microsoft C#) używają obiektów ADO lub ADO.NET dla aplikacji konsumenckich. Konsument testowy powinien obejmować wszystkie obszary funkcjonalne dostawcy. Przykład aplikacji konsumenckiej ADO zawiera [przykłady kodu ADO w programie Microsoft Visual Basic](/previous-versions/ms807514(v=msdn.10)).

1. Uruchom testy zgodności OLE DB (w tym testy zgodne z ADO), aby pokazać, że Twój dostawca spełnia normy poziomu 0 dla dostawców OLE DB. (Aby uzyskać wyjaśnienie poziomu 0, Wyszukaj **testy zgodne z poziomem OLE DB 0** w [przewodniku OLE DB programisty](/sql/connect/oledb/ole-db/oledb-driver-for-sql-server-programming). Te testy i powiązane dokumenty są zawarte w Visual C++ w zestawie SDK dostępu do danych. Te testy pomagają również sprawdzić, czy dostawca działa dobrze, gdy są agregowane przez innych [dostawców usług](../../data/oledb/ole-db-resource-pooling-and-services.md) i są szczególnie przydatne w przypadku modyfikowania lub dodawania właściwości. Aby uzyskać więcej informacji na temat testów zgodności, zobacz plik Readme dla zestawu SDK dostępu do danych, który znajduje się na jednym z dysków CD programu Visual Studio.

## <a name="see-also"></a>Zobacz też

[Praca z szablonami dostawców OLE DB](../../data/oledb/working-with-ole-db-provider-templates.md)
