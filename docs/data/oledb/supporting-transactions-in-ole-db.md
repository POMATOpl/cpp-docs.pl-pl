---
description: Dowiedz się więcej o obsłudze transakcji w OLE DB
title: Obsługa transakcji w OLE DB
ms.date: 10/24/2018
helpviewer_keywords:
- OLE DB consumer templates [C++], transaction support
- transactions [C++], OLE DB support for
- nested transactions [C++]
- OLE DB [C++], transaction support
- databases [C++], transactions
- distributed transactions [C++]
ms.assetid: 3d72e583-ad38-42ff-8f11-e2166d60a5a7
ms.openlocfilehash: f8d01a0d359a3d33fbe4b88877d8a4452f257c16
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97272724"
---
# <a name="supporting-transactions-in-ole-db"></a>Obsługa transakcji w OLE DB

[Transakcja](../../data/transactions-mfc-data-access.md) to metoda grupowania lub wsadowego szeregu aktualizacji źródła danych, dzięki czemu wszystkie sukcesy i są zatwierdzane jednocześnie lub (Jeśli którykolwiek z nich ulegnie awarii) nie zostanie zatwierdzone i cała transakcja zostanie wycofana. Ten proces zapewnia integralność wyniku w źródle danych.

OLE DB obsługuje transakcje przy użyciu następujących trzech metod:

- [ITransactionLocal::StartTransaction](/previous-versions/windows/desktop/ms709786(v=vs.85))

- [ITransaction:: Commit](/previous-versions/windows/desktop/ms713008(v=vs.85))

- [ITransaction:: Abort](/previous-versions/windows/desktop/ms709833(v=vs.85))

## <a name="relationship-of-sessions-and-transactions"></a>Relacja między sesjami i transakcjami

Pojedynczy obiekt źródła danych może utworzyć jeden lub więcej obiektów sesji, z których każdy może znajdować się wewnątrz lub poza zakresem transakcji w danym momencie.

Gdy sesja nie wprowadza transakcji, wszystkie działania wykonywane w ramach tej sesji w magazynie danych są natychmiast zatwierdzane dla każdego wywołania metody. (Jest to czasami określane jako tryb automatycznego zatwierdzania lub tryb niejawny).

Gdy sesja przejdzie do transakcji, wszystkie działania wykonywane w ramach tej sesji w magazynie danych są częścią tej transakcji i są zatwierdzane lub przerywane jako pojedyncza jednostka. (Jest to czasami określane jako tryb zatwierdzania ręcznego).

Obsługa transakcji jest specyficzna dla dostawcy. Jeśli używany dostawca obsługuje transakcje, obiekt sesji obsługujący `ITransaction` i `ITransactionLocal` może wprowadzać niezagnieżdżoną transakcję. Klasa szablonów OLE DB [CSession](../../data/oledb/csession-class.md) obsługuje te interfejsy i jest zalecanym sposobem implementacji obsługi transakcji w Visual C++.

## <a name="starting-and-ending-the-transaction"></a>Uruchamianie i Kończenie transakcji

Należy wywołać `StartTransaction` metody, `Commit` , i `Abort` w obiekcie zestawu wierszy w odbiorcy.

Wywołanie `ITransactionLocal::StartTransaction` uruchamia nową transakcję lokalną. Po rozpoczęciu transakcji wszelkie zmiany zlecone przez późniejsze operacje nie są stosowane do magazynu danych do momentu zatwierdzenia transakcji.

Wywołanie `ITransaction::Commit` lub `ITransaction::Abort` zakończenie transakcji. `Commit` powoduje, że wszystkie zmiany w zakresie transakcji mają być stosowane do magazynu danych. `Abort` powoduje, że wszystkie zmiany w zakresie transakcji mają zostać anulowane, a magazyn danych pozostanie w stanie sprzed rozpoczęcia transakcji.

## <a name="nested-transactions"></a>Transakcje zagnieżdżone

[Transakcja zagnieżdżona](/previous-versions/windows/desktop/ms716985(v=vs.85)) występuje po rozpoczęciu nowej transakcji lokalnej, gdy aktywna transakcja już istnieje w sesji. Nowa transakcja jest uruchamiana jako zagnieżdżona transakcja poniżej bieżącej transakcji. Jeśli dostawca nie obsługuje transakcji zagnieżdżonych, wywoływanie, `StartTransaction` gdy istnieje już aktywna transakcja w sesji zwracająca XACT_E_XTIONEXISTS.

## <a name="distributed-transactions"></a>Transakcje rozproszone

Transakcja rozproszona to transakcja, która aktualizuje dane rozproszone; oznacza to, że dane w więcej niż jednym sieciowym systemie komputerowym. Jeśli chcesz obsługiwać transakcje w systemie rozproszonym, użyj .NET Framework, a nie OLE DB transakcji.

## <a name="see-also"></a>Zobacz też

[Korzystanie z metod dostępu](../../data/oledb/using-accessors.md)
