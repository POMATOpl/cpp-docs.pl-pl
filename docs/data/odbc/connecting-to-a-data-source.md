---
description: 'Dowiedz się więcej o: Nawiązywanie połączenia ze źródłem danych'
title: Nawiązywanie połączenia ze źródłem danych
ms.date: 11/04/2016
helpviewer_keywords:
- database connections [C++], ODBC
- ODBC connections [C++], using
- connections [C++], data source
- databases [C++], connecting to
- data sources [C++], connecting to
- ODBC data sources [C++], connections
- database connections [C++], MFC ODBC classes
ms.assetid: ef6c8c98-5979-43a8-9fb5-5bb06fc59f36
ms.openlocfilehash: 3bc5436a678d39682b89d82dd7f3ab90eb6f5bb5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97295123"
---
# <a name="connecting-to-a-data-source"></a>Nawiązywanie połączenia ze źródłem danych

Źródło danych ODBC to określony zestaw danych, informacje wymagane do uzyskania dostępu do tych danych oraz lokalizacja źródła danych, które można opisać przy użyciu nazwy źródła danych. Z punktu widzenia programu źródło danych zawiera dane, system DBMS, Sieć (jeśli istnieje) i ODBC.

Aby uzyskać dostęp do danych dostarczanych przez źródło danych, program musi najpierw nawiązać połączenie ze źródłem danych. Cały dostęp do danych jest zarządzany przez to połączenie.

Połączenia ze źródłem danych są hermetyzowane przez klasę [CDatabase](../../mfc/reference/cdatabase-class.md). Gdy `CDatabase` obiekt jest połączony ze źródłem danych, można:

- Konstruowanie [zestawów rekordów](../../mfc/reference/crecordset-class.md), które wybierają rekordy z tabel lub zapytań.

- Zarządzanie [transakcjami](../../data/odbc/transaction-odbc.md), przetwarzanie wsadowe aktualizacji i wszystkie są zatwierdzane jednocześnie do źródła danych (lub cała transakcja jest wycofywana, więc źródło danych jest niezmienione) — Jeśli źródło danych obsługuje wymagany poziom transakcji.

- Bezpośrednie wykonywanie instrukcji [SQL](../../data/odbc/sql.md) .

Po zakończeniu pracy z połączeniem źródła danych należy zamknąć `CDatabase` obiekt i zniszczyć go lub użyć ponownie w celu nowego połączenia. Aby uzyskać więcej informacji na temat połączeń ze źródłem danych, zobacz [Data Source (ODBC)](../../data/odbc/data-source-odbc.md).

## <a name="see-also"></a>Zobacz też

[ODBC i MFC](../../data/odbc/odbc-and-mfc.md)
