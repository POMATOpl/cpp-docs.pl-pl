---
description: 'Dowiedz się więcej o: błąd kompilatora C3451'
title: Błąd kompilatora C3451
ms.date: 11/04/2016
f1_keywords:
- C3451
helpviewer_keywords:
- C3451
ms.assetid: a4897a69-e3e7-40bb-bb1c-598644904012
ms.openlocfilehash: a5cc37bf273474553c375edc940d160f0c1d023d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97316013"
---
# <a name="compiler-error-c3451"></a>Błąd kompilatora C3451

"Attribute": nie można zastosować niezarządzanego atrybutu do "Type"

Nie można zastosować atrybutu języka C++ do typu CLR. Aby uzyskać więcej informacji, zobacz [odwołania do atrybutów C++](../../windows/attributes/attributes-alphabetical-reference.md) .

Aby uzyskać więcej informacji, zobacz [atrybuty zdefiniowane przez użytkownika](../../extensions/user-defined-attributes-cpp-component-extensions.md).

Ten błąd może zostać wygenerowany w wyniku działania kompilatora, który został wykonany dla programu Visual Studio 2005: atrybut [UUID](../../windows/attributes/uuid-cpp-attributes.md) nie jest już dozwolony w atrybucie zdefiniowanym przez użytkownika przy użyciu programowania środowiska CLR. Zamiast tego użyj polecenia cmdlet <xref:System.Runtime.InteropServices.GuidAttribute>.

## <a name="example"></a>Przykład

Poniższy przykład generuje C3451.

```cpp
// C3451.cpp
// compile with: /clr /c
using namespace System;
[ attribute(AttributeTargets::All) ]
public ref struct MyAttr {};

[ MyAttr, helpstring("test") ]   // C3451
// try the following line instead
// [ MyAttr ]
public ref struct ABC {};
```
