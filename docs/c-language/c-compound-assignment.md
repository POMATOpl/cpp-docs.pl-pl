---
description: Dowiedz się więcej o przypisaniu złożonej C
title: Przydział złożony języka C
ms.date: 11/04/2016
helpviewer_keywords:
- operators [C], assignment
- compound assignment operators
- assignment operators, compound
ms.assetid: db7b5893-cd56-4f1c-9981-5a024200ab63
ms.openlocfilehash: 73c47a506960d5c80e2a7f5693dcbacf770dbf02
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97211534"
---
# <a name="c-compound-assignment"></a>Przydział złożony języka C

Operatory przypisania złożonego łączą operator przypisania prostego z innym operatorem binarnym. Operatory przypisania złożonego wykonują operacje określone przez operator dodatkowy, a następnie przypisują wynik do lewego operandu. Na przykład wyrażenie przypisania złożonego, takie jak

> *wyrażenie1* **+=** *wyrażenie2*

można zrozumieć jako

> *wyrażenie1* **=** *wyrażenie1* **+** *wyrażenie2*

Jednak wyrażenie przypisania złożonego nie jest odpowiednikiem rozwiniętej wersji, ponieważ wyrażenie przypisania złożonego szacuje wartość *wyrażenie1* tylko raz, podczas gdy rozszerzona wersja szacuje wartość *wyrażenie1* dwa razy: w operacji dodawania i w operacji przypisania.

Argumenty operacji operatora przypisania złożonego muszą być typu całkowitego lub zmiennoprzecinkowego. Każdy operator przypisania złożonego wykonuje konwersje, które są wykonywane przez odpowiedni operator binarny i odpowiednio ogranicza typy argumentów. Operatory dodawania/przypisywania ( `+=` ) i odejmowania — przypisanie ( **-=** ) mogą także mieć lewy operand typu wskaźnik, w tym przypadku prawy operand musi być typu całkowitego. Wynikiem operacji przypisania złożonego jest wartość i typ argumentu operacji po lewej stronie.

```C
#define MASK 0xff00

n &= MASK;
```

W tym przykładzie operacje bitowe i łącznie są wykonywane w systemach `n` i `MASK` , a wynik jest przypisany do `n` . Stała manifestu `MASK` jest definiowana za pomocą dyrektywy preprocesora [#define](../preprocessor/hash-define-directive-c-cpp.md) .

## <a name="see-also"></a>Zobacz też

[Operatory przypisania języka C](../c-language/c-assignment-operators.md)
