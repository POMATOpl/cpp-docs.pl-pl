---
description: 'Dowiedz się więcej na temat: Klasa CSemaphore'
title: Klasa CSemaphore
ms.date: 11/04/2016
f1_keywords:
- CSemaphore
- AFXMT/CSemaphore
- AFXMT/CSemaphore::CSemaphore
helpviewer_keywords:
- CSemaphore [MFC], CSemaphore
ms.assetid: 385fc7e4-8f86-4be2-85e1-d23b38c12f7f
ms.openlocfilehash: 102b7ac9d7f934e3a04783c9ab537a858541c780
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97264703"
---
# <a name="csemaphore-class"></a>Klasa CSemaphore

Obiekt klasy `CSemaphore` reprezentuje "Semafor" — obiekt synchronizacji, który umożliwia ograniczoną liczbę wątków w jednym lub wielu procesach, aby uzyskać dostęp do obsługiwanej liczby wątków, która aktualnie uzyskuje dostęp do określonego zasobu.

## <a name="syntax"></a>Składnia

```
class CSemaphore : public CSyncObject
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CSemaphore::CSemaphore](#csemaphore)|Konstruuje `CSemaphore` obiekt.|

## <a name="remarks"></a>Uwagi

Semafory są przydatne do kontrolowania dostępu do udostępnionego zasobu, który może obsługiwać tylko ograniczoną liczbę użytkowników. Bieżąca liczba `CSemaphore` obiektów to liczba dodatkowych użytkowników dozwolonych. Gdy licznik osiągnie wartość zero, wszystkie próby użycia zasobu kontrolowanego przez `CSemaphore` obiekt zostaną wstawione do kolejki systemowej i poczekać, aż przekroczy limit czasu lub licznik wzrośnie powyżej 0. Maksymalna liczba użytkowników, którzy mogą uzyskiwać dostęp do kontrolowanego zasobu w tym samym czasie, jest określona podczas konstruowania `CSemaphore` obiektu.

Aby użyć `CSemaphore` obiektu, Konstruuj obiekt, `CSemaphore` gdy jest to konieczne. Określ nazwę semafora, w którym ma się odczekać, i że aplikacja powinna początkowo być jego własnością. Następnie można uzyskać dostęp do semafora, gdy Konstruktor zwróci wartość. Wywołanie [CSyncObject:: Unlock](../../mfc/reference/csyncobject-class.md#unlock) po zakończeniu uzyskiwania dostępu do kontrolowanego zasobu.

Alternatywną metodą używania `CSemaphore` obiektów jest dodanie zmiennej typu `CSemaphore` jako elementu członkowskiego danych do klasy, którą chcesz kontrolować. Podczas konstruowania kontrolowanego obiektu Wywołaj konstruktora `CSemaphore` elementu członkowskiego danych, określając początkową liczbę dostępu, maksymalną liczbę dostępów, nazwę semafora (jeśli będzie używana między granicami procesów) i żądane atrybuty zabezpieczeń.

Aby uzyskać dostęp do zasobów kontrolowanych przez `CSemaphore` obiekty w ten sposób, należy najpierw utworzyć zmienną typu [CSingleLock](../../mfc/reference/csinglelock-class.md) lub [CMultiLock](../../mfc/reference/cmultilock-class.md) w funkcji członkowskiej dostępu do zasobu. Następnie Wywołaj `Lock` funkcję członkowską obiektu blokady (na przykład [CSingleLock:: Lock](../../mfc/reference/csinglelock-class.md#lock)). W tym momencie wątek uzyska dostęp do zasobu, poczeka na zwolnienie zasobu i uzyskanie dostępu albo poczekaj na zwolnienie zasobu i przekroczenie limitu czasu, aby uzyskać dostęp do zasobu. W każdym przypadku do zasobu uzyskano dostęp w sposób bezpieczny dla wątków. Aby zwolnić zasób, użyj `Unlock` funkcji składowej obiektu blokady (na przykład [CSingleLock:: Unlock](../../mfc/reference/csinglelock-class.md#unlock)) lub Zezwól obiektowi Lock poza zakres.

Alternatywnie można utworzyć obiekt autonomiczny `CSemaphore` i uzyskać do niego dostęp jawnie przed podjęciem próby dostępu do kontrolowanego zasobu. Ta metoda, natomiast wyraźniejszy dla kogoś odczytującego kod źródłowy, jest bardziej podatna na błędy.

Aby uzyskać więcej informacji na temat używania `CSemaphore` obiektów, zobacz [wielowątkowość artykułu: jak używać klas synchronizacji](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CSyncObject](../../mfc/reference/csyncobject-class.md)

`CSemaphore`

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxmt. h

## <a name="csemaphorecsemaphore"></a><a name="csemaphore"></a> CSemaphore::CSemaphore

Konstruuje obiekt nazwany lub nienazwany `CSemaphore` .

```
CSemaphore(
    LONG lInitialCount = 1,
    LONG lMaxCount = 1,
    LPCTSTR pstrName = NULL,
    LPSECURITY_ATTRIBUTES lpsaAttributes = NULL);
```

### <a name="parameters"></a>Parametry

*lInitialCount*<br/>
Początkowa liczba wykorzystań semafora. Musi być większa lub równa 0 i mniejsza niż lub równa *lMaxCount*.

*lMaxCount*<br/>
Maksymalna liczba obciążeń dla semafora. Musi być większa niż 0.

*pstrName*<br/>
Nazwa semafora. Należy podać, jeśli semafor zostanie uzyskany między granicami procesu. Jeśli `NULL` obiekt będzie nienazwany. Jeśli nazwa pasuje do istniejącego semafora, Konstruktor kompiluje nowy `CSemaphore` obiekt, który odwołuje się do semafora tej nazwy. Jeśli nazwa jest zgodna z istniejącym obiektem synchronizacji, który nie jest semaforem, konstrukcja zakończy się niepowodzeniem.

*lpsaAttributes*<br/>
Atrybuty zabezpieczeń obiektu semafora. Aby uzyskać pełny opis tej struktury, zobacz [SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\)) w Windows SDK.

### <a name="remarks"></a>Uwagi

Aby uzyskać dostęp do `CSemaphore` obiektu, Utwórz obiekt [CMultiLock](../../mfc/reference/cmultilock-class.md) lub [CSingleLock](../../mfc/reference/csinglelock-class.md) , a następnie Wywołaj funkcje [blokady](../../mfc/reference/csinglelock-class.md#lock) i [odblokowywania](../../mfc/reference/csinglelock-class.md#unlock) elementów członkowskich.

> [!IMPORTANT]
> Po utworzeniu `CSemaphore` obiektu Użyj [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) , aby upewnić się, że mutex jeszcze nie istnieje. Jeśli obiekt mutex wystąpił nieoczekiwanie, może to oznaczać, że nieautoryzowany proces jest squatting i może zależeć od złośliwego użycia obiektu mutex. W takim przypadku zalecaną procedurę świadomego zabezpieczenia jest zamknięcie uchwytu i kontynuowanie tak, jakby Wystąpił błąd podczas tworzenia obiektu.

## <a name="see-also"></a>Zobacz też

[Klasa CSyncObject](../../mfc/reference/csyncobject-class.md)<br/>
[Wykres hierarchii](../../mfc/hierarchy-chart.md)
