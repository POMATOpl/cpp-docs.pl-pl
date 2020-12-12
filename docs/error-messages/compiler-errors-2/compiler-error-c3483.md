---
description: 'Dowiedz się więcej o: błąd kompilatora C3483'
title: Błąd kompilatora C3483
ms.date: 11/04/2016
f1_keywords:
- C3483
helpviewer_keywords:
- C3483
ms.assetid: 18b3a2c5-dfc9-4661-9653-08a5798474cf
ms.openlocfilehash: 7c67e1e4d44c64fbcc023ee410dff2ecdd92c361
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97113391"
---
# <a name="compiler-error-c3483"></a>Błąd kompilatora C3483

element "var" jest już częścią listy przechwytywania lambda

Ta sama zmienna została przeniesiona na listę przechwytywania wyrażenia lambda więcej niż jeden raz.

### <a name="to-correct-this-error"></a>Aby poprawić ten błąd

- Usuń wszystkie dodatkowe wystąpienia zmiennej z listy przechwytywania.

## <a name="example"></a>Przykład

Poniższy przykład generuje C3483, ponieważ zmienna `n` występuje więcej niż jeden raz na liście przechwytywania wyrażenia lambda:

```cpp
// C3483.cpp

int main()
{
   int m = 6, n = 5;
   [m,n,n] { return n + m; }(); // C3483
}
```

## <a name="see-also"></a>Zobacz też

[Wyrażenia lambda](../../cpp/lambda-expressions-in-cpp.md)
