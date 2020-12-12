---
description: 'Dowiedz się więcej na temat: helpstringdll'
title: helpstringdll (atrybut C++ COM)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.helpstringdll
helpviewer_keywords:
- helpstringdll attribute [C++]
ms.assetid: 121271fa-f061-492b-b87f-bbfcf4b02e7b
ms.openlocfilehash: 13a64f7f98a9d63e6a176911caad1246ad64af75
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97148801"
---
# <a name="helpstringdll"></a>helpstringdll

Określa nazwę biblioteki DLL, która ma być używana do przeszukiwania ciągu dokumentu (lokalizacja).

## <a name="syntax"></a>Składnia

```cpp
[ helpstringdll("string") ]
```

### <a name="parameters"></a>Parametry

*parametry*<br/>
Biblioteka DLL do użycia w celu przeprowadzenia wyszukiwania ciągów dokumentu.

## <a name="remarks"></a>Uwagi

Atrybut **helpstringdll** C++ ma takie same funkcje jak atrybut [helpstringdll](/windows/win32/Midl/helpstringdll) MIDL.

## <a name="example"></a>Przykład

```cpp
// cpp_attr_ref_helpstringdll.cpp
// compile with: /LD
#include <unknwn.h>
[module(name="MyLib", helpstringdll="xx.dll")];

[object, uuid("00000000-0000-0000-0000-000000000001")]
__interface IMyI
{
   HRESULT xxx();
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
[Atrybuty metody](method-attributes.md)
