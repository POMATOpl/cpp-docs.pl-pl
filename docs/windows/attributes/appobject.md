---
description: 'Dowiedz się więcej na temat: appobject'
title: appobject (atrybut C++ COM)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.appobject
helpviewer_keywords:
- appobject attribute
ms.assetid: 8ce30b73-e945-403e-a755-6bc78078a695
ms.openlocfilehash: b371b9726e3a750ef5d40ebe5abae219b473bb02
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97205463"
---
# <a name="appobject"></a>appobject

Identyfikuje klasy coclass jako obiekt aplikacji, który jest skojarzony z pełną aplikacją. exe i wskazuje, że funkcje i właściwości klasy coclass są dostępne globalnie w tej [bibliotece typów](../../mfc/automation-clients-using-type-libraries.md).

## <a name="syntax"></a>Składnia

```cpp
[appobject]
```

## <a name="remarks"></a>Uwagi

Atrybut **appobject** C++ ma takie same funkcje jak atrybut [appobject](/windows/win32/Midl/appobject) MIDL.

## <a name="example"></a>Przykład

Poniższy kod pokazuje prostą definicję klasy poprzedzoną blokiem atrybutu, który zawiera **appobject**:

```cpp
// cpp_attr_ref_appobject.cpp
// compile with: /LD
#include <windows.h>
[module(name="MyLib", uuid="f1ce17f0-a5df-4d26-95f6-0a122197ac5b")];

[object, uuid="905de6db-7a12-45ab-9f8b-b39f5112f010"]
__interface ICustom {};

[coclass, appobject,uuid="00395340-745f-4b69-bd58-e2921452b9fc"]
class A : public ICustom {
   int i;
};
```

## <a name="requirements"></a>Wymagania

| Kontekst atrybutu | Wartość |
|-|-|
|**Dotyczy**|**`class`**, **`struct`**|
|**Powtarzalność**|Nie|
|**Wymagane atrybuty**|`coclass`|
|**Nieprawidłowe atrybuty**|Brak|

Aby uzyskać więcej informacji na temat kontekstów atrybutów, zobacz [konteksty atrybutów](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Zobacz też

[Atrybuty IDL](idl-attributes.md)<br/>
[Atrybuty klasy](class-attributes.md)<br/>
[Atrybuty typedef, enum, Union i struct](typedef-enum-union-and-struct-attributes.md)
