---
description: 'Dowiedz się więcej o: NoLine'
title: noinline
ms.date: 11/04/2016
f1_keywords:
- noinline_cpp
helpviewer_keywords:
- noinline __declspec keyword
- __declspec keyword [C++], noinline
ms.assetid: f259d55b-dec7-4bde-8cf9-14521e4fdc42
ms.openlocfilehash: bc1241307e143a2de81cc99e6a934c83dcf89d23
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97195388"
---
# <a name="noinline"></a>noinline

**Specyficzne dla firmy Microsoft**

**`__declspec(noinline)`** instruuje kompilator, aby nigdy nie wbudowanł określonej funkcji elementu członkowskiego (funkcja w klasie).

Może być wartościowa niewbudowaną funkcję, jeśli jest ona mała i nie ma znaczenia dla wydajności kodu. Oznacza to, że jeśli funkcja jest mała i prawdopodobnie nie jest często wywoływana, na przykład funkcja, która obsługuje warunek błędu.

Należy pamiętać, że jeśli funkcja jest oznaczona **`noinline`** , funkcja wywołująca będzie mniejsza i w ten sposób sama jest kandydatem do dekreślenia kompilatora.

```cpp
class X {
   __declspec(noinline) int mbrfunc() {
      return 0;
   }   // will not inline
};
```

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[__declspec](../cpp/declspec.md)<br/>
[Słowa kluczowe](../cpp/keywords-cpp.md)<br/>
[inline, __inline, \_ _forceinline](inline-functions-cpp.md)
