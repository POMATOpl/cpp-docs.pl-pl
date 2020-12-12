---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 2) C4099'
title: Ostrzeżenie kompilatora (poziom 2) C4099
ms.date: 11/04/2016
f1_keywords:
- C4099
helpviewer_keywords:
- C4099
ms.assetid: 00bb803d-cae7-4ab8-8969-b46f54139ac8
ms.openlocfilehash: c35ce10560ca81f9457f6a21c4c55d96996e7645
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97326520"
---
# <a name="compiler-warning-level-2-c4099"></a>Ostrzeżenie kompilatora (poziom 2) C4099

"Identyfikator": nazwa typu najpierw widoczna przy użyciu "objecttype1" jest teraz widoczna przy użyciu "objecttype2"

Obiekt zadeklarowany jako struktura jest zdefiniowany jako Klasa lub obiekt zadeklarowany jako klasa jest zdefiniowany jako struktura. Kompilator używa typu podanego w definicji.

## <a name="example"></a>Przykład

Poniższy przykład generuje C4099.

```cpp
// C4099.cpp
// compile with: /W2 /c
struct A;
class A {};   // C4099, use different identifer or use same object type
```
