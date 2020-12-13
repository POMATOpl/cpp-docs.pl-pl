---
description: 'Dowiedz się więcej na temat: korzystanie z ręcznych metod dostępu'
title: Korzystanie z ręcznych metod dostępu
ms.date: 10/24/2018
helpviewer_keywords:
- command handling, OLE DB Templates
- manual accessors
- accessors [C++], manual
ms.assetid: 29f00a89-0240-482b-8413-4120b9644672
ms.openlocfilehash: 73363be83e06a3eeced114dc90c65f82601a4a16
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97332478"
---
# <a name="using-manual-accessors"></a>Korzystanie z ręcznych metod dostępu

Podczas obsługi nieznanego polecenia należy wykonać cztery czynności:

- Określanie parametrów

- Wykonaj polecenie

- Określanie kolumn wyjściowych

- Sprawdź, czy istnieje wiele zestawów wierszy powrotu

Aby wykonać te czynności za pomocą OLE DB szablonów konsumentów, użyj `CManualAccessor` klasy i wykonaj następujące kroki:

1. Otwórz `CCommand` obiekt za pomocą `CManualAccessor` jako parametru szablonu.

    ```cpp
    CCommand<CManualAccessor, CRowset, CMultipleResults> rs;
    ```

1. Wykonaj zapytanie dotyczące sesji dla `IDBSchemaRowset` interfejsu i użyj zestawu wierszy parametrów procedury. Jeśli `IDBSchemaRowset` interfejs nie jest dostępny, należy wykonać zapytanie dotyczące `ICommandWithParameters` interfejsu. Wywołaj, `GetParameterInfo` Aby uzyskać informacje. Jeśli żaden interfejs nie jest dostępny, można założyć, że nie ma żadnych parametrów.

1. Dla każdego parametru Wywołaj polecenie, `AddParameterEntry` Aby dodać parametry i ustawić je.

1. Otwórz zestaw wierszy, ale ustaw parametr bind na **`false`** .

1. Wywołaj `GetColumnInfo` , aby pobrać kolumny wyjściowe. Służy `AddBindEntry` do dodawania kolumny danych wyjściowych do powiązania.

1. Wywołaj `GetNextResult` , aby określić, czy są dostępne więcej zestawów wierszy. Powtórz kroki od 2 do 5.

Przykład ręcznej metody dostępu można znaleźć `CDBListView::CallProcedure` w sekcji w przykładzie [DBVIEWER](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Consumer) .

## <a name="see-also"></a>Zobacz też

[Korzystanie z metod dostępu](../../data/oledb/using-accessors.md)
