---
description: 'Dowiedz się więcej o: błąd kompilatora C3808'
title: Błąd kompilatora C3808
ms.date: 11/04/2016
f1_keywords:
- C3808
helpviewer_keywords:
- C3808
ms.assetid: 2ee8ac97-3ea4-417a-8710-be73a7f98cf4
ms.openlocfilehash: e5d31e884de0b04caba7c52e8d6abc01b3d21a35
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97315156"
---
# <a name="compiler-error-c3808"></a>Błąd kompilatora C3808

> "*Type*": Klasa o atrybucie atrybutem ComImport nie może definiować składowej "*member*", dozwolone są tylko funkcje abstrakcyjne lub dllimport

## <a name="remarks"></a>Uwagi

Typ pochodzący od <xref:System.Runtime.InteropServices.ComImportAttribute> nie może definiować *elementu członkowskiego*.

**/CLR: Pure** i **/CLR:** opcje kompilatora bezpiecznego są przestarzałe w programie Visual Studio 2015 i nieobsługiwane w programie Visual Studio 2017.

## <a name="example"></a>Przykład

Poniższy przykład generuje C3808.

```cpp
// C3808.cpp
// compile with: /c /clr:pure user32.lib
using namespace System::Runtime::InteropServices;

[System::Runtime::InteropServices::ComImportAttribute()]
ref struct S1 {
   int f() {}   // C3808
   virtual int g() abstract;   // OK

   [DllImport("msvcrt.dll")]
   int printf(System::String ^, int i);   // OK
};
```
