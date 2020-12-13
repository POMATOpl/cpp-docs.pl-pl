---
description: 'Dowiedz się więcej na temat: Klasa CMFCAcceleratorKey'
title: Klasa CMFCAcceleratorKey
ms.date: 11/04/2016
f1_keywords:
- CMFCAcceleratorKey
- AFXACCELERATORKEY/CMFCAcceleratorKey
- AFXACCELERATORKEY/CMFCAcceleratorKey::CMFCAcceleratorKey
- AFXACCELERATORKEY/CMFCAcceleratorKey::Format
- AFXACCELERATORKEY/CMFCAcceleratorKey::SetAccelerator
helpviewer_keywords:
- CMFCAcceleratorKey [MFC], CMFCAcceleratorKey
- CMFCAcceleratorKey [MFC], Format
- CMFCAcceleratorKey [MFC], SetAccelerator
ms.assetid: d140fbf7-23db-45ea-a63e-414a5ec7b3d5
ms.openlocfilehash: cb7fc24c4cb4d092c5f109ad892b3778d74a906f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336621"
---
# <a name="cmfcacceleratorkey-class"></a>Klasa CMFCAcceleratorKey

Klasa pomocnika, która implementuje mapowanie i formatowanie kluczy wirtualnych.

## <a name="syntax"></a>Składnia

```
class CMFCAcceleratorKey : public CObject
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CMFCAcceleratorKey::CMFCAcceleratorKey](#cmfcacceleratorkey)|Konstruuje `CMFCAcceleratorKey` obiekt.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CMFCAcceleratorKey:: format](#format)|Tłumaczy strukturę akceleracja na swoją reprezentację wizualną.|
|[CMFCAcceleratorKey:: SetAccelerator](#setaccelerator)|Ustawia klawisz skrótu dla `CMFCAcceleratorKey` obiektu.|

## <a name="remarks"></a>Uwagi

Klucze akceleratora są również znane jako klawisze skrótów. Jeśli chcesz wyświetlić skróty klawiaturowe wprowadzane przez użytkownika, [Klasa CMFCAcceleratorKeyAssignCtrl](../../mfc/reference/cmfcacceleratorkeyassignctrl-class.md) mapuje skróty klawiaturowe, takie jak Alt + Shift + s, do niestandardowego formatu tekstu, takiego jak "Alt + Shift + S". Każdy `CMFCAcceleratorKey` obiekt mapuje jeden klawisz skrótu do formatu tekstowego.

Aby uzyskać więcej informacji na temat używania klawiszy skrótów i tabel akceleratorów, zobacz [Klasa CKeyboardManager](../../mfc/reference/ckeyboardmanager-class.md).

## <a name="example"></a>Przykład

Poniższy przykład ilustruje sposób konstruowania `CMFCAcceleratorKey` obiektu i sposobu użycia jego `Format` metody.

[!code-cpp[NVC_MFC_RibbonApp#30](../../mfc/reference/codesnippet/cpp/cmfcacceleratorkey-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

`CMFCAcceleratorKey`

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxacceleratorkey. h

## <a name="cmfcacceleratorkeycmfcacceleratorkey"></a><a name="cmfcacceleratorkey"></a> CMFCAcceleratorKey::CMFCAcceleratorKey

Konstruuje obiekt [CMFCAcceleratorKey](../../mfc/reference/cmfcacceleratorkey-class.md) .

```
CMFCAcceleratorKey();
CMFCAcceleratorKey(LPACCEL lpAccel);
```

### <a name="parameters"></a>Parametry

*lpAccel*<br/>
podczas Wskaźnik do klawisza skrótu.

### <a name="remarks"></a>Uwagi

Jeśli nie podasz klawisza skrótu podczas tworzenia `CMFCAccleratorKey` , użyj metody [CMFCAcceleratorKey:: SetAccelerator](#setaccelerator) , aby skojarzyć klawisz skrótu z `CMFCAcceleratorKey` obiektem.

## <a name="cmfcacceleratorkeyformat"></a><a name="format"></a> CMFCAcceleratorKey:: format

Tłumaczy strukturę akceleracja na skojarzoną wartość ciągu.

```cpp
void Format(CString& str) const;
```

### <a name="parameters"></a>Parametry

*str*<br/>
określoną Odwołanie do `CString` obiektu, w którym Metoda zapisuje przetłumaczony klawisz skrótu.

### <a name="remarks"></a>Uwagi

Ta metoda pobiera format ciągu skojarzonego klawisza skrótu. Można ustawić format ciągu obiektu [CMFCAcceleratorKey](../../mfc/reference/cmfcacceleratorkey-class.md) przy użyciu konstruktora lub metody [CMFCAcceleratorKey:: SetAccelerator](#setaccelerator).

## <a name="cmfcacceleratorkeysetaccelerator"></a><a name="setaccelerator"></a> CMFCAcceleratorKey:: SetAccelerator

Ustawia klawisz skrótu dla obiektu [CMFCAcceleratorKey](../../mfc/reference/cmfcacceleratorkey-class.md) .

```cpp
void SetAccelerator(LPACCEL lpAccel);
```

### <a name="parameters"></a>Parametry

*lpAccel*<br/>
podczas Wskaźnik do klawisza skrótu.

### <a name="remarks"></a>Uwagi

Użyj tej metody, aby ustawić klawisz skrótu dla, `CMFCAcceleratorKey` Jeśli nie podano klawisza skrótu podczas tworzenia `CMFCAcceleratorKey` .

## <a name="see-also"></a>Zobacz też

[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasy](../../mfc/reference/mfc-classes.md)<br/>
[Klasa CKeyboardManager](../../mfc/reference/ckeyboardmanager-class.md)
