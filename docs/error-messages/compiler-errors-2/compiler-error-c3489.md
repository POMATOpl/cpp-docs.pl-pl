---
description: 'Dowiedz się więcej o: błąd kompilatora C3489'
title: Błąd kompilatora C3489
ms.date: 11/04/2016
f1_keywords:
- C3489
helpviewer_keywords:
- C3489
ms.assetid: 47b58d69-459d-4499-abc7-5f0b9303d773
ms.openlocfilehash: 658fc83476a9fe6f0db3ac27f44a05e1cb1d0c28
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97315649"
---
# <a name="compiler-error-c3489"></a>Błąd kompilatora C3489

element "var" jest wymagany, gdy domyślny tryb przechwytywania jest przez wartość

Po określeniu, że domyślny tryb przechwytywania dla wyrażenia lambda jest przez wartość, nie można przekazać zmiennej przez wartość do klauzuli przechwytywania tego wyrażenia.

### <a name="to-correct-this-error"></a>Aby poprawić ten błąd

- Nie przekazuj jawnie zmiennej do klauzuli Capture lub

- Nie określaj według wartości jako domyślnego trybu przechwytywania ani

- Określ jako domyślny tryb przechwytywania, lub

- Przekaż zmienną przez odwołanie do klauzuli Capture. (Może to spowodować zmianę zachowania wyrażenia lambda).

## <a name="examples"></a>Przykłady

Poniższy przykład generuje zmienną C3489 `n` , która jest wyświetlana przez wartość w klauzuli Capture wyrażenia lambda, którego tryb domyślny ma wartość:

```cpp
// C3489a.cpp

int main()
{
   int n = 5;
   [=, n]() { return n; } (); // C3489
}
```

W poniższym przykładzie przedstawiono cztery możliwe rozwiązania C3489:

```cpp
// C3489b.cpp

int main()
{
   int n = 5;

   // Possible resolution 1:
   // Do not explicitly pass n to the capture clause.
   [=]() { return n; } ();

   // Possible resolution 2:
   // Do not specify by-value as the default capture mode.
   [n]() { return n; } ();

   // Possible resolution 3:
   // Specify by-reference as the default capture mode.
   [&, n]() { return n; } ();

   // Possible resolution 4:
   // Pass n by reference to the capture clause.
   [&n]() { return n; } ();
}
```

## <a name="see-also"></a>Zobacz też

[Wyrażenia lambda](../../cpp/lambda-expressions-in-cpp.md)
