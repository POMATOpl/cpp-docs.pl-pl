---
description: 'Dowiedz się więcej na temat: helpstringcontext'
title: helpstringcontext (atrybut C++ COM)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.helpstringcontext
helpviewer_keywords:
- helpstringcontext attribute [C++]
ms.assetid: d4cd135e-d91c-4aa3-9353-8aeb096f52cf
ms.openlocfilehash: afcd1d4052f7422cc6078c8dfdd0a0242c667f0f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97263364"
---
# <a name="helpstringcontext"></a>helpstringcontext

Określa identyfikator tematu pomocy w pliku HLP lub chm.

## <a name="syntax"></a>Składnia

```cpp
[ helpstringcontext(contextID) ]
```

### <a name="parameters"></a>Parametry

*Identyfikator ContextId*<br/>
32-bitowy identyfikator kontekstu pomocy w pliku **pomocy** .

## <a name="remarks"></a>Uwagi

Atrybut **helpstringcontext** C++ ma takie same funkcje jak atrybut [helpstringcontext](/windows/win32/Midl/helpstringcontext) odl.

## <a name="example"></a>Przykład

```cpp
// cpp_attr_ref_helpstringcontext.cpp
// compile with: /LD
#include <unknwn.h>
[module(name="MyLib")];

[   object, helpstring("help string"), helpstringcontext(1), uuid="11111111-1111-1111-1111-111111111111"
]
__interface IMyI
{
   HRESULT xx();
};
```

## <a name="requirements"></a>Wymagania

| Kontekst atrybutu | Wartość |
|-|-|
|**Dotyczy**|**`class`**, **interfejs**, metoda interfejsu|
|**Powtarzalność**|Nie|
|**Wymagane atrybuty**|Brak|
|**Nieprawidłowe atrybuty**|Brak|

Aby uzyskać więcej informacji, zobacz [konteksty atrybutów](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Zobacz też

[Atrybuty IDL](idl-attributes.md)<br/>
[Atrybuty interfejsu](interface-attributes.md)<br/>
[Atrybuty klasy](class-attributes.md)<br/>
[Atrybuty metody](method-attributes.md)<br/>
[elementu](module-cpp.md)
