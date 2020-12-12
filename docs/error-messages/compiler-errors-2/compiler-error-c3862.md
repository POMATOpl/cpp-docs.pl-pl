---
description: 'Dowiedz się więcej o: błąd kompilatora C3862'
title: Błąd kompilatora C3862
ms.date: 11/04/2016
f1_keywords:
- C3862
helpviewer_keywords:
- C3862
ms.assetid: ba547366-4189-4077-8c00-ab45e08a9533
ms.openlocfilehash: b8955a69bcd04c0a40aed8fab722c6c734bfa65b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97222895"
---
# <a name="compiler-error-c3862"></a>Błąd kompilatora C3862

> "*Function*": nie można skompilować niezarządzanej funkcji z/CLR: Pure lub/CLR: Safe

## <a name="remarks"></a>Uwagi

**/CLR: Pure** i **/CLR:** opcje kompilatora bezpiecznego są przestarzałe w programie Visual Studio 2015 i nieobsługiwane w programie Visual Studio 2017.

Kompilacja z **/CLR: Pure** lub **/CLR: Safe** spowoduje wygenerowanie obrazu tylko MSIL, obrazu bez kodu natywnego (niezarządzanego).  W związku z tym nie można używać `unmanaged` dyrektywy pragma w kompilacji **/CLR: Pure** lub **/CLR: Safe** .

Aby uzyskać więcej informacji, zobacz [/CLR (Kompilacja środowiska uruchomieniowego języka wspólnego)](../../build/reference/clr-common-language-runtime-compilation.md) i [zarządzana, niezarządzana](../../preprocessor/managed-unmanaged.md).

## <a name="example"></a>Przykład

Poniższy przykład generuje C3862:

```cpp
// C3862.cpp
// compile with: /clr:pure /c
#pragma unmanaged
void f() {}   // C3862
```
