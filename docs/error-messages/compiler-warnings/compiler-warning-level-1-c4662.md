---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4662'
title: Ostrzeżenie kompilatora (poziom 1) C4662
ms.date: 11/04/2016
f1_keywords:
- C4662
helpviewer_keywords:
- C4662
ms.assetid: 7efda273-d04a-47b7-ad65-ff1ff94b5ffc
ms.openlocfilehash: 60de9a5f5f4a70fc80eff5322a4757571efd5902
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97318770"
---
# <a name="compiler-warning-level-1-c4662"></a>Ostrzeżenie kompilatora (poziom 1) C4662

jawne utworzenie wystąpienia; Klasa szablonu "Identifier1" nie ma definicji, z której można specjalizacji "identifier2"

Określona Klasa szablonu została zadeklarowana, ale nie została zdefiniowana.

## <a name="example"></a>Przykład

```cpp
// C4662.cpp
// compile with: /W1 /LD
template<class T, int i> class MyClass; // no definition
template MyClass< int, 1>;              // C4662
```
