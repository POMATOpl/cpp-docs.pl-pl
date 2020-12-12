---
description: 'Dowiedz się więcej na temat: obiekt (C++)'
title: Object (atrybut C++ COM)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.object
helpviewer_keywords:
- object attribute
ms.assetid: f2d3c231-630d-4b4c-bd15-b1c30df362dd
ms.openlocfilehash: 82f259f6ca36c44f33eb68970d8b76ae2acc5853
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97329755"
---
# <a name="object-c"></a>object (C++)

Identyfikuje niestandardowy interfejs.

## <a name="syntax"></a>Składnia

```cpp
[object]
```

## <a name="remarks"></a>Uwagi

W przypadku powyższej definicji interfejsu atrybut **Object** języka C++ powoduje, że interfejs ma być umieszczony w pliku. idl jako niestandardowy interfejs.

Każdy interfejs oznaczony atrybutem Object musi dziedziczyć po elemencie `IUnknown` . Ten warunek jest spełniony, jeśli którykolwiek z interfejsów podstawowych dziedziczy z `IUnknown` . Jeśli żadne interfejsy podstawowe nie dziedziczą z `IUnknown` , kompilator spowoduje, że interfejs oznaczony atrybutem **Object** ma być pochodny `IUnknown` .

## <a name="example"></a>Przykład

Zobacz [nonbrowsable](nonbrowsable.md) , aby zapoznać się z przykładem użycia **obiektu**.

## <a name="requirements"></a>Wymagania

| Kontekst atrybutu | Wartość |
|-|-|
|**Dotyczy**|**interfejsu**|
|**Powtarzalność**|Nie|
|**Wymagane atrybuty**|Brak|
|**Nieprawidłowe atrybuty**|Brak|

Aby uzyskać więcej informacji na temat kontekstów atrybutów, zobacz [konteksty atrybutów](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Zobacz też

[Atrybuty IDL](idl-attributes.md)<br/>
[Atrybuty interfejsu](interface-attributes.md)<br/>
[obsługi](dual.md)<br/>
[dispinterface](dispinterface.md)<br/>
[celnej](custom-cpp.md)<br/>
[__interface](../../cpp/interface.md)
