---
description: 'Dowiedz się więcej o: błąd kompilatora C2482'
title: Błąd kompilatora C2482
ms.date: 09/15/2017
f1_keywords:
- C2482
helpviewer_keywords:
- C2482
ms.assetid: 98c87da2-625c-4cc2-9bf7-78d15921e779
ms.openlocfilehash: 1ffde4d7ea9f4eccdd643b3ac6efe0545775816a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97123932"
---
# <a name="compiler-error-c2482"></a>Błąd kompilatora C2482

>"*Identyfikator*": dynamiczna inicjalizacja danych "Thread" jest niedozwolona w kodzie zarządzanym/WinRT

## <a name="remarks"></a>Uwagi

W kodzie zarządzanym lub WinRT zmienne zadeklarowane przy użyciu atrybutu modyfikatora klasy magazynu [__declspec (wątku)](../../cpp/thread.md) lub [thread_localgo](../../cpp/storage-classes-cpp.md#thread_local) specyfikatora klasy magazynu nie mogą zostać zainicjowane przy użyciu wyrażenia wymagającego oceny w czasie wykonywania. Do inicjowania `__declspec(thread)` lub **`thread_local`** danych w tych środowiskach uruchomieniowych jest wymagane wyrażenie statyczne.

## <a name="example"></a>Przykład

Poniższy przykład generuje C2482 w kodzie Managed (**/CLR**) i in WinRT (**/zw**):

```cpp
// C2482.cpp
// For managed example, compile with: cl /EHsc /c /clr C2482.cpp
// For WinRT example, compile with: cl /EHsc /c /ZW C2482.cpp
#define Thread __declspec( thread )
Thread int tls_i1 = tls_i1;   // C2482

int j = j;   // OK in C++; C error
Thread int tls_i2 = sizeof( tls_i2 );   // Okay in C and C++
```

Aby rozwiązać ten problem, zainicjuj lokalne przechowywanie wątków przy użyciu stałego **`constexpr`** lub statycznego wyrażenia. Wykonaj osobno każdą inicjalizację specyficzną dla wątku.
