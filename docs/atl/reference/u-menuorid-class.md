---
description: Dowiedz się więcej na temat klasy _U_MENUorID
title: Klasa _U_MENUorID
ms.date: 11/04/2016
f1_keywords:
- ATL._U_MENUorID
- ATL::_U_MENUorID
- _U_MENUorID
helpviewer_keywords:
- U_MENUorID class
- _U_MENUorID class
ms.assetid: cfc8032b-61b4-4a68-ba3a-92b82500ccae
ms.openlocfilehash: 4418e9db455e72643c497925c19900b41c9b9f38
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97138791"
---
# <a name="_u_menuorid-class"></a>Klasa _U_MENUorID

Ta klasa udostępnia otoki dla `CreateWindow` i `CreateWindowEx` .

> [!IMPORTANT]
> Tej klasy i jej elementów członkowskich nie można używać w aplikacjach, które są wykonywane w środowisko wykonawcze systemu Windows.

## <a name="syntax"></a>Składnia

```
class _U_MENUorID
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[_U_MENUorID:: _U_MENUorID](#_u_menuorid___u_menuorid)|Konstruktor.|

### <a name="public-data-members"></a>Publiczne elementy członkowskie danych

|Nazwa|Opis|
|----------|-----------------|
|[_U_MENUorID:: m_hMenu](#_u_menuorid__m_hmenu)|Uchwyt do menu.|

## <a name="remarks"></a>Uwagi

Ta klasa adaptera argument umożliwia przekazywanie identyfikatorów (UINTs) lub uchwytów menu (HMENUs) do funkcji bez konieczności jawnego rzutowania w części obiektu wywołującego.

Ta klasa została zaprojektowana na potrzeby implementowania otok do interfejsu API systemu Windows [, w szczególności funkcji HMENU i](/windows/win32/api/winuser/nf-winuser-createwindoww) [elementu CreateWindowEx](/windows/win32/api/winuser/nf-winuser-createwindowexw) , z których oba przyjmują argument, który może być identyfikatorem okna podrzędnego (uint), a nie uchwytem menu. Na przykład można zobaczyć, że ta klasa jest używana jako parametr do [CWindowImpl:: Create](cwindowimpl-class.md#create).

Klasa definiuje dwa przeciążenia konstruktorów: jeden akceptuje argument UINT, a drugi akceptuje argument HMENU. Argument UINT jest właśnie rzutowany na HMENU w konstruktorze i wynik przechowywany w pojedynczej składowej danych klasy, [m_hMenu](#_u_menuorid__m_hmenu). Argument konstruktora HMENU jest przechowywany bezpośrednio bez konwersji.

## <a name="requirements"></a>Wymagania

**Nagłówek:** atlwin. h

## <a name="_u_menuoridm_hmenu"></a><a name="_u_menuorid__m_hmenu"></a> _U_MENUorID:: m_hMenu

Klasa przechowuje wartość przekazaną do jednego z jego konstruktorów jako element członkowski danych HMENU Public.

```
HMENU m_hMenu;
```

## <a name="_u_menuorid_u_menuorid"></a><a name="_u_menuorid___u_menuorid"></a> _U_MENUorID:: _U_MENUorID

Argument UINT jest właśnie rzutowany na HMENU w konstruktorze i wynik przechowywany w pojedynczej składowej danych klasy, [m_hMenu](#_u_menuorid__m_hmenu).

```
_U_MENUorID(UINT nID);
_U_MENUorID(HMENU hMenu);
```

### <a name="parameters"></a>Parametry

*nID*<br/>
Identyfikator okna podrzędnego.

*hMenu*<br/>
Uchwyt menu.

### <a name="remarks"></a>Uwagi

Argument konstruktora HMENU jest przechowywany bezpośrednio bez konwersji.

## <a name="see-also"></a>Zobacz też

[Przegląd klas](../../atl/atl-class-overview.md)
