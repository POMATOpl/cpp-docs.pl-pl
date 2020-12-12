---
description: 'Dowiedz się więcej na temat: Klasa CInternetConnection'
title: Klasa CInternetConnection
ms.date: 11/04/2016
f1_keywords:
- CInternetConnection
- AFXINET/CInternetConnection
- AFXINET/CInternetConnection::CInternetConnection
- AFXINET/CInternetConnection::GetContext
- AFXINET/CInternetConnection::GetServerName
- AFXINET/CInternetConnection::GetSession
helpviewer_keywords:
- CInternetConnection [MFC], CInternetConnection
- CInternetConnection [MFC], GetContext
- CInternetConnection [MFC], GetServerName
- CInternetConnection [MFC], GetSession
ms.assetid: 62a5d1c3-8471-4e36-a064-48831829b2a7
ms.openlocfilehash: 2ae869e8cbf3bbfb3ce19e78088a465ae1d6aa65
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97143549"
---
# <a name="cinternetconnection-class"></a>Klasa CInternetConnection

Zarządza połączeniem z serwerem internetowym.

## <a name="syntax"></a>Składnia

```
class CInternetConnection : public CObject
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CInternetConnection::CInternetConnection](#cinternetconnection)|Konstruuje `CInternetConnection` obiekt.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CInternetConnection:: GetContext](#getcontext)|Pobiera identyfikator kontekstu dla tego obiektu połączenia.|
|[CInternetConnection:: GetServerName](#getservername)|Pobiera nazwę serwera skojarzonego z połączeniem.|
|[CInternetConnection:: getsession](#getsession)|Pobiera wskaźnik do obiektu [CInternetSession](../../mfc/reference/cinternetsession-class.md) skojarzonego z połączeniem.|

### <a name="public-operators"></a>Operatory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CInternetConnection:: operator HINTERNET](#operator_hinternet)|Dojście do sesji internetowej.|

## <a name="remarks"></a>Uwagi

Jest klasą bazową dla klas MFC [CFtpConnection](../../mfc/reference/cftpconnection-class.md), [CHttpConnection](../../mfc/reference/chttpconnection-class.md)i [CGopherConnection](../../mfc/reference/cgopherconnection-class.md). Każda z tych klas oferuje dodatkowe funkcje komunikacji z odpowiednim serwerem FTP, HTTP lub gopher.

Aby komunikować się bezpośrednio z serwerem internetowym, musisz mieć obiekt [CInternetSession](../../mfc/reference/cinternetsession-class.md) i `CInternetConnection` obiekt.

Aby dowiedzieć się więcej o tym, jak działają klasy WinInet, zobacz artykuł [programowanie internetowe za pomocą usługi WinInet](../../mfc/win32-internet-extensions-wininet.md).

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

`CInternetConnection`

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxinet. h

## <a name="cinternetconnectioncinternetconnection"></a><a name="cinternetconnection"></a> CInternetConnection::CInternetConnection

Ta funkcja członkowska jest wywoływana, gdy `CInternetConnection` obiekt zostanie utworzony.

```
CInternetConnection(
    CInternetSession* pSession,
    LPCTSTR pstrServer,
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER,
    DWORD_PTR dwContext = 1);
