---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4230'
title: Ostrzeżenie kompilatora (poziom 1) C4230
ms.date: 11/04/2016
f1_keywords:
- C4230
helpviewer_keywords:
- C4230
ms.assetid: a4be8729-74b6-44df-a5ea-e3f45aad0f8f
ms.openlocfilehash: b5427d4ab87a1ba1c65456dab379f76100e75fea
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97266291"
---
# <a name="compiler-warning-level-1-c4230"></a>Ostrzeżenie kompilatora (poziom 1) C4230

anachronizm użyte: Modyfikatory/kwalifikatory przeplatane; kwalifikator został zignorowany

Użycie kwalifikatora przed modyfikatorem firmy Microsoft, takim jak **`__cdecl`** jest nieaktualne.

## <a name="example"></a>Przykład

```cpp
// C4230.cpp
// compile with: /W1 /LD
int __cdecl const function1();   // C4230 const ignored
```
