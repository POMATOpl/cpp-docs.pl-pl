---
description: 'Dowiedz się więcej na temat: błąd krytyczny C1103'
title: Błąd krytyczny C1103
ms.date: 11/04/2016
f1_keywords:
- C1103
helpviewer_keywords:
- C1103
ms.assetid: 9d276939-9c47-4235-9d20-76b8434f9731
ms.openlocfilehash: 7e49d4f4420fc202f54a580c194244d24a4d181c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97144927"
---
# <a name="fatal-error-c1103"></a>Błąd krytyczny C1103

Błąd krytyczny podczas importowania identyfikatora ProgID: "Message"

Kompilator wykrył problem podczas importowania biblioteki typów.  Na przykład nie można określić biblioteki typów z identyfikatorem ProgID, a także określić `no_registry` .

Aby uzyskać więcej informacji, zobacz [#import dyrektywie](../../preprocessor/hash-import-directive-cpp.md).

Poniższy przykład generuje C1103:

```cpp
// C1103.cpp
#import "progid:a.b.id.1.5" no_registry auto_search   // C1103
```
