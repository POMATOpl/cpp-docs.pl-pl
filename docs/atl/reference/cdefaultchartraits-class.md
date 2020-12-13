---
description: 'Dowiedz się więcej na temat: Klasa CDefaultCharTraits'
title: Klasa CDefaultCharTraits
ms.date: 11/04/2016
f1_keywords:
- CDefaultCharTraits
- ATLCOLL/ATL::CDefaultCharTraits
- ATLCOLL/ATL::CDefaultCharTraits::CharToLower
- ATLCOLL/ATL::CDefaultCharTraits::CharToUpper
helpviewer_keywords:
- CDefaultCharTraits class
ms.assetid: f94a3934-597f-401d-8513-ed6924ae069a
ms.openlocfilehash: 6d98c6b6ffb527fef1e5b2320b46eda61ec3f670
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97141963"
---
# <a name="cdefaultchartraits-class"></a>Klasa CDefaultCharTraits

Ta klasa udostępnia dwie statyczne funkcje do konwertowania znaków między wielkie i małe litery.

## <a name="syntax"></a>Składnia

```
template <typename T>
class CDefaultCharTraits
```

#### <a name="parameters"></a>Parametry

*T*<br/>
Typ danych, które mają być przechowywane w kolekcji.

## <a name="members"></a>Elementy członkowskie

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CDefaultCharTraits::CharToLower](#chartolower)|Ruchom Wywołaj tę funkcję, aby skonwertować znak na wielkie litery.|
|[CDefaultCharTraits::CharToUpper](#chartoupper)|Ruchom Wywołaj tę funkcję, aby skonwertować znak na małe litery.|

## <a name="remarks"></a>Uwagi

Ta klasa udostępnia funkcje, które są wykorzystywane przez klasę [CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md).

## <a name="requirements"></a>Wymagania

**Nagłówek:** atlcoll. h

## <a name="cdefaultchartraitschartolower"></a><a name="chartolower"></a> CDefaultCharTraits::CharToLower

Wywołaj tę funkcję, aby skonwertować znak na małe litery.

```
static wchar_t CharToLower(wchar_t x);
static char CharToLower(char x);
```

### <a name="parameters"></a>Parametry

*x*<br/>
Znak do przekonwertowania na małe litery.

### <a name="example"></a>Przykład

[!code-cpp[NVC_ATL_Utilities#132](../../atl/codesnippet/cpp/cdefaultchartraits-class_1.cpp)]

## <a name="cdefaultchartraitschartoupper"></a><a name="chartoupper"></a> CDefaultCharTraits::CharToUpper

Wywołaj tę funkcję, aby skonwertować znak na wielkie litery.

```
static wchar_t CharToUpper(wchar_t x);
static char CharToUpper(char x);
```

### <a name="parameters"></a>Parametry

*x*<br/>
Znak do przekonwertowania na wielkie litery.

## <a name="see-also"></a>Zobacz też

[Przegląd klas](../../atl/atl-class-overview.md)
