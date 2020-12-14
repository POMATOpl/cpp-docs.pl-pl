---
description: 'Dowiedz się więcej na temat: Klasa CCriticalSection'
title: Klasa CCriticalSection
ms.date: 11/04/2016
f1_keywords:
- CCriticalSection
- AFXMT/CCriticalSection
- AFXMT/CCriticalSection::CCriticalSection
- AFXMT/CCriticalSection::Lock
- AFXMT/CCriticalSection::Unlock
- AFXMT/CCriticalSection::m_sect
helpviewer_keywords:
- CCriticalSection [MFC], CCriticalSection
- CCriticalSection [MFC], Lock
- CCriticalSection [MFC], Unlock
- CCriticalSection [MFC], m_sect
ms.assetid: f776f74b-5b0b-4f32-9c13-2b8e4a0d7b2b
ms.openlocfilehash: 0041eea4453ec02159b26805bd5e7a264a410504
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97227796"
---
# <a name="ccriticalsection-class"></a>Klasa CCriticalSection

Reprezentuje "sekcję krytyczną" — obiekt synchronizacji, który umożliwia jednemu wątkowi w czasie uzyskanie dostępu do zasobu lub sekcji kodu.

## <a name="syntax"></a>Składnia

```
class CCriticalSection : public CSyncObject
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CCriticalSection::CCriticalSection](#ccriticalsection)|Konstruuje `CCriticalSection` obiekt.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CCriticalSection:: Lock](#lock)|Użyj, aby uzyskać dostęp do `CCriticalSection` obiektu.|
|[CCriticalSection:: Unlock](#unlock)|Zwalnia `CCriticalSection` obiekt.|

### <a name="public-operators"></a>Operatory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CCriticalSection:: operator CRITICAL_SECTION *](#operator_critical_section_star)|Pobiera wskaźnik do wewnętrznego obiektu CRITICAL_SECTION.|

### <a name="public-data-members"></a>Publiczne elementy członkowskie danych

|Nazwa|Opis|
|----------|-----------------|
|[CCriticalSection:: m_sect](#m_sect)|Obiekt CRITICAL_SECTION.|

## <a name="remarks"></a>Uwagi

Sekcje krytyczne są przydatne, gdy tylko jeden wątek w danym momencie może modyfikować dane lub inne kontrolowane zasoby. Na przykład Dodawanie węzłów do połączonej listy jest procesem, który powinien być dozwolony tylko przez jeden wątek w danym momencie. Przy użyciu `CCriticalSection` obiektu do kontrolowania połączonej listy tylko jeden wątek w danym momencie może uzyskać dostęp do listy.

> [!NOTE]
> Funkcja `CCriticalSection` klasy jest dostarczana przez rzeczywisty obiekt critical_section Win32.

Sekcje krytyczne są używane zamiast muteksów (zobacz [CMutex](../../mfc/reference/cmutex-class.md)), gdy szybkość jest krytyczna, a zasób nie będzie używany między granicami procesu.

Istnieją dwie metody używania `CCriticalSection` obiektu: autonomiczny i osadzony w klasie.

- Metoda autonomiczna do korzystania z obiektu autonomicznego `CCriticalSection` , Konstruowanie obiektu w `CCriticalSection` razie potrzeby. Po pomyślnym powrocie z konstruktora jawnie Zablokuj obiekt z wywołaniem [blokady](#lock). [Odblokuj](#unlock) wywołanie po zakończeniu uzyskiwania dostępu do sekcji krytycznej. Ta metoda, natomiast wyraźniejszy dla kogoś odczytującego kod źródłowy, jest bardziej podatna na błąd, ponieważ należy pamiętać o zablokowaniu i odblokowaniu sekcji krytycznej przed dostępem i po nim.

   Bardziej preferowaną metodą jest użycie klasy [CSingleLock](../../mfc/reference/csinglelock-class.md) . Ma także `Lock` `Unlock` metodę i, ale nie trzeba martwić się o odblokowanie zasobu, jeśli wystąpi wyjątek.

- Osadzona Metoda można również udostępnić klasę z wieloma wątkami przez dodanie `CCriticalSection` składowej danych typu i zablokowanie elementu członkowskiego danych w razie potrzeby.

Aby uzyskać więcej informacji na temat korzystania z `CCriticalSection` obiektów, zobacz [wielowątkowość artykułu: jak używać klas synchronizacji](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CSyncObject](../../mfc/reference/csyncobject-class.md)

`CCriticalSection`

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxmt. h

## <a name="ccriticalsectionccriticalsection"></a><a name="ccriticalsection"></a> CCriticalSection::CCriticalSection

Konstruuje `CCriticalSection` obiekt.

```
CCriticalSection();
```

### <a name="remarks"></a>Uwagi

Aby uzyskać dostęp do `CCriticalSection` obiektu, Utwórz obiekt [CSingleLock](../../mfc/reference/csinglelock-class.md) i Wywołaj funkcje jego [blokady](../../mfc/reference/csinglelock-class.md#lock) i [odblokowywania](../../mfc/reference/csinglelock-class.md#unlock) . Jeśli `CCriticalSection` obiekt jest używany autonomicznie, wywołaj jego funkcję [odblokowania](#unlock) , aby go zwolnić.

Jeśli Konstruktor nie może przydzielić wymaganej pamięci systemowej, zostanie automatycznie wygenerowany wyjątek pamięci (typu [CMemoryException](../../mfc/reference/cmemoryexception-class.md)).

### <a name="example"></a>Przykład

  Zobacz przykład dla [CCriticalSection:: Lock](#lock).

## <a name="ccriticalsectionlock"></a><a name="lock"></a> CCriticalSection:: Lock

Wywołaj tę funkcję elementu członkowskiego, aby uzyskać dostęp do obiektu sekcji krytycznej.

```
BOOL Lock();
BOOL Lock(DWORD dwTimeout);
```

### <a name="parameters"></a>Parametry

*dwTimeout*<br/>
`Lock` ignoruje tę wartość parametru.

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli funkcja zakończyła się pomyślnie; w przeciwnym razie 0.

### <a name="remarks"></a>Uwagi

`Lock` jest wywołaniem blokującym, które nie zostanie zwrócone do momentu zasygnalizowania obiektu sekcji krytycznej (staną się dostępne).

Jeśli czas oczekiwania jest niezbędny, można użyć obiektu [CMutex](../../mfc/reference/cmutex-class.md) zamiast `CCriticalSection` obiektu.

Jeśli `Lock` nie można przydzielić niezbędnej pamięci systemowej, zostanie automatycznie wygenerowany wyjątek pamięci (typu [CMemoryException](../../mfc/reference/cmemoryexception-class.md)).

### <a name="example"></a>Przykład

W tym przykładzie przedstawiono podejście zagnieżdżonej sekcji krytycznej przez kontrolowanie dostępu do zasobu udostępnionego ( `_strShared` obiektu statycznego) przy użyciu `CCriticalSection` obiektu udostępnionego. `SomeMethod`Funkcja pokazuje, jak aktualizować zasób udostępniony w bezpieczny sposób.

[!code-cpp[NVC_MFC_Utilities#11](../../mfc/codesnippet/cpp/ccriticalsection-class_1.h)]

## <a name="ccriticalsectionm_sect"></a><a name="m_sect"></a> CCriticalSection:: m_sect

Zawiera obiekt sekcji krytycznej, który jest używany przez wszystkie `CCriticalSection` metody.

```
CRITICAL_SECTION m_sect;
```

## <a name="ccriticalsectionoperator-critical_section"></a><a name="operator_critical_section_star"></a> CCriticalSection:: operator CRITICAL_SECTION *

Pobiera obiekt CRITICAL_SECTION.

```
operator CRITICAL_SECTION*();
```

### <a name="remarks"></a>Uwagi

Wywołaj tę funkcję, aby pobrać wskaźnik do wewnętrznego obiektu CRITICAL_SECTION.

## <a name="ccriticalsectionunlock"></a><a name="unlock"></a> CCriticalSection:: Unlock

Zwalnia `CCriticalSection` obiekt do użycia przez inny wątek.

```
BOOL Unlock();
```

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli `CCriticalSection` obiekt był własnością wątku, a wydanie zakończyło się pomyślnie; w przeciwnym razie 0.

### <a name="remarks"></a>Uwagi

Jeśli `CCriticalSection` jest używana autonomiczna, `Unlock` musi być wywoływana natychmiast po zakończeniu korzystania z zasobu kontrolowanego przez sekcję krytyczną. Jeśli obiekt [CSingleLock](../../mfc/reference/csinglelock-class.md) jest używany, `CCriticalSection::Unlock` zostanie wywołany przez `Unlock` funkcję członkowską obiektu blokady.

### <a name="example"></a>Przykład

  Zobacz przykład dla [CCriticalSection:: Lock](#lock).

## <a name="see-also"></a>Zobacz też

[Klasa CSyncObject](../../mfc/reference/csyncobject-class.md)<br/>
[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasa CMutex](../../mfc/reference/cmutex-class.md)
