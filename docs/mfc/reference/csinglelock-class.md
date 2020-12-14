---
description: 'Dowiedz się więcej na temat: Klasa CSingleLock'
title: Klasa CSingleLock
ms.date: 11/04/2016
f1_keywords:
- CSingleLock
- AFXMT/CSingleLock
- AFXMT/CSingleLock::CSingleLock
- AFXMT/CSingleLock::IsLocked
- AFXMT/CSingleLock::Lock
- AFXMT/CSingleLock::Unlock
helpviewer_keywords:
- CSingleLock [MFC], CSingleLock
- CSingleLock [MFC], IsLocked
- CSingleLock [MFC], Lock
- CSingleLock [MFC], Unlock
ms.assetid: 7dae7288-8066-4a3e-85e0-78d28bfc6bc8
ms.openlocfilehash: 7fa4fe32ce38bf47ede1b6ac133d1a057907f9c2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97342859"
---
# <a name="csinglelock-class"></a>Klasa CSingleLock

Reprezentuje mechanizm kontroli dostępu używany do kontrolowania dostępu do zasobu w programie wielowątkowym.

## <a name="syntax"></a>Składnia

```
class CSingleLock
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CSingleLock::CSingleLock](#csinglelock)|Konstruuje `CSingleLock` obiekt.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CSingleLock:: IsLocked](#islocked)|Określa, czy obiekt jest zablokowany.|
|[CSingleLock:: Lock](#lock)|Czeka na obiekt synchronizacji.|
|[CSingleLock:: Unlock](#unlock)|Zwalnia obiekt synchronizacji.|

## <a name="remarks"></a>Uwagi

`CSingleLock` nie ma klasy bazowej.

Aby można było używać klas synchronizacji [CSemaphore](../../mfc/reference/csemaphore-class.md), [CMutex](../../mfc/reference/cmutex-class.md), [CCriticalSection](../../mfc/reference/ccriticalsection-class.md)i [CEvent](../../mfc/reference/cevent-class.md), należy utworzyć `CSingleLock` obiekt a lub [CMultiLock](../../mfc/reference/cmultilock-class.md) , aby czekać i zwolnić obiekt synchronizacji. Użyj `CSingleLock` , gdy musisz poczekać na jeden obiekt jednocześnie. Użyj `CMultiLock` , gdy istnieje wiele obiektów, których można użyć w określonym czasie.

Aby użyć `CSingleLock` obiektu, wywołaj jego konstruktora wewnątrz funkcji składowej w klasie kontrolowanego zasobu. Następnie wywołaj funkcję [Islockd](#islocked) member, aby określić, czy zasób jest dostępny. Jeśli tak jest, Kontynuuj z pozostałą częścią funkcji składowej. Jeśli zasób jest niedostępny, poczekaj na określoną ilość czasu lub Zwróć błąd. Po zakończeniu korzystania z zasobu wywołaj funkcję [Unlock](#unlock) , jeśli `CSingleLock` obiekt ma być używany ponownie, lub Zezwól na `CSingleLock` zniszczenie obiektu.

`CSingleLock` obiekty wymagają obecności obiektu pochodnego od [CSyncObject](../../mfc/reference/csyncobject-class.md). Jest to zazwyczaj element członkowski danych klasy kontrolowanego zasobu. Aby uzyskać więcej informacji na temat używania `CSingleLock` obiektów, zobacz [wielowątkowość artykułu: jak używać klas synchronizacji](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`CSingleLock`

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxmt. h

## <a name="csinglelockcsinglelock"></a><a name="csinglelock"></a> CSingleLock::CSingleLock

Konstruuje `CSingleLock` obiekt.

```
explicit CSingleLock(
    CSyncObject* pObject,
    BOOL bInitialLock = FALSE);
