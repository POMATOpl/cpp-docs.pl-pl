---
description: 'Dowiedz się więcej na temat: Klasa CBaseKeyFrame'
title: Klasa CBaseKeyFrame
ms.date: 11/04/2016
f1_keywords:
- CBaseKeyFrame
- AFXANIMATIONCONTROLLER/CBaseKeyFrame
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::CBaseKeyFrame
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::AddToStoryboard
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::GetAnimationKeyframe
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::IsAdded
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::IsKeyframeAtOffset
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::m_bAdded
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::m_bIsKeyframeAtOffset
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::m_keyframe
helpviewer_keywords:
- CBaseKeyFrame [MFC], CBaseKeyFrame
- CBaseKeyFrame [MFC], AddToStoryboard
- CBaseKeyFrame [MFC], GetAnimationKeyframe
- CBaseKeyFrame [MFC], IsAdded
- CBaseKeyFrame [MFC], IsKeyframeAtOffset
- CBaseKeyFrame [MFC], m_bAdded
- CBaseKeyFrame [MFC], m_bIsKeyframeAtOffset
- CBaseKeyFrame [MFC], m_keyframe
ms.assetid: 285a2eff-e7c4-43be-b5aa-737727e6866d
ms.openlocfilehash: 0bebd91183eab9be71e8df4928dc621565718cb9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97261260"
---
# <a name="cbasekeyframe-class"></a>Klasa CBaseKeyFrame

Implementuje podstawowe funkcje klatki kluczowej.

## <a name="syntax"></a>Składnia

