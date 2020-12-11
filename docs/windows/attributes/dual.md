---
description: 'Dowiedz się więcej o: podwójne'
title: Podwójny (atrybut C++ COM)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.dual
helpviewer_keywords:
- dual attribute
ms.assetid: 5d4a9069-d819-42cd-ba56-bbcda17157d9
ms.openlocfilehash: d1e72bd787bc73042b4f4a180ea119712021edaf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97112027"
---
# <a name="dual"></a>dual

Umieszcza interfejs w pliku. idl jako podwójny interfejs.

## <a name="syntax"></a>Składnia

```cpp
[dual]
```

## <a name="remarks"></a>Uwagi

Gdy **podwójny** atrybut C++ poprzedza interfejs, powoduje, że interfejs należy umieścić wewnątrz bloku biblioteki w wygenerowanym pliku IDL.

## <a name="example"></a>Przykład

Poniższy kod jest blokiem atrybutu, który używa **dwóch** przed definicją interfejsu:

```cpp
// cpp_attr_ref_dual.cpp
// compile with: /LD
#include <windows.h>
[module(name="MyLibrary")];

[uuid("2F5F63F1-16DA-11d2-9E7B-00C04FB926DA"), dual]

__interface IStatic : IDispatch
{
   HRESULT Func1(int i);
   [   propget,    id(1),    bindable,    displaybind,    defaultbind,    requestedit
   ]
   HRESULT P1([out, retval] long *nSize);
   [   propput,    id(1),    bindable,    displaybind,    defaultbind,    requestedit
   ]
   HRESULT P1([in] long nSize);
};

[cpp_quote("#include file.h")];
```

## <a name="requirements"></a>Wymagania

| Kontekst atrybutu | Wartość |
|-|-|
|**Dotyczy**|**interfejsu**|
|**Powtarzalność**|Nie|
|**Wymagane atrybuty**|Brak|
|**Nieprawidłowe atrybuty**|`dispinterface`|

Aby uzyskać więcej informacji, zobacz [konteksty atrybutów](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Zobacz też

[Atrybuty IDL](idl-attributes.md)<br/>
[Atrybuty według użycia](attributes-by-usage.md)<br/>
[celnej](custom-cpp.md)<br/>
[dispinterface](dispinterface.md)<br/>
[Stream](object-cpp.md)<br/>
[__interface](../../cpp/interface.md)
