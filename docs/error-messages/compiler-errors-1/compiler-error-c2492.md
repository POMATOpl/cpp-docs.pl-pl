---
description: 'Dowiedz się więcej o: błąd kompilatora C2492'
title: Błąd kompilatora C2492
ms.date: 11/04/2016
f1_keywords:
- C2492
helpviewer_keywords:
- C2492
ms.assetid: 8c44c9bb-c366-4fe5-a0ab-882e38608aaa
ms.openlocfilehash: ef31b2136a2cfc0422832899dba14ffb3108d965
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97283680"
---
# <a name="compiler-error-c2492"></a>Błąd kompilatora C2492

"*zmienna*": dane z czasem trwania magazynu wątku mogą nie mieć interfejsu biblioteki DLL

Zmienna jest zadeklarowana przy użyciu atrybutu [Thread](../../cpp/thread.md) i z interfejsem dll. Adres `thread` zmiennej nie jest znany do czasu uruchomienia, dlatego nie można go połączyć z importem lub eksportem biblioteki DLL.

Poniższy przykład generuje C2492:

```cpp
// C2492.cpp
// compile with: /c
class C {
public:
   char   ch;
};

__declspec(dllexport) __declspec(thread) C c_1;   // C2492
__declspec(thread) C c_1;   // OK
```