```
class CBaseKeyFrame : public CObject;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CBaseKeyFrame::CBaseKeyFrame](#cbasekeyframe)|Konstruuje obiekt klatki kluczowej.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CBaseKeyFrame::AddToStoryboard](#addtostoryboard)|Dodaje klatkę kluczową do scenorysu.|
|[CBaseKeyFrame::GetAnimationKeyframe](#getanimationkeyframe)|Zwraca podstawową wartość klatki kluczowej.|
|[CBaseKeyFrame:: isdodał](#isadded)|Wskazuje, czy dodano klatkę kluczową do scenorysu.|
|[CBaseKeyFrame::IsKeyframeAtOffset](#iskeyframeatoffset)|Określa, czy klatka kluczowa powinna zostać dodana do scenorysu przy przesunięciu, czy po przejściu.|

### <a name="protected-data-members"></a>Chronione elementy członkowskie danych

|Nazwa|Opis|
|----------|-----------------|
|[CBaseKeyFrame:: m_bAdded](#m_badded)|Określa, czy ta klatka kluczowa została dodana do scenorysu.|
|[CBaseKeyFrame:: m_bIsKeyframeAtOffset](#m_biskeyframeatoffset)|Określa, czy ta klatka kluczowa powinna zostać dodana do scenorysu przy przesunięciu z innej istniejącej klatki kluczowej lub na końcu pewnego przejścia.|
|[CBaseKeyFrame:: m_keyframe](#m_keyframe)|Reprezentuje klatkę kluczową interfejsu API animacji systemu Windows. Gdy klatka kluczowa nie jest zainicjowana, jest ustawiona na wstępnie zdefiniowaną wartość UI_ANIMATION_KEYFRAME_STORYBOARD_START.|

## <a name="remarks"></a>Uwagi

Hermetyzuje UI_ANIMATION_KEYFRAME zmienną. Służy jako klasa bazowa dla każdej implementacji klatki kluczowej. Klatka kluczowa reprezentuje moment w czasie w ciągu scenorysu i może służyć do określenia czasu rozpoczęcia i zakończenia przejścia. Istnieją dwa typy klatek kluczowych — klatki kluczowe dodawane do scenorysu w określonym przesunięciu (w czasie) lub ramki kluczowe dodane po określonym przejściu. Ponieważ czasy trwania niektórych przejść nie są znane przed rozpoczęciem animacji, rzeczywiste wartości niektórych klatek kluczowych są określane tylko w czasie wykonywania. Ponieważ ramki kluczowe mogą zależeć od przejść, które z kolei zależą od klatek kluczowych, ważne jest, aby zapobiec nieskończonym replikom podczas kompilowania łańcuchów klatek kluczowych.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

`CBaseKeyFrame`

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxanimationcontroller. h

## <a name="cbasekeyframeaddtostoryboard"></a><a name="addtostoryboard"></a> CBaseKeyFrame::AddToStoryboard

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
Jeśli ten parametr ma wartość TRUE, a dodawana ramka kluczowa jest zależna od innej klatki kluczowej lub przejścia, ta metoda próbuje dodać tę klatkę kluczową lub przejść najpierw do scenorysu.

### <a name="return-value"></a>Wartość zwracana

PRAWDA, jeśli klatka kluczowa została pomyślnie dodana do scenorysu; w przeciwnym razie FALSE.

### <a name="remarks"></a>Uwagi

Ta metoda jest wywoływana, aby dodać klatkę kluczową do scenorysu.

## <a name="cbasekeyframecbasekeyframe"></a><a name="cbasekeyframe"></a> CBaseKeyFrame::CBaseKeyFrame

Konstruuje obiekt klatki kluczowej.

```
CBaseKeyFrame();
```

## <a name="cbasekeyframegetanimationkeyframe"></a><a name="getanimationkeyframe"></a> CBaseKeyFrame::GetAnimationKeyframe

Zwraca podstawową wartość klatki kluczowej.

```
UI_ANIMATION_KEYFRAME GetAnimationKeyframe() const;
```

### <a name="return-value"></a>Wartość zwracana

Bieżąca klatka kluczowa. Wartość domyślna to UI_ANIMATION_KEYFRAME_STORYBOARD_START.

### <a name="remarks"></a>Uwagi

Jest to metoda dostępu do bazowej wartości klatki kluczowej.

## <a name="cbasekeyframeisadded"></a><a name="isadded"></a> CBaseKeyFrame:: isdodał

Wskazuje, czy dodano klatkę kluczową do scenorysu.

```
BOOL IsAdded() const;
```

### <a name="return-value"></a>Wartość zwracana

PRAWDA, jeśli klatka kluczowa jest dodawana do scenorysu; otehrwise FALSE.

### <a name="remarks"></a>Uwagi

W klasie bazowej isdodana zawsze zwraca wartość TRUE, ale jest zastępowany w klasach pochodnych.

## <a name="cbasekeyframeiskeyframeatoffset"></a><a name="iskeyframeatoffset"></a> CBaseKeyFrame::IsKeyframeAtOffset

Określa, czy klatka kluczowa powinna zostać dodana do scenorysu przy przesunięciu, czy po przejściu.

```
BOOL IsKeyframeAtOffset() const;
```

### <a name="return-value"></a>Wartość zwracana

Ma wartość TRUE, jeśli klatka kluczowa powinna zostać dodana do scenorysu w określonym przesunięciu. FAŁSZ, jeśli klatka kluczowa powinna zostać dodana do scenorysu po pewnym przejściu.

### <a name="remarks"></a>Uwagi

Określa, czy klatka kluczowa powinna zostać dodana do scenorysu przy przesunięciu. Przesunięcie lub przejście musi być określone w klasie pochodnej.

## <a name="cbasekeyframem_badded"></a><a name="m_badded"></a> CBaseKeyFrame:: m_bAdded

Określa, czy ta klatka kluczowa została dodana do scenorysu.

```
BOOL m_bAdded;
```

## <a name="cbasekeyframem_biskeyframeatoffset"></a><a name="m_biskeyframeatoffset"></a> CBaseKeyFrame:: m_bIsKeyframeAtOffset

Określa, czy ta klatka kluczowa powinna zostać dodana do scenorysu przy przesunięciu z innej istniejącej klatki kluczowej lub na końcu pewnego przejścia.

```
BOOL m_bIsKeyframeAtOffset;
```

## <a name="cbasekeyframem_keyframe"></a><a name="m_keyframe"></a> CBaseKeyFrame:: m_keyframe

Reprezentuje klatkę kluczową interfejsu API animacji systemu Windows. Gdy klatka kluczowa nie jest zainicjowana, jest ustawiona na wstępnie zdefiniowaną wartość UI_ANIMATION_KEYFRAME_STORYBOARD_START.

```
UI_ANIMATION_KEYFRAME m_keyframe;
```

## <a name="see-also"></a>Zobacz też

[Klasy](../../mfc/reference/mfc-classes.md)
