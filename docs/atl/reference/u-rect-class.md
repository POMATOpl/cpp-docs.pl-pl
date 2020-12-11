---
description: Dowiedz się więcej na temat klasy _U_RECT
title: Klasa _U_RECT
ms.date: 11/04/2016
f1_keywords:
- ATL::_U_RECT
- _U_RECT
- ATL._U_RECT
helpviewer_keywords:
- U_RECT class
- _U_RECT class
ms.assetid: 5f880a2d-09cf-4327-bf32-a3519c4dcd63
ms.openlocfilehash: b3720107d1b64f930b4c64dff269de041d9b928c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97157610"
---
# <a name="_u_rect-class"></a>Klasa _U_RECT

Klasa adaptera argumentów umożliwia `RECT` przekazywanie wskaźników lub odwołań do funkcji, która jest zaimplementowana w warunkach wskaźników.

> [!IMPORTANT]
> Tej klasy i jej elementów członkowskich nie można używać w aplikacjach, które są wykonywane w środowisko wykonawcze systemu Windows.

## <a name="syntax"></a>Składnia

```
class _U_RECT
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[_U_RECT:: _U_RECT](#_u_rect___u_rect)|Konstruktor.|

### <a name="public-data-members"></a>Publiczne elementy członkowskie danych

|Nazwa|Opis|
|----------|-----------------|
|[_U_RECT:: m_lpRect](#_u_rect__m_lprect)|Wskaźnik na `RECT` .|

## <a name="remarks"></a>Uwagi

Klasa definiuje dwa przeciążenia konstruktorów: jeden akceptuje argument **RECT&** , a drugi akceptuje `LPRECT` argument. Pierwszy Konstruktor przechowuje adres argumentu odwołania w pojedynczej składowej danych klasy, [m_lpRect](#_u_rect__m_lprect). Argument konstruktora wskaźnika jest przechowywany bezpośrednio bez konwersji.

## <a name="requirements"></a>Wymagania

**Nagłówek:** atlwin. h

## <a name="_u_rectm_lprect"></a><a name="_u_rect__m_lprect"></a> _U_RECT:: m_lpRect

Klasa przechowuje wartość przekazaną do jednego z jego konstruktorów jako publiczną `LPRECT` składową danych.

```
LPRECT m_lpRect;
```

## <a name="_u_rect_u_rect"></a><a name="_u_rect___u_rect"></a> _U_RECT:: _U_RECT

Adres argumentu odwołania jest przechowywany w pojedynczej składowej danych klasy, [m_lpRect](#_u_rect__m_lprect).

```
_U_RECT(RECT& rc);
_U_RECT(LPRECT lpRect);
```

### <a name="parameters"></a>Parametry

*zwrot*<br/>
`RECT`Odwołanie.

*lpRect*<br/>
`RECT`Wskaźnik.

### <a name="remarks"></a>Uwagi

Argument konstruktora wskaźnika jest przechowywany bezpośrednio bez konwersji.

## <a name="see-also"></a>Zobacz też

[Przegląd klas](../../atl/atl-class-overview.md)
