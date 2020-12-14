---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4397'
title: Ostrzeżenie kompilatora (poziom 1) C4397
ms.date: 11/04/2016
f1_keywords:
- C4397
helpviewer_keywords:
- C4397
ms.assetid: 6346fdc2-dbbf-4fba-803a-32b0d0a707be
ms.openlocfilehash: 17ad322980a199b9602c4aa1ea60d818e657eaa1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97311256"
---
# <a name="compiler-warning-level-1-c4397"></a>Ostrzeżenie kompilatora (poziom 1) C4397

DefaultCharSetAttribute jest ignorowany

<xref:System.Runtime.InteropServices.DefaultCharSetAttribute> jest ignorowany przez kompilator języka Microsoft C++. Aby określić zestaw znaków dla biblioteki DLL, użyj opcji CharSet elementu DllImport. Aby uzyskać więcej informacji, zobacz [using C++ Interop (niejawne PInvoke)](../../dotnet/using-cpp-interop-implicit-pinvoke.md).

## <a name="example"></a>Przykład

Poniższy przykład generuje C4397.

```cpp
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
