---
description: 'Dowiedz się więcej o: funkcjach klas widoków rekordów (dostęp do danych MFC)'
title: Funkcje klas widoków rekordów (dostęp do danych MFC)
ms.date: 11/04/2016
helpviewer_keywords:
- record views, classes
- record view classes
ms.assetid: e7b2820f-09c4-483f-83c0-317e8be42bdf
ms.openlocfilehash: bf2a0bd1a609fcb29eb945f60ab22c4632addf1b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97116538"
---
# <a name="features-of-record-view-classes--mfc-data-access"></a>Funkcje klas widoków rekordów (dostęp do danych MFC)

Można tworzyć oparte na formularzach Programowanie dostępu do danych za pomocą klasy [CFormView](../mfc/reference/cformview-class.md), ale [formularzy CRecordView](../mfc/reference/crecordview-class.md) jest ogólnie lepszym rozwiązaniem dla klasy. Oprócz jego `CFormView` funkcji `CRecordView` :

- Udostępnia wymianę danych okna dialogowego (DDX) między kontrolkami formularzy i skojarzonym obiektem zestawu rekordów.

- Obsługuje najpierw przenoszenie, przenoszenie dalej, przenoszenie poprzedniego i przenoszenie ostatnich poleceń w celu nawigowania po rekordach w skojarzonym obiekcie zestawu rekordów.

- Aktualizuje zmiany w bieżącym rekordzie, gdy użytkownik przejdzie do innego rekordu.

Aby uzyskać więcej informacji na temat nawigacji, zobacz [widoki rekordów: obsługa nawigacji w widoku rekordu](../data/supporting-navigation-in-a-record-view-mfc-data-access.md).

## <a name="see-also"></a>Zobacz też

[Widoki rekordów (dostęp do danych MFC)](../data/record-views-mfc-data-access.md)<br/>
[Lista sterowników ODBC](../data/odbc/odbc-driver-list.md)
