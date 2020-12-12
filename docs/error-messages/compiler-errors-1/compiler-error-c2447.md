---
description: 'Dowiedz się więcej o: błąd kompilatora C2447'
title: Błąd kompilatora C2447
ms.date: 11/04/2016
f1_keywords:
- C2447
helpviewer_keywords:
- C2447
ms.assetid: d1bd6e9a-ee42-4510-ae5e-6b0378f7b931
ms.openlocfilehash: c27846b002b3b58e3ed2e1dd89c06565b32d49b8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97189655"
---
# <a name="compiler-error-c2447"></a>Błąd kompilatora C2447

'{': brak nagłówka funkcji (stary styl listy formalnej)?

Kompilator napotkał nieoczekiwany otwierający nawias klamrowy w zakresie globalnym. W większości przypadków jest to spowodowane przez nieprawidłowo sformułowany nagłówek funkcji, deklarację umieszczoną w złym miejscu lub zabłąkany średnik. Aby rozwiązać ten problem, sprawdź, czy otwierający nawias klamrowy następuje po poprawnie sformułowanym nagłówku funkcji i nie jest poprzedzony przez deklarację lub zabłąkany średnik.

Ten błąd może być też spowodowany listą argumentów formalnych języka C w starym stylu. Aby rozwiązać ten problem, zreorganizuj listę argumentów, aby używała stylu nowoczesnego — to znaczy ujętego w nawiasy.

Poniższy przykład generuje C2447:

```cpp
// C2447.cpp
int c;
{}       // C2447
```
