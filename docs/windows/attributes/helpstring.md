---
description: 'Dowiedz się więcej na temat: HelpString'
title: HelpString (atrybut C++ COM)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.helpstring
helpviewer_keywords:
- helpstring attribute [C++]
ms.assetid: 0401e905-a63e-4fad-98d0-d1efea111966
ms.openlocfilehash: 3b3aa2470080f33fd4a9dea4f063e908c0431d5a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97148814"
---
# <a name="helpstring"></a>helpstring

Określa ciąg znaków, który jest używany do opisania elementu, do którego ma zastosowanie.

## <a name="syntax"></a>Składnia

```cpp
[ helpstring("string") ]
```

### <a name="parameters"></a>Parametry

*parametry*<br/>
Tekst ciągu pomocy.

## <a name="remarks"></a>Uwagi

Atrybut **HelpString** C++ ma takie same funkcje jak atrybut [HelpString](/windows/win32/Midl/helpstring) MIDL.

## <a name="example"></a>Przykład

Zobacz przykład dla elementu [DefaultValue](defaultvalue.md) , aby zapoznać się z przykładem korzystania z **HelpString**.

## <a name="requirements"></a>Wymagania

| Kontekst atrybutu | Wartość |
|-|-|
|**Dotyczy**|**interfejs**, **`typedef`** , **`class`** , metoda, właściwość|
|**Powtarzalność**|Nie|
|**Wymagane atrybuty**|Brak|
|**Nieprawidłowe atrybuty**|Brak|

Aby uzyskać więcej informacji, zobacz [konteksty atrybutów](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Zobacz też

[Atrybuty IDL](idl-attributes.md)<br/>
[Atrybuty interfejsu](interface-attributes.md)<br/>
[Atrybuty klasy](class-attributes.md)<br/>
[Atrybuty metody](method-attributes.md)<br/>
[Atrybuty typedef, enum, Union i struct](typedef-enum-union-and-struct-attributes.md)<br/>
[helpfile](helpfile.md)<br/>
[helpcontext](helpcontext.md)
