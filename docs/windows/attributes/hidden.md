---
description: 'Dowiedz się więcej na temat: ukryte'
title: ukryty (atrybut C++ COM)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.hidden
helpviewer_keywords:
- hidden attribute
ms.assetid: 199c96dd-fc07-46c7-af93-92020aebebe7
ms.openlocfilehash: 0609ef8b0dedb08e26e5442fd5070ca6a29e11d6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97180230"
---
# <a name="hidden"></a>hidden

Wskazuje, że element istnieje, ale nie powinien być wyświetlany w przeglądarce zorientowanej na użytkownika.

## <a name="syntax"></a>Składnia

```cpp
[hidden]
```

## <a name="remarks"></a>Uwagi

**Ukryty** atrybut C++ ma taką samą funkcjonalność jak [ukryty](/windows/win32/Midl/hidden) atrybut MIDL.

## <a name="example"></a>Przykład

Zobacz przykład dla [powiązania](bindable.md) z przykładem, jak używać **ukrytego**.

## <a name="requirements"></a>Wymagania

| Kontekst atrybutu | Wartość |
|-|-|
|**Dotyczy**|**interfejs**, **`class`** , **`struct`** , metoda, właściwość|
|**Powtarzalność**|Nie|
|**Wymagane atrybuty**|**coclass** (w przypadku zastosowania do **`class`** lub **`struct`** )|
|**Nieprawidłowe atrybuty**|Brak|

Aby uzyskać więcej informacji, zobacz [konteksty atrybutów](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Zobacz też

[Atrybuty IDL](idl-attributes.md)<br/>
[Atrybuty interfejsu](interface-attributes.md)<br/>
[Atrybuty klasy](class-attributes.md)<br/>
[Atrybuty metody](method-attributes.md)
