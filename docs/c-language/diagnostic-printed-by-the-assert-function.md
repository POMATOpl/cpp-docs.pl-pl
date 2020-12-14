---
description: 'Dowiedz się więcej na temat: DIAGNOSTYKA wydrukowana przez funkcję Assert'
title: Diagnostyka wydrukowana przez funkcję assert
ms.date: 11/04/2016
ms.assetid: 78b64200-520d-40da-9a61-71553f411d4f
ms.openlocfilehash: cab4f6dfd2cab7d4b46486a103b39abb6ca17005
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97186795"
---
# <a name="diagnostic-printed-by-the-assert-function"></a>Diagnostyka wydrukowana przez funkcję assert

**ANSI 4,2** Diagnostyka wydrukowana przez i zakończenie działania funkcji **Assert**

Funkcja **Assert** drukuje komunikat diagnostyczny i wywołuje procedurę **Abort** , jeśli wyrażenie ma wartość false (0). Komunikat diagnostyczny ma postać

> **Potwierdzenie nie powiodło się**: <em>wyrażenie</em>**, plik** <em>filename</em>**, line** *LineNumber*

gdzie *filename* jest nazwą pliku źródłowego, a *LineNumber* jest numerem wiersza potwierdzenia, który zakończył się niepowodzeniem w pliku źródłowym. Jeśli *wyrażenie* ma wartość true (niezerowe), nie jest wykonywana żadna akcja.

## <a name="see-also"></a>Zobacz też

[Funkcje biblioteki](../c-language/library-functions.md)
