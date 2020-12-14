---
description: 'Dowiedz się więcej na temat: błąd krytyczny C1019'
title: Błąd krytyczny C1019
ms.date: 11/04/2016
f1_keywords:
- C1019
helpviewer_keywords:
- C1019
ms.assetid: c4f8968b-bc62-4200-b3ca-69d06c163236
ms.openlocfilehash: d11a4300b29e497fef2f148d07963997586781ec
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97316391"
---
# <a name="fatal-error-c1019"></a>Błąd krytyczny C1019

nieoczekiwany #else

`#else`Dyrektywa występuje poza `#if` , `#ifdef` , lub `#ifndef` . Używać `#else` tylko w obrębie jednego z tych konstrukcji.

Poniższy przykład generuje C1019:

```cpp
// C1019.cpp
#else   // C1019
#endif

int main() {}
```

Możliwe rozwiązanie:

```cpp
// C1019b.cpp
#if 1
#else
#endif

int main() {}
```
