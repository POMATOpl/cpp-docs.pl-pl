---
description: 'Dowiedz się więcej na temat: błąd krytyczny C1308'
title: Błąd krytyczny C1308
ms.date: 11/04/2016
f1_keywords:
- C1308
helpviewer_keywords:
- C1308
ms.assetid: 46177997-069e-433a-8e20-93c846d78ffd
ms.openlocfilehash: 9d9b8cee128b9ed830c4ba3651ee609d91d42eac
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97177877"
---
# <a name="fatal-error-c1308"></a>Błąd krytyczny C1308

Łączenie zestawów nie jest obsługiwane

Element. webmodule jest dozwolony jako dane wejściowe dla konsolidatora, ale zestaw nie jest. Ten błąd może zostać wygenerowany, gdy zostanie podjęta próba połączenia zestawu skompilowanego z `/clr:safe` .

Aby uzyskać więcej informacji, zobacz [. moduły plików jako dane wejściowe konsolidatora](../../build/reference/netmodule-files-as-linker-input.md).

Poniższy przykład generuje C1308:

```cpp
// C1308.cpp
// compile with: /clr:safe /LD
public ref class MyClass {
public:
   int i;
};
```

a następnie

```cpp
// C1308b.cpp
// compile with: /clr /link C1308b.obj C1308.dll
// C1308 expected
#using "C1308.dll"
int main() {
   MyClass ^ my = gcnew MyClass();
}
```
