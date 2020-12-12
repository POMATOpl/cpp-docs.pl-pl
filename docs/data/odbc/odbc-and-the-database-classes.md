---
description: 'Dowiedz się więcej na temat: ODBC i klasy baz danych'
title: ODBC i klasy baz danych
ms.date: 11/04/2016
helpviewer_keywords:
- database classes [C++], ODBC
- ODBC API functions [C++]
- ODBC classes [C++], MFC database classes
- MFC [C++], ODBC and
ms.assetid: b166f82d-6f85-4556-aac8-fb851235d22c
ms.openlocfilehash: 146170ddd97dfc2797fd1f755459f370be638ded
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97326773"
---
# <a name="odbc-and-the-database-classes"></a>ODBC i klasy baz danych

Klasy baz danych MFC ODBC hermetyzują wywołania funkcji interfejsu API ODBC, które zwykle należy do funkcji składowych klas [CDatabase](../../mfc/reference/cdatabase-class.md) i [CRecordset](../../mfc/reference/crecordset-class.md) . Na przykład złożone sekwencje wywołań ODBC, powiązanie zwracanych rekordów z lokalizacjami przechowywania, obsługa warunków błędów i inne operacje są zarządzane przez klasy baz danych. W efekcie należy użyć znacznie prostszego interfejsu klasy do manipulowania rekordami za pomocą obiektu zestawu rekordów.

> [!NOTE]
> Źródła danych ODBC są dostępne za pośrednictwem klas MFC ODBC, zgodnie z opisem w tym temacie lub za pośrednictwem klas obiektów dostępu do danych MFC (DAO).

Chociaż klasy baz danych hermetyzują funkcje ODBC, nie zapewniają mapowania jeden-do-jednego funkcji interfejsu API ODBC. Klasy baz danych zapewniają wyższy poziom abstrakcji, modeluje się po obiektach dostępu do danych znajdujących się w programie Microsoft Access i Microsoft Visual Basic. Aby uzyskać więcej informacji, zobacz [ODBC i MFC](../../data/odbc/odbc-and-mfc.md).

## <a name="see-also"></a>Zobacz też

[Podstawowe informacje dotyczące ODBC](../../data/odbc/odbc-basics.md)
