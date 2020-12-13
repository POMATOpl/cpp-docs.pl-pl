---
description: 'Dowiedz się więcej na temat: zwinięcie klasy'
title: Zwinięcie — Klasa
ms.date: 05/06/2019
f1_keywords:
- CUrl
- ATLUTIL/ATL::CUrl
- ATLUTIL/ATL::CUrl::CUrl
- ATLUTIL/ATL::CUrl::Canonicalize
- ATLUTIL/ATL::CUrl::Clear
- ATLUTIL/ATL::CUrl::CrackUrl
- ATLUTIL/ATL::CUrl::CreateUrl
- ATLUTIL/ATL::CUrl::GetExtraInfo
- ATLUTIL/ATL::CUrl::GetExtraInfoLength
- ATLUTIL/ATL::CUrl::GetHostName
- ATLUTIL/ATL::CUrl::GetHostNameLength
- ATLUTIL/ATL::CUrl::GetPassword
- ATLUTIL/ATL::CUrl::GetPasswordLength
- ATLUTIL/ATL::CUrl::GetPortNumber
- ATLUTIL/ATL::CUrl::GetScheme
- ATLUTIL/ATL::CUrl::GetSchemeName
- ATLUTIL/ATL::CUrl::GetSchemeNameLength
- ATLUTIL/ATL::CUrl::GetUrlLength
- ATLUTIL/ATL::CUrl::GetUrlPath
- ATLUTIL/ATL::CUrl::GetUrlPathLength
- ATLUTIL/ATL::CUrl::GetUserName
- ATLUTIL/ATL::CUrl::GetUserNameLength
- ATLUTIL/ATL::CUrl::SetExtraInfo
- ATLUTIL/ATL::CUrl::SetHostName
- ATLUTIL/ATL::CUrl::SetPassword
- ATLUTIL/ATL::CUrl::SetPortNumber
- ATLUTIL/ATL::CUrl::SetScheme
- ATLUTIL/ATL::CUrl::SetSchemeName
- ATLUTIL/ATL::CUrl::SetUrlPath
- ATLUTIL/ATL::CUrl::SetUserName
helpviewer_keywords:
- CUrl class
ms.assetid: b3894d34-47b9-4961-9719-4197153793da
ms.openlocfilehash: e8453c4dd1abbfdcb6d794b89fd55f37d7b3f286
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97140299"
---
# <a name="curl-class"></a>Zwinięcie — Klasa

Ta klasa reprezentuje adres URL. Pozwala ona na manipulowanie każdym elementem adresu URL niezależnie od innych, niezależnie od tego, czy jest analizowany istniejący ciąg adresu URL, czy też tworzący ciąg od podstaw.

> [!IMPORTANT]
> Tej klasy i jej elementów członkowskich nie można używać w aplikacjach, które są wykonywane w środowisko wykonawcze systemu Windows.

## <a name="syntax"></a>Składnia

