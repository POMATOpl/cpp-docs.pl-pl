---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4794'
title: Ostrzeżenie kompilatora (poziom 1) C4794
ms.date: 11/04/2016
f1_keywords:
- C4794
helpviewer_keywords:
- C4794
ms.assetid: badc9c36-fa1a-4fec-929b-7bfda7a7b79f
ms.openlocfilehash: bd43a9fb1f7f2433a4e1d337d49c1921211a9e5d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334950"
---
# <a name="compiler-warning-level-1-c4794"></a>Ostrzeżenie kompilatora (poziom 1) C4794

segment zmiennej lokalnego magazynu wątku "variable" został zmieniony z "Nazwa sekcji" na ". TLS $"

Użyto [#pragma data_seg](../../preprocessor/data-seg.md) , aby umieścić zmienną TLS w sekcji, która nie zaczyna się od. TLS $.

Sekcja. TLS $*x* będzie istnieć w pliku obiektu, w którym zdefiniowano zmienne [__declspec (wątku)](../../cpp/thread.md) . Sekcja. TLS w pliku EXE lub DLL będzie wynikać z tych sekcji.

## <a name="example"></a>Przykład

Poniższy przykład generuje C4794:

```cpp
// C4794.cpp
// compile with: /W1 /c
#pragma data_seg(".someseg")
__declspec(thread) int i;   // C4794

// OK
#pragma data_seg(".tls$9")
__declspec(thread) int j;
```
