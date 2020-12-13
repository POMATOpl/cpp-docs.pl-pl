---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4612'
title: Ostrzeżenie kompilatora (poziom 1) C4612
ms.date: 08/27/2018
f1_keywords:
- C4612
helpviewer_keywords:
- C4612
ms.assetid: 21ac02b2-51cd-4aff-9b70-d543511d5962
ms.openlocfilehash: 2844b54c592f5c4c4817cfec97d57c41fa2055b1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341727"
---
# <a name="compiler-warning-level-1-c4612"></a>Ostrzeżenie kompilatora (poziom 1) C4612

> błąd w nazwie pliku dołączanego

## <a name="remarks"></a>Uwagi

To ostrzeżenie występuje **#pragma include_alias** , gdy nazwa pliku jest nieprawidłowa lub nie została podana.

Argumenty do instrukcji **#pragma include_alias** mogą używać formularza cudzysłowu ("*filename*") lub nawiasu kwadratowego ( \<*filename*> ), ale oba muszą używać tego samego formularza.

## <a name="example"></a>Przykład

```cpp
// C4612.cpp
// compile with: /W1 /LD
#pragma include_alias("StandardIO", <stdio.h>) // C4612
```