```
class CUrl
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[Zwinięcie:: zwinięcie](#curl)|Konstruktor.|
|[Zwinięcie:: ~ zwinięcie](#dtor)|Destruktor.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[Zwinięcie:: sprowadź](#canonicalize)|Wywołaj tę metodę, aby przekonwertować ciąg adresu URL na postać kanoniczną.|
|[Zwinięcie:: Clear](#clear)|Wywołaj tę metodę, aby wyczyścić wszystkie pola adresu URL.|
|[Zwinięcie:: CrackUrl](#crackurl)|Wywołaj tę metodę, aby zdekodować i przeanalizować adres URL.|
|[Zwinięcie:: CreateUrl](#createurl)|Wywołaj tę metodę, aby utworzyć adres URL.|
|[Zwinięcie:: GetExtraInfo](#getextrainfo)|Wywołaj tę metodę, aby uzyskać dodatkowe informacje (takie jak *tekst* lub # *tekst*) od adresu URL.|
|[Zwinięcie:: GetExtraInfoLength](#getextrainfolength)|Wywołaj tę metodę, aby uzyskać informacje o długości dodatkowych informacji (takich jak *tekst* lub # *tekst*) do pobrania z adresu URL.|
|[Zwinięcie:: gethostname](#gethostname)|Wywołaj tę metodę, aby pobrać nazwę hosta z adresu URL.|
|[Zwinięcie:: GetHostNameLength](#gethostnamelength)|Wywołaj tę metodę, aby uzyskać długość nazwy hosta.|
|[Zwinięcie:: GetPassword](#getpassword)|Wywołaj tę metodę, aby uzyskać hasło z adresu URL.|
|[Zwinięcie:: GetPasswordLength](#getpasswordlength)|Wywołaj tę metodę, aby uzyskać długość hasła.|
|[Zwinięcie:: GetPortNumber](#getportnumber)|Wywołaj tę metodę, aby pobrać numer portu pod warunkiem ATL_URL_PORT.|
|[Zwinięcie:: GetSchema](#getscheme)|Wywołaj tę metodę, aby uzyskać schemat adresu URL.|
|[Zwinięcie:: getschemaname](#getschemename)|Wywołaj tę metodę, aby pobrać nazwę schematu adresu URL.|
|[Zwinięcie:: GetSchemeNameLength](#getschemenamelength)|Wywołaj tę metodę, aby uzyskać długość nazwy schematu adresu URL.|
|[Zwinięcie:: GetUrlLength](#geturllength)|Wywołaj tę metodę, aby uzyskać długość adresu URL.|
|[Zwinięcie:: GetUrlPath](#geturlpath)|Wywołaj tę metodę, aby uzyskać ścieżkę adresu URL.|
|[Zwinięcie:: GetUrlPathLength](#geturlpathlength)|Wywołaj tę metodę, aby uzyskać długość ścieżki URL.|
|[Zwinięcie:: GetUserName](#getusername)|Wywołaj tę metodę, aby pobrać nazwę użytkownika z adresu URL.|
|[Zwinięcie:: GetUserNameLength](#getusernamelength)|Wywołaj tę metodę, aby uzyskać długość nazwy użytkownika.|
|[Zwinięcie:: SetExtraInfo](#setextrainfo)|Wywołaj tę metodę, aby ustawić dodatkowe informacje (takie jak *tekst* lub # *tekst*) adresu URL.|
|[Zwinięcie:: sethostname](#sethostname)|Wywołaj tę metodę, aby ustawić nazwę hosta.|
|[Zwinięcie:: SetPassword](#setpassword)|Wywołaj tę metodę, aby ustawić hasło.|
|[Zwinięcie:: SetPortNumber](#setportnumber)|Wywołaj tę metodę, aby ustawić numer portu pod warunkiem ATL_URL_PORT.|
|[Zwinięcie:: setschema](#setscheme)|Wywołaj tę metodę, aby ustawić schemat adresu URL.|
|[Zwinięcie:: setschemaname](#setschemename)|Wywołaj tę metodę, aby ustawić nazwę schematu adresu URL.|
|[Zwinięcie:: SetUrlPath](#seturlpath)|Wywołaj tę metodę, aby ustawić ścieżkę adresu URL.|
|[Zwinięcie:: SetUserName](#setusername)|Wywołaj tę metodę, aby ustawić nazwę użytkownika.|

### <a name="public-operators"></a>Operatory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[Zwinięcie:: operator =](#operator_eq)|Przypisuje określony `CUrl` obiekt do bieżącego `CUrl` obiektu.|

## <a name="remarks"></a>Uwagi

`CUrl` umożliwia manipulowanie polami adresu URL, takimi jak ścieżka lub numer portu. `CUrl` rozumie adresy URL następującej postaci:

\<Scheme>://\<UserName>:\<Password>\@\<HostName>:\<PortNumber>/\<UrlPath>\<ExtraInfo>

(Niektóre pola są opcjonalne). Rozważmy na przykład ten adres URL:

`http://someone:secret@www.microsoft.com:80/visualc/stuff.htm#contents`

