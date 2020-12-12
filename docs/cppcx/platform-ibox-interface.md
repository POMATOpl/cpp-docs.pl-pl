---
description: 'Dowiedz się więcej o interfejsie: platform:: IBox'
title: 'Platform:: IBox, interfejs'
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Namespace not found::Platform
- VCCORLIB/Namespace not found::Platform::Value
ms.assetid: 774df45d-f8a7-45a3-ae24-eecc3c681040
ms.openlocfilehash: abd1b9107fe1d472135f2b2addc7fa4b0f88ecfd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97195180"
---
# <a name="platformibox-interface"></a>Platform:: IBox, interfejs

Interfejs [platform:: IBox](../cppcx/platform-ibox-interface.md) jest nazwą języka C++ dla `Windows::Foundation::IReference` interfejsu.

## <a name="syntax"></a>Składnia

```cpp
template <typename T>
interface class IBox
```

#### <a name="parameters"></a>Parametry

*T*<br/>
Typ wartości opakowanej.

### <a name="remarks"></a>Uwagi

`IBox<T>`Interfejs jest głównie używany wewnętrznie do reprezentowania typów wartości null, zgodnie z opisem w [klasach wartości i strukturach (C++/CX)](../cppcx/value-classes-and-structs-c-cx.md). Interfejs jest również używany do typów wartości, które są przesyłane do metod języka C++ przyjmujących parametry typu `Object^` . Można jawnie zadeklarować parametr wejściowy jako `IBox<SomeValueType>` . Aby zapoznać się z przykładem, zobacz [opakowanie](../cppcx/boxing-c-cx.md).

### <a name="requirements"></a>Wymagania

### <a name="members"></a>Elementy członkowskie

`Platform::IBox`Interfejs dziedziczy z interfejsu [platform:: IValueType](../cppcx/platform-ivaluetype-interface.md) . `IBox` ma następujących członków:

**Właściwości**

|Metoda|Opis|
|------------|-----------------|
|[Wartość](#value)|Zwraca niezaopakowaną wartość, która była wcześniej przechowywana w tym `IBox` wystąpieniu.|

## <a name="iboxvalue-property"></a><a name="value"></a> IBox:: Value — właściwość

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

[Przestrzeń nazw platformy](../cppcx/platform-namespace-c-cx.md)
