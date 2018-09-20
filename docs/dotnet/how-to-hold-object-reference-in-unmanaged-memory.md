---
title: 'Porady: utrzymywanie odwołania do obiektu w pamięci niezarządzanej | Dokumentacja firmy Microsoft'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- object references, in native functions
- objects [C++], reference in native functions
- references, to objects in native functions
- gcroot keyword [C++], object reference in native function
ms.assetid: a61eb8ce-3982-477d-8d3d-2173fd57166d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 3153a34844885e2b753bf68d74b7757c5d11fb1d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/19/2018
ms.locfileid: "46443465"
---
# <a name="how-to-hold-object-reference-in-unmanaged-memory"></a>Porady: utrzymywanie odwołania do obiektu w pamięci niezarządzanej

Możesz użyć gcroot.h, który otacza <xref:System.Runtime.InteropServices.GCHandle>, aby pomieścić odwołanie do obiektu CLR w pamięci niezarządzanej. Alternatywnie, można użyć `GCHandle` bezpośrednio.

## <a name="example"></a>Przykład

```
// hold_object_reference.cpp
// compile with: /clr
#include "gcroot.h"
using namespace System;

#pragma managed
class StringWrapper {

private:
   gcroot<String ^ > x;

public:
   StringWrapper() {
      String ^ str = gcnew String("ManagedString");
      x = str;
   }

   void PrintString() {
      String ^ targetStr = x;
      Console::WriteLine("StringWrapper::x == {0}", targetStr);
   }
};
#pragma unmanaged
int main() {
   StringWrapper s;
   s.PrintString();
}
```

```Output
StringWrapper::x == ManagedString
```

## <a name="example"></a>Przykład

`GCHandle` zapewnia sposób utrzymywanie odwołania do obiektu zarządzanego w niezarządzanej pamięci.  Możesz użyć <xref:System.Runtime.InteropServices.GCHandle.Alloc%2A> metodę w celu utworzenia nieprzezroczyste dojścia do obiektu zarządzanego i <xref:System.Runtime.InteropServices.GCHandle.Free%2A> do jego zwolnienia. Ponadto <xref:System.Runtime.InteropServices.GCHandle.Target%2A> metoda pozwala uzyskać odwołanie do obiektu powrót po awarii z dojście w kodzie zarządzanym.

```
// hold_object_reference_2.cpp
// compile with: /clr
using namespace System;
using namespace System::Runtime::InteropServices;

#pragma managed
class StringWrapper {
   IntPtr m_handle;
public:
   StringWrapper() {
      String ^ str = gcnew String("ManagedString");
      m_handle = static_cast<IntPtr>(GCHandle::Alloc(str));
   }
   ~StringWrapper() {
      static_cast<GCHandle>(m_handle).Free();
   }

   void PrintString() {
      String ^ targetStr = safe_cast< String ^ >(static_cast<GCHandle>(m_handle).Target);
      Console::WriteLine("StringWrapper::m_handle == {0}", targetStr);
   }
};

#pragma unmanaged
int main() {
   StringWrapper s;
   s.PrintString();
}
```

```Output
StringWrapper::m_handle == ManagedString
```

## <a name="see-also"></a>Zobacz też

[Korzystanie z międzyoperacyjności języka C++ (niejawna funkcja PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)