[Zwinięcie:: CrackUrl](#crackurl) analizuje je w następujący sposób:

- Schemat: "http" lub [ATL_URL_SCHEME_HTTP](atl-url-scheme-enum.md)

- Nazwa użytkownika: "ktoś"

- Hasło: "klucz tajny"

- Nazwa hosta: " `www.microsoft.com` "

- Numer_portu: 80

- UrlPath: "VisualC/stuff.htm"

- ExtraInfo: "#contents"

Aby manipulować polem UrlPath (na przykład), należy użyć [GetUrlPath](#geturlpath), [GetUrlPathLength](#geturlpathlength)i [SetUrlPath](#seturlpath). Użyj [createUrl](#createurl) , aby utworzyć pełny ciąg adresu URL.

## <a name="requirements"></a>Wymagania

**Nagłówek:** atlutil. h

## <a name="curlcanonicalize"></a><a name="canonicalize"></a> Zwinięcie:: sprowadź

Wywołaj tę metodę, aby przekonwertować ciąg adresu URL na postać kanoniczną.

```
inline BOOL Canonicalize(DWORD dwFlags = 0) throw();
```

### <a name="parameters"></a>Parametry

*flagiDW*<br/>
Flagi kontrolujące kanonizację. Jeśli nie określono żadnych flag (*flagiDW* = 0), Metoda konwertuje wszystkie niebezpieczne znaki i meta sequences (takie jak \\ ., \... i \\ ...) na sekwencje ucieczki. *flagiDW* może być jedną z następujących wartości:

- ATL_URL_BROWSER_MODE: nie Koduj ani dekoduje znaków po "#" lub "" i nie usuwa odstępu kończącego po "". Jeśli ta wartość nie jest określona, cały adres URL jest zakodowany, a końcowy biały znak jest usuwany.

- ATL_URL _DECODE: konwertuje wszystkie sekwencje% XX na znaki, w tym sekwencje ucieczki, przed przeanalizowanie adresu URL.

- ATL_URL _ENCODE_PERCENT: koduje wszelkie napotkane znaki procentu. Domyślnie znaki procentowe nie są zakodowane.

- ATL_URL _ENCODE_SPACES_ONLY: koduje tylko spacje.

- ATL_URL _NO_ENCODE: nie konwertuje niebezpiecznych znaków na sekwencje ucieczki.

- ATL_URL _NO_META: nie usuwa z adresu URL meta sekwencji (takich jak "." i "..").

### <a name="return-value"></a>Wartość zwracana

Zwraca wartość TRUE dla sukcesu, FALSE w przypadku błędu.

### <a name="remarks"></a>Uwagi

Konwersja na postać kanoniczną obejmuje konwertowanie niebezpiecznych znaków i spacji na sekwencje ucieczki.

## <a name="curlclear"></a><a name="clear"></a> Zwinięcie:: Clear

Wywołaj tę metodę, aby wyczyścić wszystkie pola adresu URL.

```
inline void Clear() throw();
```

## <a name="curlcrackurl"></a><a name="crackurl"></a> Zwinięcie:: CrackUrl

Wywołaj tę metodę, aby zdekodować i przeanalizować adres URL.

```
BOOL CrackUrl(LPCTSTR lpszUrl, DWORD dwFlags = 0) throw();
```

### <a name="parameters"></a>Parametry

*lpszUrl*<br/>
Adres URL.

*flagiDW*<br/>
Określ ATL_URL_DECODE lub ATL_URL_ESCAPE, aby przekonwertować wszystkie znaki ucieczki w *lpszURL* na ich rzeczywiste wartości po przeanalizowaniu. (Przed Visual C++ 2005 ATL_URL_DECODE konwertowane wszystkie znaki ucieczki przed analizą).

### <a name="return-value"></a>Wartość zwracana

Zwraca wartość TRUE dla sukcesu, FALSE w przypadku błędu.

## <a name="curlcreateurl"></a><a name="createurl"></a> Zwinięcie:: CreateUrl

Ta metoda służy do konstrukcji ciągu adresu URL na podstawie pól składnika zazwinięcia obiektu.

```
inline BOOL CreateUrl(
    LPTSTR lpszUrl,
    DWORD* pdwMaxLength,
    DWORD dwFlags = 0) const throw();
```

### <a name="parameters"></a>Parametry

*lpszUrl*<br/>
Bufor ciągu przechowujący pełny ciąg adresu URL.

*pdwMaxLength*<br/>
Maksymalna długość buforu ciągu *lpszURL* .

*flagiDW*<br/>
Określ ATL_URL_ESCAPE, aby przekonwertować wszystkie znaki ucieczki w *lpszURL* na ich rzeczywiste wartości.

### <a name="return-value"></a>Wartość zwracana

Zwraca wartość TRUE dla sukcesu, FALSE w przypadku błędu.

### <a name="remarks"></a>Uwagi

Ta metoda dołącza poszczególne pola w celu skonstruowania pełnego ciągu adresu URL przy użyciu następującego formatu:

**\<scheme>://\<user>:\<pass>\@\<domain>:\<port>\<path>\<extra>**

Podczas wywoływania tej metody parametr *pdwMaxLength* powinien początkowo zawierać maksymalną długość buforu ciągu, do którego odwołuje się parametr *lpszURL* . Wartość parametru *pdwMaxLength* zostanie zaktualizowana o rzeczywistą długość ciągu adresu URL.

### <a name="example"></a>Przykład

Ten przykład pokazuje, jak utworzyć obiekt zwinięcie i pobrać jego ciąg adresu URL

[!code-cpp[NVC_ATL_Utilities#133](../../atl/codesnippet/cpp/curl-class_1.cpp)]

## <a name="curlcurl"></a><a name="curl"></a> Zwinięcie:: zwinięcie

Konstruktor.

```
CUrl() throw();
CUrl(const CUrl& urlThat) throw();
```

### <a name="parameters"></a>Parametry

*urlThat*<br/>
`CUrl`Obiekt do skopiowania w celu utworzenia adresu URL.

## <a name="curlcurl"></a><a name="dtor"></a> Zwinięcie:: ~ zwinięcie

Destruktor.

```
~CUrl() throw();
```

## <a name="curlgetextrainfo"></a><a name="getextrainfo"></a> Zwinięcie:: GetExtraInfo

Wywołaj tę metodę, aby uzyskać dodatkowe informacje (takie jak *tekst* lub # *tekst*) od adresu URL.

```
inline LPCTSTR GetExtraInfo() const throw();
```

### <a name="return-value"></a>Wartość zwracana

Zwraca ciąg zawierający dodatkowe informacje.

## <a name="curlgetextrainfolength"></a><a name="getextrainfolength"></a> Zwinięcie:: GetExtraInfoLength

Wywołaj tę metodę, aby uzyskać informacje o długości dodatkowych informacji (takich jak *tekst* lub # *tekst*) do pobrania z adresu URL.

```
inline DWORD GetExtraInfoLength() const throw();
```

### <a name="return-value"></a>Wartość zwracana

Zwraca długość ciągu zawierającego dodatkowe informacje.

## <a name="curlgethostname"></a><a name="gethostname"></a> Zwinięcie:: gethostname

Wywołaj tę metodę, aby pobrać nazwę hosta z adresu URL.

```
inline LPCTSTR GetHostName() const throw();
```

### <a name="return-value"></a>Wartość zwracana

Zwraca nazwę hosta.

## <a name="curlgethostnamelength"></a><a name="gethostnamelength"></a> Zwinięcie:: GetHostNameLength

Wywołaj tę metodę, aby uzyskać długość nazwy hosta.

```
inline DWORD GetHostNameLength() const throw();
```

### <a name="return-value"></a>Wartość zwracana

Zwraca długość nazwy hosta.

## <a name="curlgetpassword"></a><a name="getpassword"></a> Zwinięcie:: GetPassword

Wywołaj tę metodę, aby uzyskać hasło z adresu URL.

```
inline LPCTSTR GetPassword() const throw();
```

### <a name="return-value"></a>Wartość zwracana

Zwraca hasło.

## <a name="curlgetpasswordlength"></a><a name="getpasswordlength"></a> Zwinięcie:: GetPasswordLength

Wywołaj tę metodę, aby uzyskać długość hasła.

```
inline DWORD GetPasswordLength() const throw();
```

### <a name="return-value"></a>Wartość zwracana

Zwraca długość hasła.

## <a name="curlgetportnumber"></a><a name="getportnumber"></a> Zwinięcie:: GetPortNumber

Wywołaj tę metodę, aby pobrać numer portu.

```
inline ATL_URL_PORT GetPortNumber() const throw();
```

### <a name="return-value"></a>Wartość zwracana

Zwraca numer portu.

## <a name="curlgetscheme"></a><a name="getscheme"></a> Zwinięcie:: GetSchema

Wywołaj tę metodę, aby uzyskać schemat adresu URL.

```
inline ATL_URL_SCHEME GetScheme() const throw();
```

### <a name="return-value"></a>Wartość zwracana

Zwraca wartość [ATL_URL_SCHEME](atl-url-scheme-enum.md) opisującą schemat adresu URL.

## <a name="curlgetschemename"></a><a name="getschemename"></a> Zwinięcie:: getschemaname

Wywołaj tę metodę, aby pobrać nazwę schematu adresu URL.

```
inline LPCTSTR GetSchemeName() const throw();
```

### <a name="return-value"></a>Wartość zwracana

Zwraca nazwę schematu adresu URL (na przykład "http" lub "FTP").

## <a name="curlgetschemenamelength"></a><a name="getschemenamelength"></a> Zwinięcie:: GetSchemeNameLength

Wywołaj tę metodę, aby uzyskać długość nazwy schematu adresu URL.

```
inline DWORD GetSchemeNameLength() const throw();
```

### <a name="return-value"></a>Wartość zwracana

Zwraca długość nazwy schematu adresu URL.

## <a name="curlgeturllength"></a><a name="geturllength"></a> Zwinięcie:: GetUrlLength

Wywołaj tę metodę, aby uzyskać długość adresu URL.

```
inline DWORD GetUrlLength() const throw();
```

### <a name="return-value"></a>Wartość zwracana

Zwraca długość adresu URL.

## <a name="curlgeturlpath"></a><a name="geturlpath"></a> Zwinięcie:: GetUrlPath

Wywołaj tę metodę, aby uzyskać ścieżkę adresu URL.

```
inline LPCTSTR GetUrlPath() const throw();
```

### <a name="return-value"></a>Wartość zwracana

Zwraca ścieżkę URL.

## <a name="curlgeturlpathlength"></a><a name="geturlpathlength"></a> Zwinięcie:: GetUrlPathLength

Wywołaj tę metodę, aby uzyskać długość ścieżki URL.

```
inline DWORD GetUrlPathLength() const throw();
```

### <a name="return-value"></a>Wartość zwracana

Zwraca długość ścieżki URL.

## <a name="curlgetusername"></a><a name="getusername"></a> Zwinięcie:: GetUserName

Wywołaj tę metodę, aby pobrać nazwę użytkownika z adresu URL.

```
inline LPCTSTR GetUserName() const throw();
```

### <a name="return-value"></a>Wartość zwracana

Zwraca nazwę użytkownika.

## <a name="curlgetusernamelength"></a><a name="getusernamelength"></a> Zwinięcie:: GetUserNameLength

Wywołaj tę metodę, aby uzyskać długość nazwy użytkownika.

```
inline DWORD GetUserNameLength() const throw();
```

### <a name="return-value"></a>Wartość zwracana

Zwraca długość nazwy użytkownika.

## <a name="curloperator-"></a><a name="operator_eq"></a> Zwinięcie:: operator =

Przypisuje określony `CUrl` obiekt do bieżącego `CUrl` obiektu.

```
CUrl& operator= (const CUrl& urlThat) throw();
```

### <a name="parameters"></a>Parametry

*urlThat*<br/>
`CUrl`Obiekt, który ma zostać skopiowany do bieżącego obiektu.

### <a name="return-value"></a>Wartość zwracana

Zwraca odwołanie do bieżącego obiektu.

## <a name="curlsetextrainfo"></a><a name="setextrainfo"></a> Zwinięcie:: SetExtraInfo

Wywołaj tę metodę, aby ustawić dodatkowe informacje (takie jak *tekst* lub # *tekst*) adresu URL.

```
inline BOOL SetExtraInfo(LPCTSTR lpszInfo) throw();
```

### <a name="parameters"></a>Parametry

*lpszInfo*<br/>
Ciąg zawierający dodatkowe informacje do uwzględnienia w adresie URL.

### <a name="return-value"></a>Wartość zwracana

Zwraca wartość TRUE dla sukcesu, FALSE w przypadku błędu.

## <a name="curlsethostname"></a><a name="sethostname"></a> Zwinięcie:: sethostname

Wywołaj tę metodę, aby ustawić nazwę hosta.

```
inline BOOL SetHostName(LPCTSTR lpszHost) throw();
```

### <a name="parameters"></a>Parametry

*lpszHost*<br/>
Nazwa hosta.

### <a name="return-value"></a>Wartość zwracana

Zwraca wartość TRUE dla sukcesu, FALSE w przypadku błędu.

## <a name="curlsetpassword"></a><a name="setpassword"></a> Zwinięcie:: SetPassword

Wywołaj tę metodę, aby ustawić hasło.

```
inline BOOL SetPassword(LPCTSTR lpszPass) throw();
```

### <a name="parameters"></a>Parametry

*lpszPass*<br/>
Hasło.

### <a name="return-value"></a>Wartość zwracana

Zwraca wartość TRUE dla sukcesu, FALSE w przypadku błędu.

## <a name="curlsetportnumber"></a><a name="setportnumber"></a> Zwinięcie:: SetPortNumber

Wywołaj tę metodę, aby ustawić numer portu.

```
inline BOOL SetPortNumber(ATL_URL_PORT nPrt) throw();
```

### <a name="parameters"></a>Parametry

*nPrt*<br/>
Numer portu.

### <a name="return-value"></a>Wartość zwracana

Zwraca wartość TRUE dla sukcesu, FALSE w przypadku błędu.

## <a name="curlsetscheme"></a><a name="setscheme"></a> Zwinięcie:: setschema

Wywołaj tę metodę, aby ustawić schemat adresu URL.

```
inline BOOL SetScheme(ATL_URL_SCHEME nScheme) throw();
```

### <a name="parameters"></a>Parametry

*nScheme*<br/>
Jedna z wartości [ATL_URL_SCHEME](atl-url-scheme-enum.md) dla schematu.

### <a name="return-value"></a>Wartość zwracana

Zwraca wartość TRUE dla sukcesu, FALSE w przypadku błędu.

### <a name="remarks"></a>Uwagi

Można również ustawić schemat według nazwy (zobacz [zwinięcie:: Setschemaname](#setschemename)).

## <a name="curlsetschemename"></a><a name="setschemename"></a> Zwinięcie:: setschemaname

Wywołaj tę metodę, aby ustawić nazwę schematu adresu URL.

```
inline BOOL SetSchemeName(LPCTSTR lpszSchm) throw();
```

### <a name="parameters"></a>Parametry

*lpszSchm*<br/>
Nazwa schematu adresu URL.

### <a name="return-value"></a>Wartość zwracana

Zwraca wartość TRUE dla sukcesu, FALSE w przypadku błędu.

### <a name="remarks"></a>Uwagi

Możesz również ustawić schemat przy użyciu stałej [ATL_URL_SCHEME](atl-url-scheme-enum.md) (zobacz [zwinięcie:: setschema](#setscheme)).

## <a name="curlseturlpath"></a><a name="seturlpath"></a> Zwinięcie:: SetUrlPath

Wywołaj tę metodę, aby ustawić ścieżkę adresu URL.

```
inline BOOL SetUrlPath(LPCTSTR lpszPath) throw();
```

### <a name="parameters"></a>Parametry

*lpszPath*<br/>
Ścieżka adresu URL.

### <a name="return-value"></a>Wartość zwracana

Zwraca wartość TRUE dla sukcesu, FALSE w przypadku błędu.

## <a name="curlsetusername"></a><a name="setusername"></a> Zwinięcie:: SetUserName

Wywołaj tę metodę, aby ustawić nazwę użytkownika.

```
inline BOOL SetUserName(LPCTSTR lpszUser) throw();
```

### <a name="parameters"></a>Parametry

*lpszUser*<br/>
Nazwa użytkownika.

### <a name="return-value"></a>Wartość zwracana

Zwraca wartość TRUE dla sukcesu, FALSE w przypadku błędu.

## <a name="see-also"></a>Zobacz też

[Klasy](../../atl/reference/atl-classes.md)
