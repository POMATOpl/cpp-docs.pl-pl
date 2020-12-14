---
description: 'Dowiedz się więcej o: Instrukcja wyrażenia'
title: Instrukcja wyrażeń
ms.date: 11/04/2016
helpviewer_keywords:
- statements [C++], expression
- expression statements
ms.assetid: 547d7f7a-58be-4ffc-a4b3-d64c7ae7538c
ms.openlocfilehash: a208951c536883f2f08a6e856e9da48884255b1a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97186548"
---
# <a name="expression-statement"></a>Instrukcja wyrażeń

Instrukcje wyrażenia powodują, że wyrażenia mają być oceniane. Żaden transfer kontrolki lub iteracji nie ma miejsca w wyniku instrukcji wyrażenia.

Składnia instrukcji Expression jest po prostu

## <a name="syntax"></a>Składnia

```
[expression ] ;
```

## <a name="remarks"></a>Uwagi

Wszystkie wyrażenia w instrukcji wyrażenia są oceniane i wszystkie efekty uboczne są kończone przed wykonaniem następnej instrukcji. Najczęstsze instrukcje wyrażeń to przypisania i wywołania funkcji.  Ponieważ wyrażenie jest opcjonalne, sam średnik jest uznawany za pustą instrukcję wyrażenia, nazywaną instrukcją [null](../cpp/null-statement.md) .

## <a name="see-also"></a>Zobacz też

[Omówienie instrukcji języka C++](../cpp/overview-of-cpp-statements.md)
