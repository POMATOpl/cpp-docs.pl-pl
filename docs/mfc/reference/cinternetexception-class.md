---
description: 'Dowiedz się więcej na temat: Klasa CInternetException'
title: Klasa CInternetException
ms.date: 11/04/2016
f1_keywords:
- CInternetException
- AFXINET/CInternetException
- AFXINET/CInternetException::CInternetException
- AFXINET/CInternetException::m_dwContext
- AFXINET/CInternetException::m_dwError
helpviewer_keywords:
- CInternetException [MFC], CInternetException
- CInternetException [MFC], m_dwContext
- CInternetException [MFC], m_dwError
ms.assetid: 44fb3cbe-523e-4754-8843-a77909990b14
ms.openlocfilehash: d46c2eca7f7f568b0296d6ced567d33b49ba4cb6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97209948"
---
# <a name="cinternetexception-class"></a>Klasa CInternetException

Reprezentuje warunek wyjątku związany z operacją internetową.

## <a name="syntax"></a>Składnia

```
class CInternetException : public CException
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CInternetException::CInternetException](#cinternetexception)|Konstruuje `CInternetException` obiekt.|

### <a name="public-data-members"></a>Publiczne elementy członkowskie danych

|Nazwa|Opis|
|----------|-----------------|
|[CInternetException:: m_dwContext](#m_dwcontext)|Wartość kontekstu skojarzona z operacją, która spowodowała wyjątek.|
|[CInternetException:: m_dwError](#m_dwerror)|Błąd, który spowodował wyjątek.|

## <a name="remarks"></a>Uwagi

`CInternetException`Klasa zawiera dwa publiczne elementy członkowskie danych: jeden zawiera kod błędu skojarzony z wyjątkiem, a drugi zawiera identyfikator kontekstu aplikacji internetowej skojarzonej z błędem.

Aby uzyskać więcej informacji o identyfikatorach kontekstu dla aplikacji internetowych, zobacz artykuł [programowanie internetowe za pomocą usługi WinInet](../../mfc/win32-internet-extensions-wininet.md).

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

`CInternetException`

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxinet. h

## <a name="cinternetexceptioncinternetexception"></a><a name="cinternetexception"></a> CInternetException::CInternetException

Ta funkcja członkowska jest wywoływana, gdy `CInternetException` obiekt zostanie utworzony.

```
CInternetException(DWORD dwError);
```

### <a name="parameters"></a>Parametry

*Elemencie*<br/>
Błąd, który spowodował wyjątek.

### <a name="remarks"></a>Uwagi

Aby zgłosić CInternetException, wywołaj globalną funkcję MFC [AfxThrowInternetException](internet-url-parsing-globals.md#afxthrowinternetexception).

## <a name="cinternetexceptionm_dwcontext"></a><a name="m_dwcontext"></a> CInternetException:: m_dwContext

Wartość kontekstu skojarzona z pokrewną operacją internetową.

```
DWORD_PTR m_dwContext;
```

### <a name="remarks"></a>Uwagi

Identyfikator kontekstu jest pierwotnie określony w [CInternetSession](../../mfc/reference/cinternetsession-class.md) i przesłany przez MFC do klas pochodnych [CInternetConnection](../../mfc/reference/cinternetconnection-class.md)i [CInternetFile](../../mfc/reference/cinternetfile-class.md). Można zastąpić to ustawienie domyślne i przypisać dowolny parametr *dwContext* wybraną wartość. *dwContext* jest skojarzony z żadną operacją danego obiektu. *dwContext* identyfikuje informacje o stanie operacji zwrócone przez [CInternetSession:: OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback).

## <a name="cinternetexceptionm_dwerror"></a><a name="m_dwerror"></a> CInternetException:: m_dwError

Błąd, który spowodował wyjątek.

```
DWORD m_dwError;
```

### <a name="remarks"></a>Uwagi

Ta wartość błędu może być kodem błędu systemu, który znajduje się w WINERROR. H lub wartość błędu z WININET. H.

Aby uzyskać listę kodów błędów Win32, zobacz [kody błędów](/windows/win32/Debug/system-error-codes). Lista komunikatów o błędach specyficznych dla Internetu znajduje się w temacie. Oba tematy znajdują się w Windows SDK.

## <a name="see-also"></a>Zobacz też

[Klasa CException](../../mfc/reference/cexception-class.md)<br/>
[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasa CException](../../mfc/reference/cexception-class.md)
