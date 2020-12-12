---
description: 'Dowiedz się więcej o: TN047: złagodzeniu wymagań dotyczących wymagania dotyczące transakcji bazy danych'
title: 'TN047: mniejsze wymagania dotyczące transakcji bazy danych'
ms.date: 11/04/2016
f1_keywords:
- vc.data
helpviewer_keywords:
- TN047
ms.assetid: f93c51cf-a8c0-43d0-aa47-7bcb8333d693
ms.openlocfilehash: 6f356db75df93466bc392e555246a363e6b52187
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97215121"
---
# <a name="tn047-relaxing-database-transaction-requirements"></a>TN047: mniejsze wymagania dotyczące transakcji bazy danych

Ta Uwaga techniczna, która omawia wymagania dotyczące transakcji klas baz danych MFC ODBC, jest obecnie przestarzała. Przed MFC 4,2 klasy baz danych wymagały zachowania kursorów w zestawach rekordów po operacji **CommitTrans** lub **wycofywania** . Jeśli sterownik ODBC i system DBMS nie obsługują tego poziomu zachowywania kursora, klasy baz danych nie umożliwiały transakcji.

Począwszy od MFC 4,2, klasy baz danych ograniczają ograniczenie wymagające zachowywania kursora. Transakcje zostaną włączone, jeśli sterownik je obsługuje. Należy jednak teraz sprawdzić efekt operacji **CommitTrans** lub **wycofywania** na otwartych zestawach rekordów. Aby uzyskać więcej informacji, zobacz funkcje członkowskie [CDatabase:: GetCursorCommitBehavior](../mfc/reference/cdatabase-class.md#getcursorcommitbehavior) i [CDatabase:: GetCursorRollbackBehavior](../mfc/reference/cdatabase-class.md#getcursorrollbackbehavior) .

## <a name="see-also"></a>Zobacz też

[Uwagi techniczne według numeru](../mfc/technical-notes-by-number.md)<br/>
[Uwagi techniczne według kategorii](../mfc/technical-notes-by-category.md)