```

### <a name="parameters"></a>Parametry

*pObject*<br/>
Wskazuje obiekt synchronizacji, do którego ma zostać uzyskany dostęp. Nie może mieć wartości NULL.

*bInitialLock*<br/>
Określa, czy początkowo próbować uzyskać dostęp do podanego obiektu.

### <a name="remarks"></a>Uwagi

Ta funkcja jest zazwyczaj wywoływana z poziomu funkcji członkowskiej dostępu kontrolowanego zasobu.

### <a name="example"></a>Przykład

[!code-cpp[NVC_MFC_Utilities#19](../../mfc/codesnippet/cpp/csinglelock-class_1.h)]

## <a name="csinglelockislocked"></a><a name="islocked"></a> CSingleLock:: IsLocked

Określa, czy obiekt skojarzony z `CSingleLock` obiektem jest Niesygnalizowane (niedostępny).

```
BOOL IsLocked();
```

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli obiekt jest zablokowany; w przeciwnym razie 0.

### <a name="example"></a>Przykład

[!code-cpp[NVC_MFC_Utilities#20](../../mfc/codesnippet/cpp/csinglelock-class_2.h)]

## <a name="csinglelocklock"></a><a name="lock"></a> CSingleLock:: Lock

Wywołaj tę funkcję, aby uzyskać dostęp do zasobu kontrolowanego przez obiekt synchronizacji dostarczony do `CSingleLock` konstruktora.

```
BOOL Lock(DWORD dwTimeOut = INFINITE);
```

### <a name="parameters"></a>Parametry

*dwTimeOut*<br/>
Określa czas oczekiwania na udostępnienie obiektu synchronizacji (sygnalizowanego zasygnalizowaniem). Jeśli NIESKOŃCZONość, `Lock` czeka na zasygnalizowanie obiektu przed zwróceniem.

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli funkcja zakończyła się pomyślnie; w przeciwnym razie 0.

### <a name="remarks"></a>Uwagi

Jeśli obiekt synchronizacji jest sygnalizujący, `Lock` zostanie pomyślnie zwrócony i wątek jest teraz właścicielem obiektu. Jeśli obiekt synchronizacji jest niesygnalizujący (niedostępny), `Lock` poczeka, aż obiekt synchronizacji zostanie zasygnalizowani do liczby milisekund określonych w parametrze *dwTimeOut* . Jeśli obiekt synchronizacji nie został zasygnalizowani w określonym czasie, `Lock` zwracany jest błąd.

### <a name="example"></a>Przykład

[!code-cpp[NVC_MFC_Utilities#21](../../mfc/codesnippet/cpp/csinglelock-class_3.h)]

## <a name="csinglelockunlock"></a><a name="unlock"></a> CSingleLock:: Unlock

Zwalnia obiekt synchronizacji posiadany przez `CSingleLock` .

```
BOOL Unlock();

BOOL Unlock(
    LONG lCount,
    LPLONG lPrevCount = NULL);
```

### <a name="parameters"></a>Parametry

*lCount*<br/>
Liczba dostępów do wydania. Musi być większa niż 0. Jeśli określona ilość spowodowałaby przekroczenie maksymalnej liczby obiektów, liczba nie zostanie zmieniona, a funkcja zwróci wartość FALSE.

*lPrevCount*<br/>
Wskazuje zmienną, w której ma zostać wyświetlona Poprzednia liczba obiektów synchronizacji. Jeśli wartość jest równa NULL, Poprzednia liczba nie jest zwracana.

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli funkcja zakończyła się pomyślnie; w przeciwnym razie 0.

### <a name="remarks"></a>Uwagi

Ta funkcja jest wywoływana przez `CSingleLock` destruktor.

Jeśli trzeba wydać więcej niż jedną liczbę dostępu semafora, należy użyć drugiej formy `Unlock` i określić liczbę dostępu do wydania.

### <a name="example"></a>Przykład

[!code-cpp[NVC_MFC_Utilities#21](../../mfc/codesnippet/cpp/csinglelock-class_3.h)]

## <a name="see-also"></a>Zobacz także

[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasa CMultiLock](../../mfc/reference/cmultilock-class.md)
