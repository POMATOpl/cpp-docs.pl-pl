---
description: 'Dowiedz się więcej na temat: Klasa CD2DSizeF'
title: Klasa CD2DSizeF
ms.date: 08/29/2019
f1_keywords:
- CD2DSizeF
- AFXRENDERTARGET/CD2DSizeF
- AFXRENDERTARGET/CD2DSizeF::CD2DSizeF
- AFXRENDERTARGET/CD2DSizeF::IsNull
helpviewer_keywords:
- CD2DSizeF [MFC], CD2DSizeF
- CD2DSizeF [MFC], IsNull
ms.assetid: f486a1e1-997d-4286-8cb9-26369dc82055
ms.openlocfilehash: d1416f7cd225be8edf1a7b08f06f611219d7846d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97240562"
---
# <a name="cd2dsizef-class"></a>Klasa CD2DSizeF

Otoka dla D2D1_SIZE_F.

## <a name="syntax"></a>Składnia

```
class CD2DSizeF : public D2D1_SIZE_F;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CD2DSizeF::CD2DSizeF](#cd2dsizef)|Przeciążone. Konstruuje `CD2DSizeF` obiekt z `D2D1_SIZE_F` obiektu.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CD2DSizeF:: IsNull](#isnull)|Zwraca wartość **logiczną** wskazującą, czy wyrażenie nie zawiera prawidłowych danych (null).|

### <a name="public-operators"></a>Operatory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CD2DSizeF:: operator CSize](#operator_csize)|Konwertuje `CD2DSizeF` na `CSize` obiekt.|

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`D2D1_SIZE_F`

[CD2DSizeF](../../mfc/reference/cd2dsizef-class.md)

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxrendertarget. h

## <a name="cd2dsizefcd2dsizef"></a><a name="cd2dsizef"></a> CD2DSizeF::CD2DSizeF

Konstruuje obiekt CD2DSizeF z obiektu CSize.

```
CD2DSizeF(const CSize& size);
CD2DSizeF(const D2D1_SIZE_F& size);
CD2DSizeF(const D2D1_SIZE_F* size);

CD2DSizeF(
    FLOAT cx = 0.,
    FLOAT cy = 0.);
```

### <a name="parameters"></a>Parametry

*zmienia*<br/>
rozmiar źródła

*CX*<br/>
Szerokość źródła

*cy*<br/>
wysokość źródła

## <a name="cd2dsizefisnull"></a><a name="isnull"></a> CD2DSizeF:: IsNull

Zwraca wartość logiczną wskazującą, czy wyrażenie nie zawiera prawidłowych danych (null).

```
BOOL IsNull() const;
```

### <a name="return-value"></a>Wartość zwracana

PRAWDA, jeśli szerokość i wysokość są puste; w przeciwnym razie FALSE.

## <a name="cd2dsizefoperator-csize"></a><a name="operator_csize"></a> CD2DSizeF:: operator CSize

Konwertuje CD2DSizeF na obiekt CSize.

```
operator CSize();
```

### <a name="return-value"></a>Wartość zwracana

Bieżąca wartość rozmiaru D2D.

## <a name="see-also"></a>Zobacz też

[Klasy](../../mfc/reference/mfc-classes.md)
