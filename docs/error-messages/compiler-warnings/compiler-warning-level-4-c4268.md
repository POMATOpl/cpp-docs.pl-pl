---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 4) C4268'
title: Ostrzeżenie kompilatora (poziom 4) C4268
ms.date: 11/04/2016
f1_keywords:
- C4268
helpviewer_keywords:
- C4268
ms.assetid: d0511e80-904f-4ee1-b4d7-39b5c0bd8234
ms.openlocfilehash: 50e4a2afd577653fa14ae5d663f2b00fa95670b5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97294668"
---
# <a name="compiler-warning-level-4-c4268"></a>Ostrzeżenie kompilatora (poziom 4) C4268

"Identyfikator": "const" dane statyczne/globalne zainicjowane przy użyciu konstruktora domyślnego wygenerowanego przez kompilator wypełniają obiekt zerami

**`const`** Globalne lub statyczne wystąpienie klasy nieuproszczonej jest inicjowane za pomocą domyślnego konstruktora wygenerowanego przez kompilator.

## <a name="example"></a>Przykład

```cpp
// C4268.cpp
// compile with: /c /LD /W4
class X {
public:
   int m_data;
};

const X x1;   // C4268
```

Ponieważ to wystąpienie klasy ma **`const`** wartość, `m_data` nie można zmienić wartości.
