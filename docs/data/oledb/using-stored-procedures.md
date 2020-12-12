---
description: 'Dowiedz się więcej o programie: używanie procedur składowanych'
title: korzystanie z procedur składowanych
ms.date: 10/24/2018
helpviewer_keywords:
- OLE DB, stored procedures
- stored procedures, Visual C++
- stored procedures, about stored procedures
- OLE DB provider templates, stored procedures
- stored procedures, OLE DB
ms.assetid: 90507e4c-eca2-46c9-ad8c-07e10dc1d41b
ms.openlocfilehash: 6bd7dbd3980eb4bfe0fbca71d86af080128d3309
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97319108"
---
# <a name="using-stored-procedures"></a>korzystanie z procedur składowanych

Procedura składowana jest obiektem wykonywalnym przechowywanym w bazie danych. Wywołanie procedury składowanej jest podobne do wywołania polecenia SQL. Korzystanie z procedur składowanych w źródle danych (zamiast wykonywania lub przygotowywania instrukcji w aplikacji klienckiej) może zapewnić kilka korzyści, w tym wyższą wydajność, zmniejszenie obciążenia sieci oraz lepszą spójność i dokładność.

Procedura składowana może zawierać dowolną liczbę parametrów wejściowych lub wyjściowych (w tym zero) i może przekazać wartość zwracaną. Można użyć wartości parametrów kodu twardego jako konkretnych wartości danych lub znacznika parametru (znak zapytania "?").

> [!NOTE]
> Procedury składowane SQL Server CLR utworzone przy użyciu Visual C++ muszą być kompilowane przy użyciu `/clr:safe` opcji kompilatora.

Dostawca OLE DB dla SQL Server (SQLOLEDB) obsługuje następujące mechanizmy, za pomocą których procedury składowane zwracają dane:

- Każda instrukcja **SELECT** w procedurze generuje zestaw wyników.

- Procedura może zwracać dane za pomocą parametrów wyjściowych.

- Procedura może mieć kod powrotu typu Integer.

> [!NOTE]
> Nie można użyć procedur składowanych z dostawcą OLE DB dla aparatu Jet, ponieważ ten dostawca nie obsługuje procedur składowanych. ciągi zapytań mogą dotyczyć tylko stałych.

## <a name="see-also"></a>Zobacz też

[Praca z szablonami konsumentów OLE DB](../../data/oledb/working-with-ole-db-consumer-templates.md)
