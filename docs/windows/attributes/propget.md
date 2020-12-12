---
description: 'Dowiedz się więcej na temat: propget'
title: propget (atrybut C++ COM)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.propget
helpviewer_keywords:
- propget attribute
ms.assetid: c9d4a97f-36dd-4b61-8eb0-b1a217598f14
ms.openlocfilehash: 9fe284fb35d4753fbc3e124458200a9882838450
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327408"
---
# <a name="propget"></a>propget

Określa funkcję akcesora właściwości.

## <a name="syntax"></a>Składnia

```cpp
[propget]
```

## <a name="remarks"></a>Uwagi

Atrybut **propget** C++ ma takie same funkcje jak atrybut [propget](/windows/win32/Midl/propget) MIDL.

## <a name="example"></a>Przykład

Zobacz przykład dla [powiązania](bindable.md) z przykładowym wykorzystaniem **propget**.

## <a name="requirements"></a>Wymagania

| Kontekst atrybutu | Wartość |
|-|-|
|**Dotyczy**|Metoda|
|**Powtarzalność**|Nie|
|**Wymagane atrybuty**|Brak|
|**Nieprawidłowe atrybuty**|`propput`, `propputref`|

Aby uzyskać więcej informacji na temat kontekstów atrybutów, zobacz [konteksty atrybutów](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Zobacz też

[Atrybuty IDL](idl-attributes.md)<br/>
[Atrybuty metody](method-attributes.md)<br/>
[propput](propput.md)<br/>
[propputref](propputref.md)
