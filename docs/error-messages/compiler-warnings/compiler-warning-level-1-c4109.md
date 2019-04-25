---
title: Kompilator ostrzeżenie (poziom 1) C4109
ms.date: 11/04/2016
f1_keywords:
- C4109
helpviewer_keywords:
- C4109
ms.assetid: 9e8d95c6-e05d-47e0-bd87-78974b3cc06c
ms.openlocfilehash: 1156bbfbed7aed9524b24b046b9ce9acdbdc8b8a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/23/2019
ms.locfileid: "62300209"
---
# <a name="compiler-warning-level-1-c4109"></a>Kompilator ostrzeżenie (poziom 1) C4109

Nieoczekiwany identyfikator 'Identyfikator'

Dyrektywy, nieoczekiwany identyfikator zawierające jest ignorowany.

## <a name="example"></a>Przykład

```
// C4109.cpp
// compile with: /W1 /LD
#pragma init_seg( abc ) // C4109
```