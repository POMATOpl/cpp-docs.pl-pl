---
description: 'Dowiedz się więcej o programie: z ograniczeniami'
title: z ograniczeniami (atrybut C++ COM)
ms.date: 10/03/2018
f1_keywords:
- vc-attr.restricted
helpviewer_keywords:
- restricted attribute
ms.assetid: 504a96be-b904-4269-8be1-920feba201b4
ms.openlocfilehash: 8c0dc33d1ae7cff3625f1a938cac05c7ac72f474
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97329616"
---
# <a name="restricted"></a>restricted

Określa, że element członkowski modułu, interfejsu lub dispinterface nie może zostać wywołany arbitralnie.

## <a name="syntax"></a>Składnia

```cpp
[ restricted(
   interfaces
) ]
```

### <a name="parameters"></a>Parametry

*interfejsów*<br/>
Co najmniej jeden interfejs, który może nie być wywoływany arbitralnie dla obiektu COM. Ten parametr jest prawidłowy tylko wtedy, gdy jest stosowany do klasy.

## <a name="remarks"></a>Uwagi

Atrybut C++ z **ograniczeniami** ma taką samą funkcjonalność jak atrybut MIDL z [ograniczeniami](/windows/win32/Midl/restricted) .

## <a name="example"></a>Przykład

Poniższy kod pokazuje, jak używać atrybutu z **ograniczeniami** :

```cpp
// cpp_attr_ref_restricted.cpp
// compile with: /LD
#include "windows.h"
#include "unknwn.h"
[module(name="MyLib")];

[object, uuid("00000000-0000-0000-0000-000000000001")]
__interface a
{
};

[object, uuid("00000000-0000-0000-0000-000000000002")]
__interface b
{
};

[coclass, restricted(a,b), uuid("00000000-0000-0000-0000-000000000003")]
class c : public a, public b
{
};
```

## <a name="requirements"></a>Wymagania

| Kontekst atrybutu | Wartość |
|-|-|
|**Dotyczy**|Interface — Metoda, **interfejs**, **`class`** , **`struct`**|
|**Powtarzalność**|Nie|
|**Wymagane atrybuty**|**coclass** (w przypadku zastosowania do **`class`** lub **`struct`** )|
|**Nieprawidłowe atrybuty**|Brak|

Aby uzyskać więcej informacji na temat kontekstów atrybutów, zobacz [konteksty atrybutów](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Zobacz też

[Atrybuty IDL](idl-attributes.md)<br/>
[Atrybuty interfejsu](interface-attributes.md)<br/>
[Atrybuty metody](method-attributes.md)