```

### <a name="parameters"></a>Parametry

*pSession*<br/>
Wskaźnik do obiektu [CInternetSession](../../mfc/reference/cinternetsession-class.md) .

*pstrServer*<br/>
Wskaźnik do ciągu zawierającego nazwę serwera.

*nPort*<br/>
Numer identyfikujący port internetowy dla tego połączenia.

*dwContext*<br/>
Identyfikator kontekstu dla `CInternetConnection` obiektu. Aby uzyskać więcej informacji na temat *dwContext*, zobacz **uwagi** .

### <a name="remarks"></a>Uwagi

Nigdy nie wywołujesz `CInternetConnection` siebie; zamiast tego wywołaj funkcję członkowską [CInternetSession](../../mfc/reference/cinternetsession-class.md) dla typu połączenia, które chcesz ustalić:

- [CInternetSession::GetFtpConnection](../../mfc/reference/cinternetsession-class.md#getftpconnection)

- [CInternetSession::GetHttpConnection](../../mfc/reference/cinternetsession-class.md#gethttpconnection)

- [CInternetSession::GetGopherConnection](../../mfc/reference/cinternetsession-class.md#getgopherconnection)

Wartość domyślna parametru *dwContext* jest wysyłana przez MFC do `CInternetConnection` obiektu pochodnego z obiektu [CInternetSession](../../mfc/reference/cinternetsession-class.md) , który utworzył obiekt pochodny **InternetConnection**. Wartość domyślna to 1; można jednak jawnie przypisać określony identyfikator kontekstu w konstruktorze [CInternetSession](../../mfc/reference/cinternetsession-class.md#cinternetsession) dla tego połączenia. Obiekt i wszystkie wykonane zadania zostaną skojarzone z tym IDENTYFIKATORem kontekstu. Identyfikator kontekstu jest zwracany do [CInternetSession:: OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) w celu udostępnienia stanu obiektu, z którym został zidentyfikowany. Zapoznaj się z artykułem [internetowym pierwsze kroki: WinInet](../../mfc/wininet-basics.md) , aby uzyskać więcej informacji na temat identyfikatora kontekstu.

## <a name="cinternetconnectiongetcontext"></a><a name="getcontext"></a> CInternetConnection:: GetContext

Wywołaj tę funkcję elementu członkowskiego, aby uzyskać identyfikator kontekstu dla tej sesji.

```
DWORD_PTR GetContext() const;
```

### <a name="return-value"></a>Wartość zwracana

Identyfikator kontekstu przypisany do aplikacji.

### <a name="remarks"></a>Uwagi

Identyfikator kontekstu jest początkowo określony w [CInternetSession](../../mfc/reference/cinternetsession-class.md) i propagowany do `CInternetConnection` klas pochodnych i [CInternetFile](../../mfc/reference/cinternetfile-class.md), chyba że określono inaczej w wywołaniu funkcji otwierającej połączenie. Identyfikator kontekstu jest skojarzony z dowolną operacją danego obiektu i identyfikuje informacje o stanie operacji zwrócone przez [CInternetSession:: OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback).

Aby uzyskać więcej informacji o `GetContext` tym, jak współpracuje z innymi klasami WinInet w celu uzyskania informacji o stanie użytkownika, zobacz artykuł [Internet pierwsze kroki: WinInet](../../mfc/wininet-basics.md) , aby uzyskać więcej informacji na temat identyfikatora kontekstu.

## <a name="cinternetconnectiongetservername"></a><a name="getservername"></a> CInternetConnection:: GetServerName

Wywołaj tę funkcję elementu członkowskiego, aby uzyskać nazwę serwera skojarzonego z tym połączeniem internetowym.

```
CString GetServerName() const;
```

### <a name="return-value"></a>Wartość zwracana

Nazwa serwera, z którym działa ten obiekt połączenia.

## <a name="cinternetconnectiongetsession"></a><a name="getsession"></a> CInternetConnection:: getsession

Wywołaj tę funkcję elementu członkowskiego, aby uzyskać wskaźnik do `CInternetSession` obiektu, który jest skojarzony z tym połączeniem.

```
CInternetSession* GetSession() const;
```

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do obiektu [CInternetSession](../../mfc/reference/cinternetsession-class.md) skojarzonego z tym obiektem połączenia internetowego.

## <a name="cinternetconnectionoperator-hinternet"></a><a name="operator_hinternet"></a> CInternetConnection:: operator HINTERNET

Użyj tego operatora, aby uzyskać dojście na poziomie interfejsu API dla bieżącej sesji internetowej.

```
operator HINTERNET() const;
```

## <a name="see-also"></a>Zobacz też

[Klasa CObject](../../mfc/reference/cobject-class.md)<br/>
[Wykres hierarchii](../../mfc/hierarchy-chart.md)
