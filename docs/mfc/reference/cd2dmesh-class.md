---
description: 'Dowiedz się więcej na temat: Klasa CD2DMesh'
title: Klasa CD2DMesh
ms.date: 11/04/2016
f1_keywords:
- CD2DMesh
- AFXRENDERTARGET/CD2DMesh
- AFXRENDERTARGET/CD2DMesh::CD2DMesh
- AFXRENDERTARGET/CD2DMesh::Attach
- AFXRENDERTARGET/CD2DMesh::Create
- AFXRENDERTARGET/CD2DMesh::Destroy
- AFXRENDERTARGET/CD2DMesh::Detach
- AFXRENDERTARGET/CD2DMesh::Get
- AFXRENDERTARGET/CD2DMesh::IsValid
- AFXRENDERTARGET/CD2DMesh::Open
- AFXRENDERTARGET/CD2DMesh::m_pMesh
helpviewer_keywords:
- CD2DMesh [MFC], CD2DMesh
- CD2DMesh [MFC], Attach
- CD2DMesh [MFC], Create
- CD2DMesh [MFC], Destroy
- CD2DMesh [MFC], Detach
- CD2DMesh [MFC], Get
- CD2DMesh [MFC], IsValid
- CD2DMesh [MFC], Open
- CD2DMesh [MFC], m_pMesh
ms.assetid: 11a2c78a-1367-40e8-a34f-44aa0509a4c9
ms.openlocfilehash: fbdb941d04b87df5c136f1925445564caab63443
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97193373"
---
# <a name="cd2dmesh-class"></a>Klasa CD2DMesh

Otoka dla ID2D1Mesh.

## <a name="syntax"></a>Składnia

```
class CD2DMesh : public CD2DResource;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CD2DMesh::CD2DMesh](#cd2dmesh)|Konstruuje obiekt CD2DMesh.|
|[CD2DMesh:: ~ CD2DMesh](#_dtorcd2dmesh)|Destruktor. Wywoływana, gdy trwa niszczenie obiektu siatki D2D.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CD2DMesh:: Attach](#attach)|Dołącza istniejący interfejs zasobów do obiektu|
|[CD2DMesh:: Create](#create)|Tworzy element CD2DMesh. (Przesłania [CD2DResource:: Create](../../mfc/reference/cd2dresource-class.md#create).)|
|[CD2DMesh::D Estroy](#destroy)|Niszczy obiekt CD2DMesh. (Przesłania [CD2DResource::D Estroy](../../mfc/reference/cd2dresource-class.md#destroy).)|
|[CD2DMesh::D etach](#detach)|Odłącza interfejs zasobów od obiektu|
|[CD2DMesh:: Get](#get)|Zwraca interfejs ID2D1Mesh|
|[CD2DMesh:: IsValid](#isvalid)|Sprawdza poprawność zasobów (Przesłania [CD2DResource:: IsValid](../../mfc/reference/cd2dresource-class.md#isvalid)).|
|[CD2DMesh:: Open](#open)|Otwiera siatkę do wypełniania.|

### <a name="public-operators"></a>Operatory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CD2DMesh:: operator ID2D1Mesh *](#operator_id2d1mesh_star)|Zwraca interfejs ID2D1Mesh|

### <a name="protected-data-members"></a>Chronione elementy członkowskie danych

|Nazwa|Opis|
|----------|-----------------|
|[CD2DMesh:: m_pMesh](#m_pmesh)|Wskaźnik do elementu ID2D1Mesh.|

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CD2DResource](../../mfc/reference/cd2dresource-class.md)

`CD2DMesh`

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxrendertarget. h

## <a name="cd2dmeshcd2dmesh"></a><a name="_dtorcd2dmesh"></a> CD2DMesh:: ~ CD2DMesh

Destruktor. Wywoływana, gdy trwa niszczenie obiektu siatki D2D.

```
virtual ~CD2DMesh();
```

## <a name="cd2dmeshattach"></a><a name="attach"></a> CD2DMesh:: Attach

Dołącza istniejący interfejs zasobów do obiektu

```cpp
void Attach(ID2D1Mesh* pResource);
```

### <a name="parameters"></a>Parametry

*Źródło*<br/>
Istniejący interfejs zasobów. Nie może mieć wartości NULL

## <a name="cd2dmeshcd2dmesh"></a><a name="cd2dmesh"></a> CD2DMesh::CD2DMesh

Konstruuje obiekt CD2DMesh.

```
CD2DMesh(
    CRenderTarget* pParentTarget,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>Parametry

*pParentTarget*<br/>
Wskaźnik do elementu docelowego renderowania.

*bAutoDestroy*<br/>
Wskazuje, że obiekt zostanie zniszczony przez właściciela (pParentTarget).

## <a name="cd2dmeshcreate"></a><a name="create"></a> CD2DMesh:: Create

Tworzy element CD2DMesh.

```
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```

### <a name="parameters"></a>Parametry

*pRenderTarget*<br/>
Wskaźnik do elementu docelowego renderowania.

### <a name="return-value"></a>Wartość zwracana

Jeśli metoda się powiedzie, zwraca S_OK. W przeciwnym razie zwraca kod błędu HRESULT.

## <a name="cd2dmeshdestroy"></a><a name="destroy"></a> CD2DMesh::D Estroy

Niszczy obiekt CD2DMesh.

```
virtual void Destroy();
```

## <a name="cd2dmeshdetach"></a><a name="detach"></a> CD2DMesh::D etach

Odłącza interfejs zasobów od obiektu

```
ID2D1Mesh* Detach();
```

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do odłączonego interfejsu zasobu.

## <a name="cd2dmeshget"></a><a name="get"></a> CD2DMesh:: Get

Zwraca interfejs ID2D1Mesh

```
ID2D1Mesh* Get();
```

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do interfejsu ID2D1Mesh lub NULL, jeśli obiekt nie jest jeszcze zainicjowany.

## <a name="cd2dmeshisvalid"></a><a name="isvalid"></a> CD2DMesh:: IsValid

Sprawdza poprawność zasobów

```
virtual BOOL IsValid() const;
```

### <a name="return-value"></a>Wartość zwracana

PRAWDA, jeśli zasób jest prawidłowy; w przeciwnym razie FALSE.

## <a name="cd2dmeshm_pmesh"></a><a name="m_pmesh"></a> CD2DMesh:: m_pMesh

Wskaźnik do elementu ID2D1Mesh.

```
ID2D1Mesh* m_pMesh;
```

## <a name="cd2dmeshopen"></a><a name="open"></a> CD2DMesh:: Open

Otwiera siatkę do wypełniania.

```
ID2D1TessellationSink* Open();
```

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do elementu ID2D1TessellationSink, który jest używany do wypełniania siatki.

## <a name="cd2dmeshoperator-id2d1mesh"></a><a name="operator_id2d1mesh_star"></a> CD2DMesh:: operator ID2D1Mesh *

Zwraca interfejs ID2D1Mesh

```
operator ID2D1Mesh*();
```

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do interfejsu ID2D1Mesh lub NULL, jeśli obiekt nie jest jeszcze zainicjowany.

## <a name="see-also"></a>Zobacz też

[Klasy](../../mfc/reference/mfc-classes.md)
