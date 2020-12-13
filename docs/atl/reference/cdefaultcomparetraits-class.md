---
description: 'Dowiedz się więcej na temat: Klasa CDefaultCompareTraits'
title: Klasa CDefaultCompareTraits
ms.date: 11/04/2016
f1_keywords:
- CDefaultCompareTraits
- ATLCOLL/ATL::CDefaultCompareTraits
- ATLCOLL/ATL::CDefaultCompareTraits::CompareElements
- ATLCOLL/ATL::CDefaultCompareTraits::CompareElementsOrdered
helpviewer_keywords:
- CDefaultCompareTraits class
ms.assetid: a17e2740-e7b4-48f2-aeb7-c80ce84b63f7
ms.openlocfilehash: dcb366cdcd99a6eed2b641be290ccc4913a81476
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97141911"
---
# <a name="cdefaultcomparetraits-class"></a>Klasa CDefaultCompareTraits

Ta klasa zapewnia domyślne funkcje porównywania elementów.

## <a name="syntax"></a>Składnia

```
template<typename T>
class CDefaultCompareTraits
```

#### <a name="parameters"></a>Parametry

*T*<br/>
Typ danych, które mają być przechowywane w kolekcji.

## <a name="members"></a>Elementy członkowskie

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CDefaultCompareTraits::CompareElements](#compareelements)|Ruchom Wywołaj tę funkcję, aby porównać dwa elementy dla równości.|
|[CDefaultCompareTraits::CompareElementsOrdered](#compareelementsordered)|Ruchom Wywołaj tę funkcję, aby określić większy i mniejszy element.|

## <a name="remarks"></a>Uwagi

Ta klasa zawiera dwie statyczne funkcje do porównywania elementów przechowywanych w obiekcie klasy kolekcji. Ta klasa jest wykorzystywana przez [klasę CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md).

Aby uzyskać więcej informacji, zobacz [klasy kolekcji ATL](../../atl/atl-collection-classes.md).

## <a name="requirements"></a>Wymagania

**Nagłówek:** atlcoll. h

## <a name="cdefaultcomparetraitscompareelements"></a><a name="compareelements"></a> CDefaultCompareTraits::CompareElements

Wywołaj tę funkcję, aby porównać dwa elementy dla równości.

```
static bool CompareElements(const T& element1, const T& element2);
```

### <a name="parameters"></a>Parametry

*element1*<br/>
Pierwszy element.

*element2*<br/>
Drugi element.

### <a name="return-value"></a>Wartość zwracana

Zwraca wartość true, jeśli elementy są równe, w przeciwnym razie false.

### <a name="remarks"></a>Uwagi

Domyślną implementacją tej funkcji jest operator równości ( **==** ). W przypadku obiektów innych niż proste typy danych ta funkcja może wymagać przesłaniania.

## <a name="cdefaultcomparetraitscompareelementsordered"></a><a name="compareelementsordered"></a> CDefaultCompareTraits::CompareElementsOrdered

Wywołaj tę funkcję, aby określić większy i mniejszy element.

```
static int CompareElementsOrdered(const T& element1, const T& element2);
```

### <a name="parameters"></a>Parametry

*element1*<br/>
Pierwszy element.

*element2*<br/>
Drugi element.

### <a name="return-value"></a>Wartość zwracana

Zwraca liczbę całkowitą na podstawie następującej tabeli:

|Warunek|Wartość zwracana|
|---------------|------------------|
|*element1*  <  *element2*|<0|
|*element1*  ==  *element2*|0|
|*element1*  >  *element2*|>0|

### <a name="remarks"></a>Uwagi

Domyślna implementacja tej funkcji używa **==** **\<**, and **>** operatorów. W przypadku obiektów innych niż proste typy danych ta funkcja może wymagać przesłaniania.

## <a name="see-also"></a>Zobacz też

[Przegląd klas](../../atl/atl-class-overview.md)
