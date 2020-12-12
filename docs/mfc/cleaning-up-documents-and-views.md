---
description: 'Dowiedz się więcej o: Oczyszczanie dokumentów i widoków'
title: Oczyszczanie dokumentów i widoków
ms.date: 11/04/2016
helpviewer_keywords:
- views [MFC], cleaning up
- documents [MFC], cleaning up
- documents [MFC], closing
ms.assetid: 0c454db2-3644-434d-9e53-8108a7aedfe1
ms.openlocfilehash: 73d7dcb94068499998ac05d76dd023b7274c6588
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97176656"
---
# <a name="cleaning-up-documents-and-views"></a>Oczyszczanie dokumentów i widoków

Gdy dokument zostanie zamknięty, struktura najpierw wywołuje jego funkcję członkowską [DeleteContents](reference/cdocument-class.md#deletecontents) . W przypadku przydzielenia dowolnej ilości pamięci na stercie w trakcie operacji dokumentu, `DeleteContents` najlepszym miejscem, aby ją cofnąć.

> [!NOTE]
> Nie należy cofać alokacji danych dokumentu w destruktorze dokumentu. W przypadku aplikacji SDI, obiekt dokumentu może być ponownie używany.

Można zastąpić destruktor widoku, aby cofnąć alokację dowolnej pamięci przydzieloną na stercie.

## <a name="see-also"></a>Zobacz też

[Inicjowanie i oczyszczanie dokumentów i widoków](initializing-and-cleaning-up-documents-and-views.md)
