---
description: 'Dowiedz się więcej o interfejsie: platform:: IBoxArray'
title: 'Platform:: IBoxArray, interfejs'
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::IBoxArray
- VCCORLIB/Platform::IBoxArray::Value
helpviewer_keywords:
- Platform::IBoxArray
ms.assetid: 6cd82c9e-4230-4147-9edb-7a652875dbf1
ms.openlocfilehash: 8b87a00d709bec8af016de4532c7c4ec759d72fc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97195147"
---
# <a name="platformiboxarray-interface"></a>Platform:: IBoxArray, interfejs

`IBoxArray` jest otoką dla tablic typów wartości, które są przesyłane przez interfejs binarny aplikacji (ABI) lub przechowywane w kolekcjach `Platform::Object^` elementów, takich jak te w kontrolkach XAML.

## <a name="syntax"></a>Składnia

```cpp
template <typename T>
interface class IBoxArray
```

#### <a name="parameters"></a>Parametry

*T*<br/>
Typ wartości opakowanej w każdym elemencie tablicy.

### <a name="remarks"></a>Uwagi

`IBoxArray` jest nazwą C++/CX dla `Windows::Foundation::IReferenceArray` .

### <a name="members"></a>Elementy członkowskie

`IBoxArray`Interfejs dziedziczy po `IValueType` interfejsie. `IBoxArray` ma również następujące elementy członkowskie:

|Metoda|Opis|
|------------|-----------------|
|[Wartość](#value)|Zwraca tablicę nieopakowaną, która była wcześniej przechowywana w tym `IBoxArray` wystąpieniu.|

## <a name="iboxarrayvalue-property"></a><a name="value"></a> IBoxArray:: Value — właściwość

Zwraca wartość oryginalnie przechowywaną w tym obiekcie.

### <a name="syntax"></a>Składnia

```cpp
property T Value {T get();}
```

### <a name="parameters"></a>Parametry

*T*<br/>
Typ wartości opakowanej.

### <a name="property-valuereturn-value"></a>Wartość właściwości/Zwracana wartość

Zwraca wartość oryginalnie przechowywaną w tym obiekcie.

### <a name="remarks"></a>Uwagi

Aby zapoznać się z przykładem, zobacz [opakowanie](../cppcx/boxing-c-cx.md).

## <a name="see-also"></a>Zobacz też

[Array i WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md)
