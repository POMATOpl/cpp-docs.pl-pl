---
title: Błąd krytyczny C1308
ms.date: 11/04/2016
f1_keywords:
- C1308
helpviewer_keywords:
- C1308
ms.assetid: 46177997-069e-433a-8e20-93c846d78ffd
ms.openlocfilehash: 0128953b3b3fa0f29a6764c1d7dab0ece67dfae7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/23/2019
ms.locfileid: "62266520"
---
# <a name="fatal-error-c1308"></a>Błąd krytyczny C1308

Łączenie zestawów nie jest obsługiwana.

.Netmodule jest dozwolona jako dane wejściowe do konsolidatora, ale zestaw nie jest. Ten błąd może zostać wygenerowany, gdy podejmowana jest próba połączyć zestawu skompilowanego z `/clr:safe`.

Aby uzyskać więcej informacji, zobacz [pliki .netmodule — wejście konsolidatora](../../build/reference/netmodule-files-as-linker-input.md).

Poniższy przykład spowoduje wygenerowanie C1308:

```
// C1308.cpp
// compile with: /clr:safe /LD
public ref class MyClass {
public:
   int i;
};
```

Następnie wyszukaj maszynę

```
// C1308b.cpp
// compile with: /clr /link C1308b.obj C1308.dll
// C1308 expected
#using "C1308.dll"
int main() {
   MyClass ^ my = gcnew MyClass();
}
```