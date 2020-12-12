---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 3) C4792'
title: Ostrzeżenie kompilatora (poziom 3) C4792
ms.date: 11/04/2016
f1_keywords:
- C4792
helpviewer_keywords:
- C4792
ms.assetid: c047ce69-a622-44e1-9425-d41aa9261c61
ms.openlocfilehash: 37dc805477e3150eedaffe7eb5d900b7903b1d48
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97332130"
---
# <a name="compiler-warning-level-3-c4792"></a>Ostrzeżenie kompilatora (poziom 3) C4792

Funkcja "Function" została zadeklarowana przy użyciu SysImport i przywoływana z kodu natywnego; Biblioteka importowana wymagana do konsolidacji

Funkcja natywna zaimportowana do programu z elementem DllImport została wywołana z funkcji niezarządzanej. W związku z tym należy połączyć się z biblioteką importu biblioteki DLL.

Tego ostrzeżenia nie można rozpoznać w kodzie lub poprzez zmianę sposobu kompilowania. Aby wyłączyć to ostrzeżenie, użyj dyrektywy pragma [ostrzeżenia](../../preprocessor/warning.md) .

Poniższy przykład generuje C4792:

```cpp
// C4792.cpp
// compile with: /clr /W3
// C4792 expected
using namespace System::Runtime::InteropServices;
[DllImport("msvcrt")]
extern "C" int __cdecl puts(const char *);
int main() {}

// Uncomment the following line to resolve.
// #pragma warning(disable : 4792)
#pragma unmanaged
void func(void){
   puts("test");
}
```
