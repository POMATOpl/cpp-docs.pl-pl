---
description: Dowiedz się więcej o parametrach wyjściowych
title: Parametry wyjściowe
ms.date: 10/24/2018
helpviewer_keywords:
- OLE DB, stored procedures
- stored procedures, calling
- stored procedures, parameters
- procedure calls
- procedure calls, stored procedures
ms.assetid: 4f7c2700-1c2d-42f3-8c9f-7e83962b2442
ms.openlocfilehash: c52877483d40d7de1a8313eb806769ce92af7337
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97316937"
---
# <a name="output-parameters"></a>Parametry wyjściowe

Wywołanie procedury składowanej jest podobne do uruchamiania polecenia SQL. Główną różnicą jest to, że procedury składowane używają parametrów wyjściowych (lub "parametrów") i zwracanych wartości.

W poniższej procedurze składowanej pierwszy "?" jest wartością zwracaną (telefon), a drugi "?" jest parametrem wejściowym (Name):

```cpp
DEFINE_COMMAND_EX(CMySProcAccessor, _T("{ ? = SELECT phone FROM shippers WHERE name = ? }"))
```

Parametry wejściowe i out są określane na mapie parametrów:

```cpp
BEGIN_PARAM_MAP(CMySProcAccessor)
   SET_PARAM_TYPE(DBPARAMIO_OUTPUT)
   COLUMN_ENTRY(1, m_Phone)   // Phone is the return value
   SET_PARAM_TYPE(DBPARAMIO_INPUT)
   COLUMN_ENTRY(2, m_Name)   // Name is the input parameter
END_PARAM_MAP()
```

Aplikacja musi obsługiwać dane wyjściowe zwracane z procedur składowanych. Różne dostawcy OLE DB zwracają parametry wyjściowe i zwracają wartości w różnym czasie podczas przetwarzania wyniku. Na przykład dostawca OLE DB firmy Microsoft dla SQL Server (SQLOLEDB) nie dostarcza parametrów wyjściowych i kodów powrotu dopiero po pobraniu lub anulowaniu przez odbiorcę zestawów wyników zwracanych przez procedurę składowaną. Dane wyjściowe są zwracane w ostatnim pakiecie TDS z serwera.

## <a name="row-count"></a>Liczba wierszy

Jeśli użyjesz szablonów konsumentów OLE DB do wykonania procedury składowanej z parametrami, liczba wierszy nie zostanie ustawiona do momentu zamknięcia zestawu wierszy.

Rozważmy na przykład procedurę składowaną z zestawem wierszy i parametrem:

```sql
create procedure sp_test
   @_rowcount integer output
as
   select top 50 * from test
   @_rowcount = @@rowcount
return 0
```

Parametr, który `@_rowcount` informuje, ile wierszy zostało zwróconych z tabeli testowej. Jednakże ta procedura składowana ogranicza liczbę wierszy do 50. Na przykład jeśli w teście wystąpiło 100 wierszy, liczba wierszy będzie 50 (ponieważ ten kod pobiera tylko pierwsze 50 wierszy). Jeśli tabela zawiera tylko 30 wierszy, liczba wierszy wynosi 30. Upewnij się, że Wywołaj `Close` lub `CloseAll` , aby wypełnić parametr, przed pobraniem jego wartości.

## <a name="see-also"></a>Zobacz też

[Korzystanie z procedur składowanych](../../data/oledb/using-stored-procedures.md)
