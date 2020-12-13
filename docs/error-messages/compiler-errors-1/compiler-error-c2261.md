---
description: 'Dowiedz się więcej o: błąd kompilatora C2261'
title: Błąd kompilatora C2261
ms.date: 11/04/2016
f1_keywords:
- C2261
helpviewer_keywords:
- C2261
ms.assetid: 60969482-9e83-49b5-9631-a04bc844da12
ms.openlocfilehash: c5156a240696f9021613b54cf7013e9372a13b45
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97134618"
---
# <a name="compiler-error-c2261"></a>Błąd kompilatora C2261

"String": odwołanie do zestawu jest nieprawidłowe i nie można go rozpoznać

Wartość jest nieprawidłowa.

<xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> służy do określania zaprzyjaźnionego zestawu. Na przykład jeśli a.dll chce określić b.dll jako zestaw zaprzyjaźniony, należy określić (w a.dll): InternalsVisibleTo ("b"). Środowisko uruchomieniowe umożliwi b.dll dostęp do wszystkich elementów a.dll (z wyjątkiem typów prywatnych).

Aby uzyskać więcej informacji na temat poprawnej składni podczas określania zaprzyjaźnionych zestawów, zobacz [zaprzyjaźnione zestawy (C++)](../../dotnet/friend-assemblies-cpp.md).

## <a name="example"></a>Przykład

Poniższy przykład generuje C2261.

```cpp
// C2261.cpp
// compile with: /clr /c
using namespace System::Runtime::CompilerServices;
[assembly: InternalsVisibleTo("a,a,a")];   // C2261
[assembly: InternalsVisibleTo("a.a")];   // OK
[assembly: InternalsVisibleTo("a")];   // OK
```
