---
description: 'Dowiedz się więcej na temat: Klasa CAtlAutoThreadModule'
title: Klasa CAtlAutoThreadModule
ms.date: 11/04/2016
f1_keywords:
- CAtlAutoThreadModule
- atlbase/ATL::CAtlAutoThreadModule
helpviewer_keywords:
- CAtlAutoThreadModule class
ms.assetid: 3be834aa-55ef-403e-94ae-41979691b15f
ms.openlocfilehash: d1742488cca84dccfa53753bec40f9081d77f67d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97165059"
---
# <a name="catlautothreadmodule-class"></a>Klasa CAtlAutoThreadModule

Ta klasa implementuje serwer COM z pulą wątków, model typu Apartment.

> [!IMPORTANT]
> Tej klasy i jej elementów członkowskich nie można używać w aplikacjach, które są wykonywane w środowisko wykonawcze systemu Windows.

## <a name="syntax"></a>Składnia

```cpp
class CAtlAutoThreadModule : public CAtlAutoThreadModuleT<CAtlAutoThreadModule>
```

## <a name="remarks"></a>Uwagi

`CAtlAutoThreadModule` pochodzi z [CAtlAutoThreadModuleT](../../atl/reference/catlautothreadmodulet-class.md) i implementuje serwer modelu COM z pulą wątków. `CAtlAutoThreadModule` używa [CComApartment](../../atl/reference/ccomapartment-class.md) do zarządzania komórką dla każdego wątku w module.

Aby określić [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md) jako fabrykę klas, należy użyć makra [DECLARE_CLASSFACTORY_AUTO_THREAD](aggregation-and-class-factory-macros.md#declare_classfactory_auto_thread) w definicji klasy obiektu. Następnie należy dodać pojedyncze wystąpienie klasy pochodzącej z `CAtlAutoThreadModuleT` takich elementów jak `CAtlAutoThreadModule` . Na przykład:

`CAtlAutoThreadModule _AtlAutoModule; // name is immaterial.`

> [!NOTE]
> Ta klasa zastępuje przestarzałą klasę [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md) .

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`IAtlAutoThreadModule`

[CAtlAutoThreadModuleT](../../atl/reference/catlautothreadmodulet-class.md)

`CAtlAutoThreadModule`

## <a name="requirements"></a>Wymagania

**Nagłówek:** atlbase. h

## <a name="see-also"></a>Zobacz też

[Klasa CAtlAutoThreadModuleT](../../atl/reference/catlautothreadmodulet-class.md)<br/>
[Klasa IAtlAutoThreadModule](../../atl/reference/iatlautothreadmodule-class.md)<br/>
[Przegląd klas](../../atl/atl-class-overview.md)<br/>
[Klasy modułów](../../atl/atl-module-classes.md)
