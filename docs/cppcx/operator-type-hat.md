---
description: 'Dowiedz się więcej na temat: typ operatora ^'
title: operator Type^
ms.date: 12/30/2016
ms.assetid: b24ffc83-0780-4f9a-8ee0-f5725db339d1
ms.openlocfilehash: 6258da5f276313d28f56fe470849c929cc057a47
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97276806"
---
# <a name="operator-type"></a>operator Type^

Włącza konwersję z [systemu Windows:: UI:: XAML:: Interop:: TypeName](/uwp/api/windows.ui.xaml.interop.typename) do `Platform::Type` .

## <a name="syntax"></a>Składnia

```cpp
Operator Type^(Windows::UI::Xaml::Interop::TypeName typeName);
```

### <a name="return-value"></a>Wartość zwracana

Zwraca wartość, `Platform::Type` gdy podaje się obiekt [Windows:: UI:: XAML:: Interop:: TypeName](/uwp/api/windows.ui.xaml.interop.typename).

### <a name="remarks"></a>Uwagi

`TypeName` jest to niezależna od języka struktura środowisko wykonawcze systemu Windows dla reprezentowania informacji o typie. [Platform:: Type](../cppcx/platform-type-class.md) jest specyficzne dla języka C++ i nie można go przekazywać przez interfejs binarny aplikacji (ABI). Oto jedno z nich `TypeName` , w funkcji [nawigacji](/uwp/api/windows.ui.xaml.controls.frame.navigate) :

```
rootFrame->Navigate(TypeName(MainPage::typeid), e->Arguments);
```

### <a name="example"></a>Przykład

W następnym przykładzie pokazano, jak konwertować między `TypeName` i `Type` .

```

// Convert from Type to TypeName
TypeName tn = TypeName(MainPage::typeid);

// Convert back from TypeName to Type
Type^ tx2 = (Type^)(tn);
```

## <a name="net-framework-equivalent"></a>Odpowiednik w programie .NET Framework

.NET Framework programów projektu `TypeName` jako <xref:System.Type>

### <a name="requirements"></a>Wymagania

## <a name="see-also"></a>Zobacz też

[operator Windows::UI::Xaml::Interop::TypeName](../cppcx/operator-windows-ui-xaml-interop-typename.md)<br/>
[Platform:: Type — Klasa](../cppcx/platform-type-class.md)
