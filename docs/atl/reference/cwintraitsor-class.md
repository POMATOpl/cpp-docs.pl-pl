---
description: 'Dowiedz się więcej na temat: Klasa CWinTraitsOR'
title: Klasa CWinTraitsOR
ms.date: 11/04/2016
f1_keywords:
- CWinTraitsOR
- ATLWIN/ATL::CWinTraitsOR
- ATLWIN/ATL::CWinTraitsOR::GetWndExStyle
- ATLWIN/ATL::CWinTraitsOR::GetWndStyle
helpviewer_keywords:
- CWinTraitsOR class
- window styles, default values for ATL
ms.assetid: 1eb7b1e8-a9bd-411b-a30a-35a8a10af989
ms.openlocfilehash: 1d0a7ff8a78ebbdc416bdace2a1ea1f0199c292f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97140065"
---
# <a name="cwintraitsor-class"></a>Klasa CWinTraitsOR

Ta klasa udostępnia metodę standaryzacji stylów używanych podczas tworzenia obiektu okna.

> [!IMPORTANT]
> Tej klasy i jej elementów członkowskich nie można używać w aplikacjach, które są wykonywane w środowisko wykonawcze systemu Windows.

## <a name="syntax"></a>Składnia

```
template <DWORD t_dwStyle = 0,
          DWORD t_dwExStyle = 0,
          class TWinTraits = CControlWinTraits>
class CWinTraitsOR
```

#### <a name="parameters"></a>Parametry

*t_dwStyle*<br/>
Domyślne style okien.

*t_dwExStyle*<br/>
Domyślne style okna rozszerzonego.

## <a name="members"></a>Elementy członkowskie

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CWinTraitsOR::GetWndExStyle](#getwndexstyle)|Pobiera Style rozszerzone dla `CWinTraitsOR` obiektu.|
|[CWinTraitsOR::GetWndStyle](#getwndstyle)|Pobiera standardowe style dla `CWinTraitsOR` obiektu.|

## <a name="remarks"></a>Uwagi

Ta klasa [cech okna](../../atl/understanding-window-traits.md) zapewnia prostą metodę standaryzacji stylów używanych do tworzenia obiektu okna ATL. Użyj specjalizacji tej klasy jako parametru szablonu do [CWindowImpl](../../atl/reference/cwindowimpl-class.md) lub innej klasy okna ATL, aby określić minimalny zestaw standardowych i rozszerzonych stylów, które mają być używane dla wystąpień tej klasy okna.

Użyj specjalizacji tego szablonu, jeśli chcesz mieć pewność, że niektóre style są ustawione dla wszystkich wystąpień klasy okna, a jednocześnie zezwalasz na ustawienie innych stylów dla poszczególnych wystąpień w wywołaniu [CWindowImpl:: Create](../../atl/reference/cwindowimpl-class.md#create).

Jeśli chcesz podać domyślne style okna, które będą używane tylko wtedy, gdy w wywołaniu nie określono żadnych innych stylów `CWindowImpl::Create` , użyj [CWinTraits](../../atl/reference/cwintraits-class.md) zamiast tego.

## <a name="requirements"></a>Wymagania

**Nagłówek:** atlwin. h

## <a name="cwintraitsorgetwndstyle"></a><a name="getwndstyle"></a> CWinTraitsOR::GetWndStyle

Wywołaj tę funkcję, aby pobrać kombinację (przy użyciu operatora logicznego OR) standardowych stylów `CWinTraits` obiektu i domyślnych stylów określonych przez *t_dwStyle*.

```
static DWORD GetWndStyle(DWORD dwStyle);
```

### <a name="parameters"></a>Parametry

*dwStyle*<br/>
Style używane do tworzenia okna.

### <a name="return-value"></a>Wartość zwracana

Kombinacja stylów, które są przesyłane w *dwStyle* i domyślnych określonych przez `t_dwStyle` , za pomocą operatora logicznego OR.

## <a name="cwintraitsorgetwndexstyle"></a><a name="getwndexstyle"></a> CWinTraitsOR::GetWndExStyle

Wywołaj tę funkcję, aby pobrać kombinację (przy użyciu operatora logicznego OR) dla rozszerzonych stylów `CWinTraits` obiektu i domyślnych stylów określonych przez `t_dwStyle` .

```
static DWORD GetWndExStyle(DWORD dwExStyle);
```

### <a name="parameters"></a>Parametry

*dwExStyle*<br/>
Rozszerzone style używane do tworzenia okna.

### <a name="return-value"></a>Wartość zwracana

Kombinacja stylów rozszerzonych, które są przesyłane w *dwExStyle* i domyślnych określonych przez `t_dwExStyle` , za pomocą operatora logicznego OR

## <a name="see-also"></a>Zobacz też

[Przegląd klas](../../atl/atl-class-overview.md)<br/>
[Informacje o cechach okna](../../atl/understanding-window-traits.md)
