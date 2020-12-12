---
description: 'Dowiedz się więcej na temat: Klasa CKeyFrame'
title: Klasa CKeyFrame
ms.date: 11/04/2016
f1_keywords:
- CKeyFrame
- AFXANIMATIONCONTROLLER/CKeyFrame
- AFXANIMATIONCONTROLLER/CKeyFrame::CKeyFrame
- AFXANIMATIONCONTROLLER/CKeyFrame::AddToStoryboard
- AFXANIMATIONCONTROLLER/CKeyFrame::AddToStoryboardAfterTransition
- AFXANIMATIONCONTROLLER/CKeyFrame::AddToStoryboardAtOffset
- AFXANIMATIONCONTROLLER/CKeyFrame::GetExistingKeyframe
- AFXANIMATIONCONTROLLER/CKeyFrame::GetOffset
- AFXANIMATIONCONTROLLER/CKeyFrame::GetTransition
- AFXANIMATIONCONTROLLER/CKeyFrame::m_offset
- AFXANIMATIONCONTROLLER/CKeyFrame::m_pExistingKeyFrame
- AFXANIMATIONCONTROLLER/CKeyFrame::m_pTransition
helpviewer_keywords:
- CKeyFrame [MFC], CKeyFrame
- CKeyFrame [MFC], AddToStoryboard
- CKeyFrame [MFC], AddToStoryboardAfterTransition
- CKeyFrame [MFC], AddToStoryboardAtOffset
- CKeyFrame [MFC], GetExistingKeyframe
- CKeyFrame [MFC], GetOffset
- CKeyFrame [MFC], GetTransition
- CKeyFrame [MFC], m_offset
- CKeyFrame [MFC], m_pExistingKeyFrame
- CKeyFrame [MFC], m_pTransition
ms.assetid: d050a562-20f6-4c65-8ce5-ccb3aef1a20e
ms.openlocfilehash: ec6aa45484965afbf0c636a1eed26a3d4a63e426
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97236883"
---
# <a name="ckeyframe-class"></a>Klasa CKeyFrame

Reprezentuje klatkę kluczową animacji.

## <a name="syntax"></a>Składnia

```
class CKeyFrame : public CBaseKeyFrame;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CKeyFrame::CKeyFrame](#ckeyframe)|Przeciążone. Konstruuje klatkę kluczową, która zależy od innej klatki kluczowej.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CKeyFrame::AddToStoryboard](#addtostoryboard)|Dodaje klatkę kluczową do scenorysu. (Przesłania [CBaseKeyFrame:: AddToStoryboard](../../mfc/reference/cbasekeyframe-class.md#addtostoryboard).)|
|[CKeyFrame::AddToStoryboardAfterTransition](#addtostoryboardaftertransition)|Dodaje klatkę kluczową do scenorysu po przejściu.|
|[CKeyFrame::AddToStoryboardAtOffset](#addtostoryboardatoffset)|Dodaje klatkę kluczową do scenorysu przy przesunięciu.|
|[CKeyFrame::GetExistingKeyframe](#getexistingkeyframe)|Zwraca wskaźnik do klatki kluczowej, od której zależy ta klatka kluczowa.|
|[CKeyFrame:: GetOffset](#getoffset)|Zwraca przesunięcie z innej klatki kluczowej.|
|[CKeyFrame:: gettransition](#gettransition)|Zwraca wskaźnik do przejścia, od którego zależy ta klatka kluczowa.|

### <a name="protected-data-members"></a>Chronione elementy członkowskie danych

|Nazwa|Opis|
|----------|-----------------|
|[CKeyFrame:: m_offset](#m_offset)|Określa przesunięcie tej klatki kluczowej z klatki kluczowej przechowywanej w m_pExistingKeyFrame.|
|[CKeyFrame:: m_pExistingKeyFrame](#m_pexistingkeyframe)|Przechowuje wskaźnik do istniejącej keframe. Ta klatka kluczowa jest dodawana do scenorysu z m_offset do istniejącej klatki kluczowej.|
|[CKeyFrame:: m_pTransition](#m_ptransition)|Przechowuje wskaźnik do przechowania, który rozpoczyna się od tej klatki kluczowej.|

## <a name="remarks"></a>Uwagi

Ta klasa implementuje klatkę kluczową animacji. Klatka kluczowa reprezentuje moment w czasie w ciągu scenorysu i może służyć do określenia czasu rozpoczęcia i zakończenia przejścia. Klatka kluczowa może opierać się na innej klatce kluczowej i mieć przesunięcie (w sekundach) od niej lub być zależne od przejścia i przedstawiać moment czasu zakończenia tego przejścia.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CBaseKeyFrame](../../mfc/reference/cbasekeyframe-class.md)

[CKeyFrame](../../mfc/reference/ckeyframe-class.md)

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxanimationcontroller. h

## <a name="ckeyframeaddtostoryboard"></a><a name="addtostoryboard"></a> CKeyFrame::AddToStoryboard

Dodaje klatkę kluczową do scenorysu.

```
virtual BOOL AddToStoryboard(
    IUIAnimationStoryboard* pStoryboard,
    BOOL bDeepAdd);
