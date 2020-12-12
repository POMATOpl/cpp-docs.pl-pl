---
description: 'Dowiedz się więcej o: operator Windows:: UI:: XAML:: Interop:: TypeName'
title: operator Windows::UI::Xaml::Interop::TypeName
ms.date: 12/30/2016
ms.assetid: a65a105e-7e3a-452f-932f-2cdaf00fbba5
ms.openlocfilehash: 3c4c856fcf93214959f75f861b035dbdee9b94a6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97145720"
---
# <a name="operator-windowsuixamlinteroptypename"></a>operator Windows::UI::Xaml::Interop::TypeName

Włącza konwersję z `Platform::Type` do [systemu Windows:: UI:: XAML:: Interop:: TypeName](/uwp/api/windows.ui.xaml.interop.typename).

## <a name="syntax"></a>Składnia

```cpp
Operator TypeName(Platform::Type^ type);
```

### <a name="return-value"></a>Wartość zwracana

Zwraca element [Windows:: UI:: XAML:: Interop:: TypeName](/uwp/api/windows.ui.xaml.interop.typename) , gdy podaje `Platform::Type^` .

### <a name="remarks"></a>Uwagi

`TypeName` jest to niezależna od języka struktura środowisko wykonawcze systemu Windows dla reprezentowania informacji o typie. [Platform:: Type](../cppcx/platform-type-class.md) jest specyficzne dla języka C++ i nie można go przekazywać przez interfejs binarny aplikacji (ABI). Oto jedno z nich `TypeName` , w funkcji [nawigacji](/uwp/api/windows.ui.xaml.controls.frame.navigate) :

```cpp
rootFrame->Navigate(TypeName(MainPage::typeid), e->Arguments);
```

### <a name="example"></a>Przykład

W następnym przykładzie pokazano, jak konwertować między `TypeName` i `Type` .

```cpp
// Convert from Type to TypeName
Windows::UI::Xaml::Interop::TypeName tn = TypeName(MainPage::typeid);

// Convert back from TypeName to Type
Type^ tx2 = (Type^)(tn);
```

## <a name="net-framework-equivalent"></a>Odpowiednik w programie .NET Framework

.NET Framework programów projektu `TypeName` jako [System. Type](/dotnet/api/system.type).

### <a name="requirements"></a>Wymagania

## <a name="see-also"></a>Zobacz też

[operator Windows::UI::Xaml::Interop::TypeName](../cppcx/operator-windows-ui-xaml-interop-typename.md)<br/>
[Platform:: Type — Klasa](../cppcx/platform-type-class.md)
