---
description: 'Dowiedz się więcej na temat: Klasa CComSimpleThreadAllocator'
title: Klasa CComSimpleThreadAllocator
ms.date: 11/04/2016
f1_keywords:
- CComSimpleThreadAllocator
- ATLBASE/ATL::CComSimpleThreadAllocator
- ATLBASE/ATL::CComSimpleThreadAllocator::GetThread
helpviewer_keywords:
- threading [ATL], selecting threads
- ATL threads
- CComSimpleThreadAllocator class
- ATL threads, allocating
ms.assetid: 66b2166a-8c50-49fd-b8e4-7f293470327d
ms.openlocfilehash: 5925707ecd459475d9e9002af76fb76dd9cf9d38
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97142190"
---
# <a name="ccomsimplethreadallocator-class"></a>Klasa CComSimpleThreadAllocator

Ta klasa zarządza wyborem wątku dla klasy `CComAutoThreadModule` .

## <a name="syntax"></a>Składnia

```
class CComSimpleThreadAllocator
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CComSimpleThreadAllocator:: GetThread](#getthread)|Wybiera wątek.|

## <a name="remarks"></a>Uwagi

`CComSimpleThreadAllocator` zarządza wyborem wątku dla [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md). `CComSimpleThreadAllocator::GetThread` po prostu przechodzi przez każdy wątek i zwraca następny z nich w sekwencji.

## <a name="requirements"></a>Wymagania

**Nagłówek:** atlbase. h

## <a name="ccomsimplethreadallocatorgetthread"></a><a name="getthread"></a> CComSimpleThreadAllocator:: GetThread

Wybiera wątek przez określenie następnego wątku w sekwencji.

```
int GetThread(CComApartment* /* pApt */, int nThreads);
```

### <a name="parameters"></a>Parametry

*pApt*<br/>
Nieużywane w domyślnej implementacji ATL.

*nThreads*<br/>
Maksymalna liczba wątków w module EXE.

### <a name="return-value"></a>Wartość zwracana

Liczba całkowita z zakresu od 0 do (*nThreads* -1). Identyfikuje jeden z wątków w module EXE.

### <a name="remarks"></a>Uwagi

Można przesłonić, `GetThread` Aby zapewnić inną metodę wyboru lub użyć parametru *pApt* .

`GetThread` jest wywoływany przez [CComAutoThreadModule:: CreateInstance](../../atl/reference/ccomautothreadmodule-class.md#createinstance).

## <a name="see-also"></a>Zobacz też

[Klasa CComApartment](../../atl/reference/ccomapartment-class.md)<br/>
[Przegląd klas](../../atl/atl-class-overview.md)