```

### <a name="parameters"></a>Parametry

*pStoryboard*<br/>
Wskaźnik do scenorysu.

*bDeepAdd*<br/>
Określa, czy dodać klatkę kluczową lub przejść cyklicznie.

### <a name="return-value"></a>Wartość zwracana

PRAWDA, jeśli klatka kluczowa została dodana pomyślnie.

### <a name="remarks"></a>Uwagi

Ta metoda dodaje klatkę kluczową do scenorysu. Jeśli jest to zależne od innej klatki kluczowej lub przejścia, a bDeepAdd ma wartość TRUE, ta metoda próbuje dodać je rekursywnie.

## <a name="ckeyframeaddtostoryboardaftertransition"></a><a name="addtostoryboardaftertransition"></a> CKeyFrame::AddToStoryboardAfterTransition

Dodaje klatkę kluczową do scenorysu po przejściu.

```
BOOL AddToStoryboardAfterTransition(
    IUIAnimationStoryboard* pStoryboard,
    BOOL bDeepAdd);
```

### <a name="parameters"></a>Parametry

*pStoryboard*<br/>
Wskaźnik do scenorysu.

*bDeepAdd*<br/>
Określa, czy dodać przejście cyklicznie.

### <a name="return-value"></a>Wartość zwracana

PRAWDA, jeśli klatka kluczowa została dodana pomyślnie.

### <a name="remarks"></a>Uwagi

Ta funkcja jest wywoływana przez platformę, aby dodać klatkę kluczową do scenorysu po przejściu.

## <a name="ckeyframeaddtostoryboardatoffset"></a><a name="addtostoryboardatoffset"></a> CKeyFrame::AddToStoryboardAtOffset

Dodaje klatkę kluczową do scenorysu przy przesunięciu.

```
virtual BOOL AddToStoryboardAtOffset(
    IUIAnimationStoryboard* pStoryboard,
    BOOL bDeepAdd);
```

### <a name="parameters"></a>Parametry

*pStoryboard*<br/>
Wskaźnik do scenorysu.

*bDeepAdd*<br/>
Określa, czy ma zostać dodana klatka kluczowa, która jest zależna od rekursywnie.

### <a name="return-value"></a>Wartość zwracana

PRAWDA, jeśli klatka kluczowa została dodana pomyślnie.

### <a name="remarks"></a>Uwagi

Ta funkcja jest wywoływana przez platformę, aby dodać klatkę kluczową do scenorysu przy przesunięciu.

## <a name="ckeyframeckeyframe"></a><a name="ckeyframe"></a> CKeyFrame::CKeyFrame

Konstruuje klatkę kluczową, która zależy od przejścia.

```
CKeyFrame(CBaseTransition* pTransition);

CKeyFrame(
    CBaseKeyFrame* pKeyframe,
    UI_ANIMATION_SECONDS offset = 0.0);
```

### <a name="parameters"></a>Parametry

*pTransition*<br/>
Wskaźnik do przejścia.

*pKeyframe*<br/>
Wskaźnik do klatki kluczowej.

*Przesunięcie*<br/>
Przesunięcie (w sekundach) od klatki kluczowej określonej przez pKeyframe.

### <a name="remarks"></a>Uwagi

Skonstruowana klatka kluczowa będzie reprezentować moment w ciągu scenorysu po zakończeniu określonego przejścia.

## <a name="ckeyframegetexistingkeyframe"></a><a name="getexistingkeyframe"></a> CKeyFrame::GetExistingKeyframe

Zwraca wskaźnik do klatki kluczowej, od której zależy ta klatka kluczowa.

```
CBaseKeyFrame* GetExistingKeyframe();
```

### <a name="return-value"></a>Wartość zwracana

Prawidłowy wskaźnik do klatki kluczowej lub wartość NULL, jeśli ta klatka kluczowa nie jest zależna od innej klatki kluczowej.

### <a name="remarks"></a>Uwagi

Jest to metoda dostępu do klatki kluczowej, od której zależy ta klatka kluczowa.

## <a name="ckeyframegetoffset"></a><a name="getoffset"></a> CKeyFrame:: GetOffset

Zwraca przesunięcie z innej klatki kluczowej.

```
UI_ANIMATION_SECONDS GetOffset();
```

### <a name="return-value"></a>Wartość zwracana

Przesunięcie w sekundach od innej klatki kluczowej.

### <a name="remarks"></a>Uwagi

Ta metoda powinna być wywoływana w celu określenia przesunięcia w sekundach od innej klatki kluczowej.

## <a name="ckeyframegettransition"></a><a name="gettransition"></a> CKeyFrame:: gettransition

Zwraca wskaźnik do przejścia, od którego zależy ta klatka kluczowa.

```
CBaseTransition* GetTransition();
```

### <a name="return-value"></a>Wartość zwracana

Prawidłowy wskaźnik do przejścia lub wartość NULL, jeśli ta klatka kluczowa nie zależy od przejścia.

### <a name="remarks"></a>Uwagi

Jest to metoda dostępu do przejścia, od którego zależy ta klatka kluczowa.

## <a name="ckeyframem_offset"></a><a name="m_offset"></a> CKeyFrame:: m_offset

Określa przesunięcie tej klatki kluczowej z klatki kluczowej przechowywanej w m_pExistingKeyFrame.

```
UI_ANIMATION_SECONDS m_offset;
```

## <a name="ckeyframem_pexistingkeyframe"></a><a name="m_pexistingkeyframe"></a> CKeyFrame:: m_pExistingKeyFrame

Przechowuje wskaźnik do istniejącej keframe. Ta klatka kluczowa jest dodawana do scenorysu z m_offset do istniejącej klatki kluczowej.

```
CBaseKeyFrame* m_pExistingKeyFrame;
```

## <a name="ckeyframem_ptransition"></a><a name="m_ptransition"></a> CKeyFrame:: m_pTransition

Przechowuje wskaźnik do przechowania, który rozpoczyna się od tej klatki kluczowej.

```
CBaseTransition* m_pTransition;
```

## <a name="see-also"></a>Zobacz też

[Klasy](../../mfc/reference/mfc-classes.md)
