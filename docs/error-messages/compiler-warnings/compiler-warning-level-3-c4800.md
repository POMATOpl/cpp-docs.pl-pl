---
title: Ostrzeżenie kompilatora (poziom 4) C4800
ms.date: 03/14/2019
f1_keywords:
- C4800
helpviewer_keywords:
- C4800
ms.assetid: 4f409799-a250-45ed-bb5f-657691b0d9f7
ms.openlocfilehash: bcc98b9bb24f77e39a31332b8fbe2f7dcc5a7638
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2020
ms.locfileid: "92924612"
---
# <a name="compiler-warning-level-4-c4800"></a>Ostrzeżenie kompilatora (poziom 4) C4800

::: moniker range=">= msvc-160"
Program Visual Studio 2019 lub nowszy:
> Niejawna konwersja z *typu "Type* " na typ bool. Możliwa utrata informacji
::: moniker-end

C4800 to ostrzeżenie poziomu 3 w programie Visual Studio 2015 i jego wcześniejszych wersjach:
> " *Type* ": wymuszanie wartości logicznej "true" lub "false" (ostrzeżenie o wydajności)

To ostrzeżenie jest generowane, gdy wartość jest niejawnie konwertowana na typ **`bool`** . Zazwyczaj ten komunikat jest spowodowany przypisaniem **`int`** zmiennych do zmiennych, w **`bool`** których **`int`** zmienna zawiera tylko wartości **`true`** i **`false`** i może być ponownie zadeklarowana jako typ **`bool`** . Jeśli nie możesz ponownie zapisać wyrażenia w celu użycia typu **`bool`** , możesz dodać " `!=0` " do wyrażenia, które zwraca typ wyrażenia **`bool`** . Rzutowanie wyrażenia do typu **`bool`** nie powoduje wyłączenia ostrzeżenia, które jest zgodne z projektem.

::: moniker range=">= msvc-150"
To ostrzeżenie nie jest emitowane w programie Visual Studio 2017.
::: moniker-end

::: moniker range=">= msvc-160"
To ostrzeżenie jest domyślnie wyłączone w programie Visual Studio 2019. Użyj __/w__*n*__4800__ , aby włączyć C4800 jako poziom *n* ostrzeżenie lub [/Wall](../../build/reference/compiler-option-warning-level.md) , aby włączyć wszystkie ostrzeżenia, które są domyślnie wyłączone. Aby uzyskać więcej informacji, zobacz [ostrzeżenia kompilatora, które są domyślnie wyłączone](../../preprocessor/compiler-warnings-that-are-off-by-default.md).
::: moniker-end

## <a name="example"></a>Przykład

Poniższy przykład generuje C4800 i pokazuje, jak to naprawić:

```cpp
// C4800.cpp
// compile with: /W4 /w44800
int main() {
   int i = 0;

   // To fix, instead try:
   // bool i = 0;

   bool j = i;   // C4800
   j++;
}
```
