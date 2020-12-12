---
description: 'Dowiedz się więcej o: transakcje (dostęp do danych MFC)'
title: Transakcje (dostęp do danych MFC)
ms.date: 11/04/2016
helpviewer_keywords:
- transactions [C++], support for
- transactions [C++]
- databases [C++], transactions
ms.assetid: f80afbfe-1517-4fec-8870-9ffc70a58b05
ms.openlocfilehash: bd04e1c8f1b5ef11e66a3c2c3f1e391f409b4892
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97116486"
---
# <a name="transactions--mfc-data-access"></a>Transakcje (dostęp do danych MFC)

Koncepcja transakcji została opracowana w celu obsługi przypadków, w których stan wynikający z bazy danych zależy od całkowitego sukcesu serii operacji. Może to wynikać z faktu, że kolejne operacje mogą zmodyfikować wyniki poprzednich operacji. W takich przypadkach, jeśli jedna operacja nie powiedzie się, stan wyników może być nieokreślony.

Aby rozwiązać ten problem, grupy transakcji grupują serię operacji w taki sposób, aby zapewnić integralność końcowego wyniku. Wszystkie operacje muszą się zakończyć, a następnie zostać zatwierdzone (zapisywane w bazie danych) lub cała transakcja nie powiedzie się. Anulowanie transakcji jest nazywane wycofywaniem. Funkcja wycofywania umożliwia odzyskiwanie zmian i zwraca bazę danych do stanu sprzed transakcji.

Na przykład w zautomatyzowanej transakcji bankowej, jeśli dokonasz transferu pieniędzy z konta A do konta B, zarówno wycofanie od a, jak i kaucja na B muszą pomyślnie przetworzyć odpowiednie środki lub cała transakcja nie powiedzie się.

Transakcja musi mieć właściwości KWAŚNe, które są dostępne dla następujących:

- **Niepodzielność** Transakcja jest niepodzielną jednostką pracy i jest wykonywana dokładnie raz; wszystkie zadania są wykonywane albo żadna z nich nie jest.

- **Spójność** Transakcja zachowuje spójność danych i przekształca jeden spójny stan danych na inny spójny stan danych. Dane powiązane z transakcją muszą być zakonserwowane semantycznie.

- **Izolacja** Transakcja jest jednostką izolacji, a każda z nich występuje oddzielnie i niezależnie od współbieżnych transakcji. Transakcja nie powinna nigdy widzieć etapów pośrednich innej transakcji.

- **Trwałość** Transakcja jest jednostką odzyskiwania. Jeśli transakcja zakończy się powodzeniem, jej aktualizacje są zachowywane nawet wtedy, gdy system ulegnie awarii lub zostanie zamknięty. Jeśli transakcja nie powiedzie się, system pozostanie w stanie poprzedzającym zatwierdzenie transakcji.

Można obsługiwać transakcje w OLE DB (zobacz temat [Obsługa transakcji w OLE DB](../data/oledb/supporting-transactions-in-ole-db.md)) lub ODBC (zobacz [Transaction (ODBC)](../data/odbc/transaction-odbc.md)).

Transakcja rozproszona to transakcja, która aktualizuje dane rozproszone, czyli dane w więcej niż jednym sieciowym systemie komputerowym. Jeśli chcesz obsługiwać transakcje za pośrednictwem systemu rozproszonego, należy użyć ADO.NET zamiast obsługi transakcji OLE DB.

## <a name="see-also"></a>Zobacz też

[Programowanie dostępu do danych (MFC/ATL)](../data/data-access-programming-mfc-atl.md)
