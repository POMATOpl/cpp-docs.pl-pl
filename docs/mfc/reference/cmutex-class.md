---
description: 'Dowiedz się więcej na temat: Klasa CMutex'
title: Klasa CMutex
ms.date: 11/04/2016
f1_keywords:
- CMutex
- AFXMT/CMutex
- AFXMT/CMutex::CMutex
helpviewer_keywords:
- CMutex [MFC], CMutex
ms.assetid: 6330c050-4f01-4195-a099-2029b92f8cf1
ms.openlocfilehash: 4890a99d52fb8142bac0cc25d6a23ef6dbcaed5b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331493"
---
# <a name="cmutex-class"></a>Klasa CMutex

Reprezentuje "mutex" — obiekt synchronizacji, który umożliwia jednemu wątkowi wyłączny dostęp do zasobu.

## <a name="syntax"></a>Składnia

```
class CMutex : public CSyncObject
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CMutex::CMutex](#cmutex)|Konstruuje `CMutex` obiekt.|

## <a name="remarks"></a>Uwagi

Muteksy są przydatne, gdy tylko jeden wątek w danym momencie może modyfikować dane lub inne kontrolowane zasoby. Na przykład Dodawanie węzłów do połączonej listy jest procesem, który powinien być dozwolony tylko przez jeden wątek w danym momencie. Przy użyciu `CMutex` obiektu do kontrolowania połączonej listy tylko jeden wątek w danym momencie może uzyskać dostęp do listy.

Aby użyć `CMutex` obiektu, Konstruuj obiekt, `CMutex` gdy jest to konieczne. Określ nazwę obiektu mutex, który ma być oczekiwany, i że aplikacja powinna początkowo być jego właścicielem. Następnie można uzyskać dostęp do obiektu mutex, gdy Konstruktor zwróci wartość. Wywołanie [CSyncObject:: Unlock](../../mfc/reference/csyncobject-class.md#unlock) po zakończeniu uzyskiwania dostępu do kontrolowanego zasobu.

Alternatywną metodą używania `CMutex` obiektów jest dodanie zmiennej typu `CMutex` jako elementu członkowskiego danych do klasy, którą chcesz kontrolować. Podczas konstruowania kontrolowanego obiektu Wywołaj konstruktora `CMutex` elementu członkowskiego danych, określając, czy mutex jest początkowo własnością, nazwa obiektu mutex (jeśli będzie używana między granicami procesów) i żądane atrybuty zabezpieczeń.

Aby uzyskać dostęp do zasobów kontrolowanych przez `CMutex` obiekty w ten sposób, należy najpierw utworzyć zmienną typu [CSingleLock](../../mfc/reference/csinglelock-class.md) lub [CMultiLock](../../mfc/reference/cmultilock-class.md) w funkcji członkowskiej dostępu do zasobu. Następnie Wywołaj `Lock` funkcję członkowską obiektu blokady (na przykład [CSingleLock:: Lock](../../mfc/reference/csinglelock-class.md#lock)). W tym momencie wątek uzyska dostęp do zasobu, poczeka na zwolnienie zasobu i uzyskanie dostępu albo poczekaj na zwolnienie zasobu i przekroczenie limitu czasu, aby uzyskać dostęp do zasobu. W każdym przypadku do zasobu uzyskano dostęp w sposób bezpieczny dla wątków. Aby zwolnić zasób, użyj `Unlock` funkcji składowej obiektu blokady (na przykład [CSingleLock:: Unlock](../../mfc/reference/csinglelock-class.md#unlock)) lub Zezwól obiektowi Lock poza zakres.

Aby uzyskać więcej informacji na temat korzystania z `CMutex` obiektów, zobacz [wielowątkowość artykułu: jak używać klas synchronizacji](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CSyncObject](../../mfc/reference/csyncobject-class.md)

`CMutex`

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxmt. h

## <a name="cmutexcmutex"></a><a name="cmutex"></a> CMutex::CMutex

Konstruuje obiekt nazwany lub nienazwany `CMutex` .

```
CMutex(
    BOOL bInitiallyOwn = FALSE,
    LPCTSTR lpszName = NULL,
    LPSECURITY_ATTRIBUTES lpsaAttribute = NULL);
```

### <a name="parameters"></a>Parametry

*bInitiallyOwn*<br/>
Określa, czy wątek tworzący `CMutex` obiekt początkowo ma dostęp do zasobu kontrolowanego przez mutex.

*lpszName*<br/>
Nazwa `CMutex` obiektu. Jeśli istnieje inny element mutex o tej samej nazwie, *lpszName* musi zostać dostarczony, jeśli obiekt będzie używany między granicami procesu. Jeśli **wartość jest równa null**, mutex będzie nienazwany. Jeśli nazwa pasuje do istniejącego obiektu mutex, Konstruktor kompiluje nowy `CMutex` obiekt, który odwołuje się do obiektu mutex o tej nazwie. Jeśli nazwa jest zgodna z istniejącym obiektem synchronizacji, który nie jest mutex, konstrukcja zakończy się niepowodzeniem.

*lpsaAttribute*<br/>
Atrybuty zabezpieczeń dla obiektu mutex. Aby uzyskać pełny opis tej struktury, zobacz [SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\)) w Windows SDK.

### <a name="remarks"></a>Uwagi

Aby uzyskać dostęp do `CMutex` obiektu, Utwórz obiekt [CMultiLock](../../mfc/reference/cmultilock-class.md) lub [CSingleLock](../../mfc/reference/csinglelock-class.md) , a następnie Wywołaj funkcje [blokady](../../mfc/reference/csinglelock-class.md#lock) i [odblokowywania](../../mfc/reference/csinglelock-class.md#unlock) elementów członkowskich. Jeśli `CMutex` obiekt jest używany autonomicznie, wywołaj jego `Unlock` funkcję członkowską, aby go zwolnić.

> [!IMPORTANT]
> Po utworzeniu `CMutex` obiektu Użyj [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) , aby upewnić się, że mutex jeszcze nie istnieje. Jeśli obiekt mutex wystąpił nieoczekiwanie, może to oznaczać, że nieautoryzowany proces jest squatting i może zależeć od złośliwego użycia obiektu mutex. W takim przypadku zalecaną procedurę świadomego zabezpieczenia jest zamknięcie uchwytu i kontynuowanie tak, jakby Wystąpił błąd podczas tworzenia obiektu.

## <a name="see-also"></a>Zobacz też

[Klasa CSyncObject](../../mfc/reference/csyncobject-class.md)<br/>
[Wykres hierarchii](../../mfc/hierarchy-chart.md)
