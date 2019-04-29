---
title: Kompilator ostrzeżenie (poziom 1) C4397
ms.date: 11/04/2016
f1_keywords:
- C4397
helpviewer_keywords:
- C4397
ms.assetid: 6346fdc2-dbbf-4fba-803a-32b0d0a707be
ms.openlocfilehash: 4ad690d78c1544adbe365a35ba3b5921c883631e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/23/2019
ms.locfileid: "62365393"
---
# <a name="compiler-warning-level-1-c4397"></a>Kompilator ostrzeżenie (poziom 1) C4397

DefaultCharSetAttribute jest ignorowany

<xref:System.Runtime.InteropServices.DefaultCharSetAttribute> jest ignorowane przez kompilator języka Visual C++. Aby określić zestaw znaków dla biblioteki DLL, użyj opcji CharSet elementu DllImport. Aby uzyskać więcej informacji, zobacz [za pomocą międzyoperacyjności języka C++ (niejawna funkcja PInvoke)](../../dotnet/using-cpp-interop-implicit-pinvoke.md).

## <a name="example"></a>Przykład

Poniższy przykład spowoduje wygenerowanie C4397.

```
// C4397.cpp
// compile with: /W1 /c /clr
using namespace System;
using namespace System::Runtime::InteropServices;

[module:DefaultCharSetAttribute(CharSet::Unicode)];   // C4397

[DllImport("kernel32", EntryPoint="CloseHandle", CharSet=CharSet::Unicode)]   // OK
extern "C" bool ImportDefault(IntPtr hObject);

public ref class MySettingVC {
public:
   void method() {
      ImportDefault(IntPtr::Zero);
   }
};

[StructLayout(LayoutKind::Explicit)]
public ref struct StructDefault1{};

public ref class ClassDefault1{};
```