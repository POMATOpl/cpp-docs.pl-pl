---
description: 'Dowiedz się więcej na temat: błąd krytyczny C1020'
title: Błąd krytyczny C1020
ms.date: 11/04/2016
f1_keywords:
- C1020
helpviewer_keywords:
- C1020
ms.assetid: 42f429e2-5e3b-4086-a10d-b99e032e51c5
ms.openlocfilehash: 444da85bddf65533eb5ae37278085664efeae7ee
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97316365"
---
# <a name="fatal-error-c1020"></a>Błąd krytyczny C1020

nieoczekiwany #endif

`#endif`Dyrektywa nie ma zgodnej `#if` `#ifdef` dyrektywy, lub `#ifndef` . Upewnij się, że każda `#endif` z nich ma pasującą dyrektywę.

Poniższy przykład generuje C1020:

```cpp
// C1020.cpp
#endif     // C1020
```

Możliwe rozwiązanie:

```cpp
// C1020b.cpp
// compile with: /c
#if 1
#endif
```
