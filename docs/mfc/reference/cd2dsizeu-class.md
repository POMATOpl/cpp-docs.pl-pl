---
description: 'Dowiedz się więcej na temat: Klasa CD2DSizeU'
title: Klasa CD2DSizeU
ms.date: 08/29/2019
f1_keywords:
- CD2DSizeU
- AFXRENDERTARGET/CD2DSizeU
- AFXRENDERTARGET/CD2DSizeU::CD2DSizeU
- AFXRENDERTARGET/CD2DSizeU::IsNull
helpviewer_keywords:
- CD2DSizeU [MFC], CD2DSizeU
- CD2DSizeU [MFC], IsNull
ms.assetid: 6e679ba8-2112-43c3-8275-70b660856f02
ms.openlocfilehash: 0bb2d7cc632012fe8d8c0e3ada09025c2b025e64
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97154711"
---
# <a name="cd2dsizeu-class"></a>Klasa CD2DSizeU

Otoka dla D2D1_SIZE_U.

## <a name="syntax"></a>Składnia

```
class CD2DSizeU : public D2D1_SIZE_U;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CD2DSizeU::CD2DSizeU](#cd2dsizeu)|Przeciążone. Konstruuje `CD2DSizeU` obiekt z `D2D1_SIZE_U` obiektu.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CD2DSizeU:: IsNull](#isnull)|Zwraca wartość **logiczną** wskazującą, czy wyrażenie nie zawiera prawidłowych danych (null).|

### <a name="public-operators"></a>Operatory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CD2DSizeU:: operator CSize](#operator_csize)|Konwertuje `CD2DSizeU` na `CSize` obiekt.|

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`D2D1_SIZE_U`

[CD2DSizeU](../../mfc/reference/cd2dsizeu-class.md)

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxrendertarget. h

## <a name="cd2dsizeucd2dsizeu"></a><a name="cd2dsizeu"></a> CD2DSizeU::CD2DSizeU

Konstruuje obiekt CD2DSizeU z obiektu CSize.

```
CD2DSizeU(const CSize& size);
CD2DSizeU(const D2D1_SIZE_U& size);
CD2DSizeU(const D2D1_SIZE_U* size);

CD2DSizeU(
    UINT32 cx = 0,
    UINT32 cy = 0);
```

### <a name="parameters"></a>Parametry

*zmienia*<br/>
rozmiar źródła

*CX*<br/>
Szerokość źródła

*cy*<br/>
wysokość źródła

## <a name="cd2dsizeuisnull"></a><a name="isnull"></a> CD2DSizeU:: IsNull

Zwraca wartość logiczną wskazującą, czy wyrażenie nie zawiera prawidłowych danych (null).

```
BOOL IsNull() const;
```

### <a name="return-value"></a>Wartość zwracana

PRAWDA, jeśli szerokość i wysokość są puste; w przeciwnym razie FALSE.

## <a name="cd2dsizeuoperator-csize"></a><a name="operator_csize"></a> CD2DSizeU:: operator CSize

Konwertuje CD2DSizeU na obiekt CSize.

```
operator CSize();
```

### <a name="return-value"></a>Wartość zwracana

Bieżąca wartość rozmiaru D2D.

## <a name="see-also"></a>Zobacz też

[Klasy](../../mfc/reference/mfc-classes.md)
