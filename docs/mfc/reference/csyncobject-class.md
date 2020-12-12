---
description: 'Dowiedz się więcej na temat: Klasa CSyncObject'
title: Klasa CSyncObject
ms.date: 11/04/2016
f1_keywords:
- CSyncObject
- AFXMT/CSyncObject
- AFXMT/CSyncObject::CSyncObject
- AFXMT/CSyncObject::Lock
- AFXMT/CSyncObject::Unlock
- AFXMT/CSyncObject::m_hObject
helpviewer_keywords:
- CSyncObject [MFC], CSyncObject
- CSyncObject [MFC], Lock
- CSyncObject [MFC], Unlock
- CSyncObject [MFC], m_hObject
ms.assetid: c62ea6eb-a17b-4e01-aed4-321fc435a5f4
ms.openlocfilehash: 5743f632f9a8c482ac15995e8d2429851ba015d8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97318601"
---
# <a name="csyncobject-class"></a>Klasa CSyncObject

Czysta Klasa wirtualna, która zapewnia funkcje wspólne dla obiektów synchronizacji w systemie Win32.

## <a name="syntax"></a>Składnia

```
class CSyncObject : public CObject
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CSyncObject::CSyncObject](#csyncobject)|Konstruuje `CSyncObject` obiekt.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CSyncObject:: Lock](#lock)|Uzyskuje dostęp do obiektu synchronizacji.|
|[CSyncObject:: Unlock](#unlock)|Uzyskuje dostęp do obiektu synchronizacji.|

### <a name="public-operators"></a>Operatory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CSyncObject:: uchwyt operatora](#operator_handle)|Zapewnia dostęp do obiektu synchronizacji.|

### <a name="public-data-members"></a>Publiczne elementy członkowskie danych

|Nazwa|Opis|
|----------|-----------------|
|[CSyncObject:: m_hObject](#m_hobject)|Uchwyt do źródłowego obiektu synchronizacji.|

## <a name="remarks"></a>Uwagi

Biblioteka MFC zawiera kilka klas pochodnych od `CSyncObject` . Są to [CEvent](../../mfc/reference/cevent-class.md), [CMutex](../../mfc/reference/cmutex-class.md), [CCriticalSection](../../mfc/reference/ccriticalsection-class.md)i [CSemaphore](../../mfc/reference/csemaphore-class.md).

Aby uzyskać informacje na temat korzystania z obiektów synchronizacji, zobacz [wielowątkowość artykułu: jak używać klas synchronizacji](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

`CSyncObject`

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxmt. h

## <a name="csyncobjectcsyncobject"></a><a name="csyncobject"></a> CSyncObject::CSyncObject

Tworzy obiekt synchronizacji o podanej nazwie.

```
explicit CSyncObject(LPCTSTR pstrName);
virtual ~CSyncObject();
```

### <a name="parameters"></a>Parametry

*pstrName*<br/>
Nazwa obiektu. Jeśli wartość jest równa NULL, *pstrName* będzie mieć wartość null.

## <a name="csyncobjectlock"></a><a name="lock"></a> CSyncObject:: Lock

Wywołaj tę funkcję, aby uzyskać dostęp do zasobu kontrolowanego przez obiekt synchronizacji.

```
virtual BOOL Lock(DWORD dwTimeout = INFINITE);
```

### <a name="parameters"></a>Parametry

*dwTimeout*<br/>
Określa czas (w milisekundach) oczekiwania na dostępność obiektu synchronizacji (sygnalizujący). Jeśli NIESKOŃCZONość, `Lock` czeka na zasygnalizowanie obiektu przed zwróceniem.

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli funkcja zakończyła się pomyślnie; w przeciwnym razie 0.

### <a name="remarks"></a>Uwagi

Jeśli obiekt synchronizacji jest sygnalizujący, `Lock` zostanie pomyślnie zwrócony i wątek jest teraz właścicielem obiektu. Jeśli obiekt synchronizacji jest niesygnalizujący (niedostępny), `Lock` poczeka, aż obiekt synchronizacji zostanie zasygnalizowani do liczby milisekund określonych w parametrze *dwTimeOut* . Jeśli obiekt synchronizacji nie został zasygnalizowani w określonym czasie, `Lock` zwracany jest błąd.

## <a name="csyncobjectm_hobject"></a><a name="m_hobject"></a> CSyncObject:: m_hObject

Uchwyt do źródłowego obiektu synchronizacji.

```
HANDLE m_hObject;
```

## <a name="csyncobjectoperator-handle"></a><a name="operator_handle"></a> CSyncObject:: uchwyt operatora

Użyj tego operatora, aby uzyskać uchwyt `CSyncObject` obiektu.

```
operator HANDLE() const;
```

### <a name="return-value"></a>Wartość zwracana

Jeśli to się powiedzie, uchwyt obiektu synchronizacji; w przeciwnym razie wartość NULL.

### <a name="remarks"></a>Uwagi

Możesz użyć uchwytu, aby bezpośrednio wywołać interfejsy API systemu Windows.

## <a name="csyncobjectunlock"></a><a name="unlock"></a> CSyncObject:: Unlock

Deklaracja `Unlock` bez parametrów jest czystą funkcją wirtualną i musi zostać przesłonięta przez wszystkie klasy pochodne z `CSyncObject` .

```
virtual BOOL Unlock() = 0; virtual BOOL Unlock(
    LONG lCount,
    LPLONG lpPrevCount = NULL);
```

### <a name="parameters"></a>Parametry

*lCount*<br/>
Nieużywane przez implementację domyślną.

*lpPrevCount*<br/>
Nieużywane przez implementację domyślną.

### <a name="return-value"></a>Wartość zwracana

Domyślna implementacja zawsze zwraca wartość TRUE.

### <a name="remarks"></a>Uwagi

Domyślna implementacja deklaracji z dwoma parametrami zawsze zwraca wartość TRUE. Ta funkcja jest wywoływana w celu zwolnienia dostępu do obiektu synchronizacji należącego do wątku wywołującego. Druga deklaracja jest świadczona dla obiektów synchronizacji, takich jak semafory, które zezwalają na więcej niż jeden dostęp do kontrolowanego zasobu.

## <a name="see-also"></a>Zobacz też

[Klasa CObject](../../mfc/reference/cobject-class.md)<br/>
[Wykres hierarchii](../../mfc/hierarchy-chart.md)
