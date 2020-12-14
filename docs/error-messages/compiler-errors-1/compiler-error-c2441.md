---
description: 'Dowiedz się więcej o: błąd kompilatora C2441'
title: Błąd kompilatora C2441
ms.date: 11/04/2016
f1_keywords:
- C2441
helpviewer_keywords:
- C2441
ms.assetid: ffbd6573-777a-48dd-892f-5cf4a758dcab
ms.openlocfilehash: d7a6073be821fcd2717caae258c5b3f397fb3f87
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97189733"
---
# <a name="compiler-error-c2441"></a>Błąd kompilatora C2441

> "*zmienna*": symbol zadeklarowany z __declspec (Process) musi być stały w/CLR: Pure Mode

## <a name="remarks"></a>Uwagi

**/CLR: Pure** i **/CLR:** opcje kompilatora bezpiecznego są przestarzałe w programie Visual Studio 2015 i nieobsługiwane w programie Visual Studio 2017.

Domyślnie zmienne są dla domeny aplikacji w ramach opcji **/CLR: Pure**. Zmienna oznaczona jako `__declspec(process)` **/CLR: Pure** jest podatna na błędy w przypadku zmodyfikowania w jednej domenie aplikacji i odczytania w innej.

W związku z tym kompilator wymusza na zmienne procesów **`const`** w obszarze **/CLR: Pure**, co sprawia, że są one odczytane tylko we wszystkich domenach aplikacji.

Aby uzyskać więcej informacji, zobacz [proces](../../cpp/process.md) i [/CLR (Kompilacja środowiska uruchomieniowego języka wspólnego)](../../build/reference/clr-common-language-runtime-compilation.md).

## <a name="example"></a>Przykład

Poniższy przykład generuje C2441.

```cpp
// C2441.cpp
// compile with: /clr:pure /c
__declspec(process) int i;   // C2441
__declspec(process) const int j = 0;   // OK
```
