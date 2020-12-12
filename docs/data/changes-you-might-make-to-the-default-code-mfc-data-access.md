---
description: 'Dowiedz się więcej na temat: zmiany wprowadzone w kodzie domyślnym (dostęp do danych MFC)'
title: Zmiany wprowadzone w kodzie domyślnym (dostęp do danych MFC)
ms.date: 11/04/2016
helpviewer_keywords:
- record views [C++], customizing default code
ms.assetid: 9992ed37-a6bf-45a5-a572-5c14e42b6628
ms.openlocfilehash: 431144eeaf7ef0a2413e4d9e3931016c2505d338
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97181452"
---
# <a name="changes-you-might-make-to-the-default-code--mfc-data-access"></a>Zmiany wprowadzone w kodzie domyślnym (dostęp do danych MFC)

[Kreator aplikacji MFC](../mfc/reference/database-support-mfc-application-wizard.md) zapisuje klasę zestawu rekordów, która wybiera wszystkie rekordy w pojedynczej tabeli. Często należy zmienić to zachowanie na co najmniej jeden z następujących sposobów:

- Ustaw filtr lub kolejność sortowania dla zestawu rekordów. Zrób to w `OnInitialUpdate` przypadku konstruowania obiektu zestawu rekordów, ale przed `Open` wywołaniem jego funkcji składowej. Aby uzyskać więcej informacji, zobacz [zestaw rekordów: filtrowanie rekordów (ODBC)](../data/odbc/recordset-filtering-records-odbc.md) i [zestaw rekordów: sortowanie rekordów (ODBC)](../data/odbc/recordset-sorting-records-odbc.md).

- Sparametryzuj zestaw rekordów. Określ rzeczywistą wartość parametru Run po filtrowaniu. Aby uzyskać więcej informacji, zobacz [zestaw rekordów: parametryzacja a zestaw rekordów (ODBC)](../data/odbc/recordset-parameterizing-a-recordset-odbc.md)

- Przekaż dostosowany ciąg SQL do funkcji [Open](../mfc/reference/crecordset-class.md#open) member. Aby zapoznać się z tym, co można zrobić za pomocą tej techniki, zobacz [SQL: dostosowywanie instrukcji SQL zestawu rekordów (ODBC)](../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md).

## <a name="see-also"></a>Zobacz też

[Korzystanie z widoku rekordu](../data/using-a-record-view-mfc-data-access.md)
