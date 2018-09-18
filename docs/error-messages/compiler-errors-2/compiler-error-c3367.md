---
title: Błąd kompilatora C3367 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3367
dev_langs:
- C++
helpviewer_keywords:
- C3367
ms.assetid: e675d42b-f5b0-4d43-aab1-1f5024233102
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2e063635e521efe1eabf8f2b50664ef8bf3e85e8
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/18/2018
ms.locfileid: "46020235"
---
# <a name="compiler-error-c3367"></a>Błąd kompilatora C3367

"static_member_function": nie można użyć statycznej funkcji by utworzyć niezwiązanego delegata

Jeśli chcesz wywołać niezwiązanego delegata, należy przekazać wystąpienia obiektu. Ponieważ funkcja statycznej składowej jest wywoływana za pośrednictwem nazwy klasy, można tylko utworzyć wystąpienie niezwiązanego delegata z funkcję składową wystąpienia.

Aby uzyskać więcej informacji na temat niezwiązane obiekty delegowane, zobacz [porady: definiowanie i użycie delegatów (C + +/ interfejsu wiersza polecenia)](../../dotnet/how-to-define-and-use-delegates-cpp-cli.md).

## <a name="example"></a>Przykład

Poniższy przykład spowoduje wygenerowanie C3367.

```cpp
// C3367.cpp
// compile with: /clr
ref struct R {
   void b() {}
   static void f() {}
};

delegate void Del(R^);

int main() {
   Del ^ a = gcnew Del(&R::b);   // OK
   Del ^ b = gcnew Del(&R::f);   // C3367
}
```