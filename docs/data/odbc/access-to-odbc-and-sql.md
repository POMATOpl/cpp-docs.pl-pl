---
description: 'Dowiedz się więcej o: dostęp do ODBC i SQL'
title: Dostęp do ODBC i SQL
ms.date: 11/04/2016
helpviewer_keywords:
- API calls [C++], calling DAO or ODBC directly
- Windows API [C++], calling from MFC
- ODBC API functions [C++]
- ODBC API functions [C++], calling from MFC
- SQL [C++], calling ODBC API functions
- ODBC [C++], API functions
ms.assetid: 5613d7dc-00b7-4646-99ae-1116c05c52b4
ms.openlocfilehash: 507e3a8e2d88c253f193de41be1a28ae0c5cba87
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97295149"
---
# <a name="access-to-odbc-and-sql"></a>Dostęp do ODBC i SQL

Biblioteka MFC hermetyzuje wiele wywołań interfejsu API systemu Windows i nadal umożliwia bezpośrednie wywoływanie dowolnej funkcji interfejsu API systemu Windows. Klasy baz danych zapewniają taką samą elastyczność, jak w przypadku interfejsu API ODBC. Chociaż klasy baz danych osłony z dużą złożonością ODBC, można wywołać funkcje interfejsu API ODBC bezpośrednio z dowolnego miejsca w programie.

Analogicznie, klasy baz danych osłony nie muszą współpracować z [programem SQL](../../data/odbc/sql.md), ale możesz użyć programu SQL bezpośrednio, jeśli chcesz. Można dostosować obiekty zestawu rekordów przez przekazanie niestandardowej instrukcji SQL (lub ustawienie części instrukcji domyślnej) po otwarciu zestawu rekordów. Można również wykonywać wywołania SQL bezpośrednio przy użyciu funkcji składowej [ExecuteSql by](../../mfc/reference/cdatabase-class.md#executesql) klasy [CDatabase](../../mfc/reference/cdatabase-class.md).

Aby uzyskać więcej informacji, zobacz [ODBC: bezpośrednie wywoływanie funkcji ODBC API](../../data/odbc/odbc-calling-odbc-api-functions-directly.md) i [SQL: wykonywanie bezpośrednich wywołań SQL (ODBC)](../../data/odbc/sql-making-direct-sql-calls-odbc.md).

## <a name="see-also"></a>Zobacz też

[ODBC i MFC](../../data/odbc/odbc-and-mfc.md)
