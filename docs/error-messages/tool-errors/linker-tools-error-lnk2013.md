---
description: 'Dowiedz się więcej na temat: Błąd narzędzi konsolidatora LNK2013'
title: Błąd narzędzi konsolidatora LNK2013
ms.date: 11/04/2016
f1_keywords:
- LNK2013
helpviewer_keywords:
- LNK2013
ms.assetid: 21408e2d-3f56-4d1f-a031-00df70785ed4
ms.openlocfilehash: 51b754e19656ad8ec7ef1686605086b6e4a41853
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338465"
---
# <a name="linker-tools-error-lnk2013"></a>Błąd narzędzi konsolidatora LNK2013

przepełnienie naprawy typu naprawy. Obiekt docelowy "Nazwa symbolu" jest poza zakresem

Konsolidator nie może dopasować wymaganego adresu lub przesunięcia do podanych instrukcji, ponieważ symbol docelowy jest zbyt daleko od lokalizacji instrukcji.

Ten problem można rozwiązać przez utworzenie wielu obrazów lub użycie opcji [/Order](../../build/reference/order-put-functions-in-order.md) , aby instrukcje i cel zostały bliżej siebie.

Gdy nazwa symbolu jest symbolem zdefiniowanym przez użytkownika (a nie symbolem wygenerowanym przez kompilator), możesz również spróbować wykonać następujące czynności, aby rozwiązać ten problem:

- Zmień statyczną funkcję na niestatyczną.

- Zmień nazwę sekcji kodu zawierającej funkcję statyczną tak, aby była taka sama jak obiekt wywołujący.

Użyj `DUMPBIN /SYMBOLS` , aby sprawdzić, czy funkcja jest statyczna.
