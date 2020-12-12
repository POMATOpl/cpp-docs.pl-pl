---
description: 'Dowiedz się więcej na temat: propputref'
title: propputref (atrybut C++ COM)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.propputref
helpviewer_keywords:
- propputref attribute
ms.assetid: 9b0aed74-fdc7-4e59-9117-949bea4f86dd
ms.openlocfilehash: 5f09d742ef0df75df03e4f4d740181cfcaaa8f2d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97329668"
---
# <a name="propputref"></a>propputref

Określa funkcję ustawienia właściwości, która używa odwołania zamiast wartości.

## <a name="syntax"></a>Składnia

```cpp
[propputref]
```

## <a name="remarks"></a>Uwagi

Atrybut **propputref** C++ ma takie same funkcje jak atrybut [propputref](/windows/win32/Midl/propputref) MIDL.

## <a name="example"></a>Przykład

Zobacz przykład dla [powiązania](bindable.md) z przykładowym wykorzystaniem **propputref**.

## <a name="requirements"></a>Wymagania

| Kontekst atrybutu | Wartość |
|-|-|
|**Dotyczy**|Metoda|
|**Powtarzalność**|Nie|
|**Wymagane atrybuty**|Brak|
|**Nieprawidłowe atrybuty**|`propget`, `propput`|

Aby uzyskać więcej informacji na temat kontekstów atrybutów, zobacz [konteksty atrybutów](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Zobacz też

[Atrybuty IDL](idl-attributes.md)<br/>
[Atrybuty metody](method-attributes.md)<br/>
[propget](propget.md)<br/>
[propput](propput.md)
