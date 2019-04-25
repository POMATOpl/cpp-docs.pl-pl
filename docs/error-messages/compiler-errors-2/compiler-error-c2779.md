---
title: Błąd kompilatora C2779
ms.date: 11/04/2016
f1_keywords:
- C2779
helpviewer_keywords:
- C2779
ms.assetid: 4a00e492-855a-41f3-8a18-5f60ee20c2f2
ms.openlocfilehash: 7cf8aed276ab2aea61dc92b9e9fcbff9552c2ad6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/23/2019
ms.locfileid: "62257052"
---
# <a name="compiler-error-c2779"></a>Błąd kompilatora C2779

"deklaracją": metody właściwości mogą być skojarzony tylko z danych niestatycznych elementów członkowskich

`property` Atrybutów rozszerzonych niepoprawnie jest stosowany do składowej danych statycznych.

Poniższy przykład spowoduje wygenerowanie C2779:

```
// C2779.cpp
struct A {
   static __declspec(property(put=PutProp))
   // try the following line instead
   __declspec(property(put=PutProp))
      int prop;   // C2779
   int PutProp(void);
};
```