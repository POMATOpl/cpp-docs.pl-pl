---
description: 'Dowiedz się więcej na temat: Klasa CWinTraits'
title: Klasa CWinTraits
ms.date: 11/04/2016
f1_keywords:
- CWinTraits
- ATLWIN/ATL::CWinTraits
- ATLWIN/ATL::CWinTraits::GetWndExStyle
- ATLWIN/ATL::CWinTraits::GetWndStyle
helpviewer_keywords:
- CMDIChildWinTraits class
- window styles, default values for ATL
- CWinTraits class
- CFrameWinTraits class
- CControlWinTraits class
ms.assetid: f78f486e-6d9c-42c6-8e86-371e05aa7e59
ms.openlocfilehash: 3f23342cae58d70a602ebce1dcbe7efcddf36781
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97140091"
---
# <a name="cwintraits-class"></a>Klasa CWinTraits

Ta klasa udostępnia metodę standaryzacji stylów używanych podczas tworzenia obiektu okna.

> [!IMPORTANT]
> Tej klasy i jej elementów członkowskich nie można używać w aplikacjach, które są wykonywane w środowisko wykonawcze systemu Windows.

## <a name="syntax"></a>Składnia

```
template <DWORD t_dwStyle = 0, DWORD t_dwExStyle = 0>  class CWinTraits
```

#### <a name="parameters"></a>Parametry

*t_dwStyle*<br/>
Domyślny standardowy styl okna.

*t_dwExStyle*<br/>
Domyślne style okna rozszerzonego.

## <a name="members"></a>Elementy członkowskie

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CWinTraits::GetWndExStyle](#getwndexstyle)|Ruchom Pobiera Style rozszerzone dla `CWinTraits` obiektu.|
|[CWinTraits::GetWndStyle](#getwndstyle)|Ruchom Pobiera standardowe style dla `CWinTraits` obiektu.|

## <a name="remarks"></a>Uwagi

Ta klasa [cech okna](../../atl/understanding-window-traits.md) zapewnia prostą metodę standaryzacji stylów używanych do tworzenia obiektu okna ATL. Użyj specjalizacji tej klasy jako parametru szablonu do [CWindowImpl](../../atl/reference/cwindowimpl-class.md) lub innej klasy okna ATL, aby określić domyślny standardowy i rozszerzony styl używany dla wystąpień tej klasy okna.

Użyj tego szablonu, jeśli chcesz podać domyślne style okna, które będą używane tylko wtedy, gdy nie określono innych stylów w wywołaniu [CWindowImpl:: Create](../../atl/reference/cwindowimpl-class.md#create).

ATL oferuje trzy wstępnie zdefiniowane specjalizacje tego szablonu dla najczęściej używanych kombinacji stylów okna:

- `CControlWinTraits`

   Zaprojektowana dla standardowego okna kontroli. Używane są następujące style standardowe: WS_CHILD, WS_VISIBLE, WS_CLIPCHILDREN i WS_CLIPSIBLINGS. Brak stylów rozszerzonych.

- `CFrameWinTraits`

   Zaprojektowana dla standardowego okna ramki. Używane standardowe style obejmują: WS_OVERLAPPEDWINDOW, WS_CLIPCHILDREN i WS_CLIPSIBLINGS. Używane style rozszerzone obejmują: WS_EX_APPWINDOW i WS_EX_WINDOWEDGE.

- `CMDIChildWinTraits`

   Zaprojektowana dla standardowego okna podrzędnego MDI. Używane standardowe style obejmują: WS_OVERLAPPEDWINDOW, WS_CHILD, WS_VISIBLE, WS_CLIPCHILDREN i WS_CLIPSIBLINGS. Używane style rozszerzone obejmują: WS_EX_MDICHILD.

Jeśli chcesz upewnić się, że niektóre style są ustawione dla wszystkich wystąpień klasy Window, a inne style mają być ustawiane dla poszczególnych wystąpień, użyj [CWinTraitsOR](../../atl/reference/cwintraitsor-class.md) zamiast tego.

## <a name="requirements"></a>Wymagania

**Nagłówek:** atlwin. h

## <a name="cwintraitsgetwndstyle"></a><a name="getwndstyle"></a> CWinTraits::GetWndStyle

Wywołaj tę funkcję, aby pobrać style standardowe `CWinTraits` obiektu.

```
static DWORD GetWndStyle(DWORD dwStyle);
```

### <a name="parameters"></a>Parametry

*dwStyle*<br/>
Standardowe style używane do tworzenia okna. Jeśli *dwStyle* ma wartość 0, zwracane są wartości stylu szablonu ( `t_dwStyle` ). Jeśli *dwStyle* jest różna od zera, zwracany jest *dwStyle* .

### <a name="return-value"></a>Wartość zwracana

Standardowe style okna obiektu.

## <a name="cwintraitsgetwndexstyle"></a><a name="getwndexstyle"></a> CWinTraits::GetWndExStyle

Wywołaj tę funkcję, aby pobrać rozszerzone style `CWinTraits` obiektu.

```
static DWORD GetWndExStyle(DWORD dwExStyle);
```

### <a name="parameters"></a>Parametry

*dwExStyle*<br/>
Rozszerzone style używane do tworzenia okna. Jeśli *dwExStyle* ma wartość 0, zwracane są wartości stylu szablonu ( `t_dwExStyle` ). Jeśli *dwExStyle* jest różna od zera, zwracany jest *dwExStyle* .

### <a name="return-value"></a>Wartość zwracana

Rozszerzone style okna obiektu.

## <a name="see-also"></a>Zobacz też

[Przegląd klas](../../atl/atl-class-overview.md)<br/>
[Informacje o cechach okna](../../atl/understanding-window-traits.md)
