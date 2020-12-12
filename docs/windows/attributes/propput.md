---
description: 'Dowiedz się więcej na temat: propput'
title: propput (atrybut C++ COM)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.propput
helpviewer_keywords:
- propput attribute
ms.assetid: 1f84dda9-9cce-4e16-aaf0-b2c5219827f2
ms.openlocfilehash: f7b33996c4575de6b94fc3127c33a88c6f791aed
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327385"
---
# <a name="propput"></a>propput

Określa funkcję ustawienia właściwości.

## <a name="syntax"></a>Składnia

```cpp
[propput]
```

## <a name="remarks"></a>Uwagi

Atrybut **propput** C++ ma takie same funkcje jak atrybut [propput](/windows/win32/Midl/propput) MIDL.

## <a name="example"></a>Przykład

Zobacz przykład dla [powiązania](bindable.md) z przykładowym wykorzystaniem **propput**.

## <a name="requirements"></a>Wymagania

| Kontekst atrybutu | Wartość |
|-|-|
|**Dotyczy**|Metoda|
|**Powtarzalność**|Nie|
|**Wymagane atrybuty**|Brak|
|**Nieprawidłowe atrybuty**|`propget`, `propputref`|

Aby uzyskać więcej informacji na temat kontekstów atrybutów, zobacz [konteksty atrybutów](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Zobacz też

[Atrybuty IDL](idl-attributes.md)<br/>
[Atrybuty metody](method-attributes.md)<br/>
[propget](propget.md)<br/>
[propputref](propputref.md)
