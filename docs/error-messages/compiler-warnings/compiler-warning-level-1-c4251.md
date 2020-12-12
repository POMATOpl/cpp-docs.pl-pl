---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4251'
title: Ostrzeżenie kompilatora (poziom 1) C4251
ms.date: 04/21/2020
f1_keywords:
- C4251
helpviewer_keywords:
- C4251
ms.assetid: a9992038-f0c2-4fc4-a9be-4509442cbc1e
ms.openlocfilehash: 4d08462442fd64ebef85573f5d538d6a884c8131
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97266237"
---
# <a name="compiler-warning-level-1-c4251"></a>Ostrzeżenie kompilatora (poziom 1) C4251

> "*Type*": Klasa "*Type1*" musi mieć interfejs dll, który ma być używany przez klientów klasy "*Type2*"

## <a name="remarks"></a>Uwagi

Aby zminimalizować prawdopodobieństwo uszkodzenia danych podczas eksportowania klasy zadeklarowanej jako [__declspec (dllexport)](../../cpp/dllexport-dllimport.md), upewnij się, że:

- Do wszystkich danych statycznych uzyskuje się dostęp za pośrednictwem funkcji wyeksportowanych z biblioteki DLL.

- Żadna z nieliniowych metod klasy nie może modyfikować danych statycznych.

- Żadna z nieliniowych metod klasy używa funkcji CRT lub innych funkcji biblioteki, które używają danych statycznych. Aby uzyskać więcej informacji, zobacz [potencjalne błędy podczas przekazywania obiektów CRT między granicami bibliotek DLL](../../c-runtime-library/potential-errors-passing-crt-objects-across-dll-boundaries.md).

- Brak metod klasy (bez pokreślenia lub nie) może używać typów, w których wystąpienia w EXE i DLL mają statyczne różnice danych.

Podczas eksportowania klasy z biblioteki DLL można uniknąć problemów: Zdefiniuj klasę tak, aby zawierała funkcje wirtualne, oraz funkcje do tworzenia wystąpień i usuwania obiektów typu. Następnie można wywołać funkcje wirtualne w typie.

C4251 można zignorować, jeśli klasa pochodzi od typu w standardowej bibliotece języka C++, zostanie skompilowane wydanie debugowania (**/MTD**) i miejsce, do którego odwołuje się komunikat o błędzie kompilatora `_Container_base` .

## <a name="example"></a>Przykład

Ten przykład eksportuje wyspecjalizowaną klasę `VecWrapper` pochodną `std::vector` .

```cpp
// C4251.cpp
// compile with: /EHsc /MTd /W2 /c
#include <vector>
using namespace std;
class Node;
class __declspec(dllexport) VecWrapper : vector<Node *> {};   // C4251
```
