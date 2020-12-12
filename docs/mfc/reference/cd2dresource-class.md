---
description: 'Dowiedz się więcej na temat: Klasa CD2DResource'
title: Klasa CD2DResource
ms.date: 03/27/2019
f1_keywords:
- CD2DResource
- AFXRENDERTARGET/CD2DResource
- AFXRENDERTARGET/CD2DResource::CD2DResource
- AFXRENDERTARGET/CD2DResource::Create
- AFXRENDERTARGET/CD2DResource::Destroy
- AFXRENDERTARGET/CD2DResource::IsValid
- AFXRENDERTARGET/CD2DResource::IsAutoDestroy
- AFXRENDERTARGET/CD2DResource::ReCreate
- AFXRENDERTARGET/CD2DResource::m_bIsAutoDestroy
- AFXRENDERTARGET/CD2DResource::m_pParentTarget
helpviewer_keywords:
- CD2DResource [MFC], CD2DResource
- CD2DResource [MFC], Create
- CD2DResource [MFC], Destroy
- CD2DResource [MFC], IsValid
- CD2DResource [MFC], IsAutoDestroy
- CD2DResource [MFC], ReCreate
- CD2DResource [MFC], m_bIsAutoDestroy
- CD2DResource [MFC], m_pParentTarget
ms.assetid: 34e3ee18-aab6-4c39-9294-de869e1f7820
ms.openlocfilehash: a110732a7e2bde5ab2fb3b6025acf98d6a3278c6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97118735"
---
# <a name="cd2dresource-class"></a>Klasa CD2DResource

Klasa abstrakcyjna, która udostępnia interfejs do tworzenia zasobów D2D i zarządzania nimi, takich jak pędzle, warstwy i teksty.

## <a name="syntax"></a>Składnia

```
class CD2DResource : public CObject;
```

## <a name="members"></a>Elementy członkowskie

### <a name="protected-constructors"></a>Konstruktory chronione

|Nazwa|Opis|
|----------|-----------------|
|[CD2DResource::CD2DResource](#cd2dresource)|Konstruuje obiekt CD2DResource.|
|[CD2DResource:: ~ CD2DResource](#_dtorcd2dresource)|Destruktor. Wywołuje się, gdy obiekt zasobów D2D jest niszczony.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CD2DResource:: Create](#create)|Tworzy element CD2DResource.|
|[CD2DResource::D Estroy](#destroy)|Niszczy obiekt CD2DResource.|
|[CD2DResource:: IsValid](#isvalid)|Sprawdza poprawność zasobów|

### <a name="protected-methods"></a>Metody chronione

|Nazwa|Opis|
|----------|-----------------|
|[CD2DResource::IsAutoDestroy](#isautodestroy)|Sprawdź flagę autoniszczenia.|
|[CD2DResource:: Recreate](#recreate)|Tworzy ponowną CD2DResource.|

### <a name="protected-data-members"></a>Chronione elementy członkowskie danych

|Nazwa|Opis|
|----------|-----------------|
|[CD2DResource:: m_bIsAutoDestroy](#m_bisautodestroy)|Zasób zostanie zniszczony przez właściciela (CRenderTarget)|
|[CD2DResource:: m_pParentTarget](#m_pparenttarget)|Wskaźnik do elementu nadrzędnego CRenderTarget)|

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

`CD2DResource`

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxrendertarget. h

## <a name="cd2dresourcecd2dresource"></a><a name="_dtorcd2dresource"></a> CD2DResource:: ~ CD2DResource

Destruktor. Wywołuje się, gdy obiekt zasobów D2D jest niszczony.

```
virtual ~CD2DResource();
```

## <a name="cd2dresourcecd2dresource"></a><a name="cd2dresource"></a> CD2DResource::CD2DResource

Konstruuje obiekt CD2DResource.

```
CD2DResource(
    CRenderTarget* pParentTarget,
    BOOL bAutoDestroy);
```

### <a name="parameters"></a>Parametry

*pParentTarget*<br/>
Wskaźnik do elementu docelowego renderowania.

*bAutoDestroy*<br/>
Wskazuje, że obiekt zostanie zniszczony przez właściciela (pParentTarget).

## <a name="cd2dresourcecreate"></a><a name="create"></a> CD2DResource:: Create

Tworzy element CD2DResource.

```
virtual HRESULT Create(CRenderTarget* pRenderTarget) = 0;
```

### <a name="parameters"></a>Parametry

*pRenderTarget*<br/>
Wskaźnik do elementu docelowego renderowania.

### <a name="return-value"></a>Wartość zwracana

Jeśli metoda się powiedzie, zwraca S_OK. W przeciwnym razie zwraca kod błędu HRESULT.

## <a name="cd2dresourcedestroy"></a><a name="destroy"></a> CD2DResource::D Estroy

Niszczy obiekt CD2DResource.

```
virtual void Destroy() = 0;
```

## <a name="cd2dresourceisautodestroy"></a><a name="isautodestroy"></a> CD2DResource::IsAutoDestroy

Sprawdź flagę autoniszczenia.

```
BOOL IsAutoDestroy() const;
```

### <a name="return-value"></a>Wartość zwracana

TRUE, jeśli obiekt zostanie zniszczony przez jego właściciela; w przeciwnym razie FALSE.

## <a name="cd2dresourceisvalid"></a><a name="isvalid"></a> CD2DResource:: IsValid

Sprawdza poprawność zasobów

```
virtual BOOL IsValid() const = 0;
```

### <a name="return-value"></a>Wartość zwracana

PRAWDA, jeśli zasób jest prawidłowy; w przeciwnym razie FALSE.

## <a name="cd2dresourcem_bisautodestroy"></a><a name="m_bisautodestroy"></a> CD2DResource:: m_bIsAutoDestroy

Zasób zostanie zniszczony przez właściciela (CRenderTarget)

```
BOOL m_bIsAutoDestroy;
```

## <a name="cd2dresourcem_pparenttarget"></a><a name="m_pparenttarget"></a> CD2DResource:: m_pParentTarget

Wskaźnik do elementu nadrzędnego CRenderTarget)

```
CRenderTarget* m_pParentTarget;
```

## <a name="cd2dresourcerecreate"></a><a name="recreate"></a> CD2DResource:: Recreate

Tworzy ponowną CD2DResource.

```
virtual HRESULT ReCreate(CRenderTarget* pRenderTarget);
```

### <a name="parameters"></a>Parametry

*pRenderTarget*<br/>
Wskaźnik do elementu docelowego renderowania.

### <a name="return-value"></a>Wartość zwracana

Jeśli metoda się powiedzie, zwraca S_OK. W przeciwnym razie zwraca kod błędu HRESULT.

## <a name="see-also"></a>Zobacz też

[Klasy](../../mfc/reference/mfc-classes.md)
