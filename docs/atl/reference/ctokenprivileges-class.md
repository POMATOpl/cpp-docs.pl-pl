---
description: 'Dowiedz się więcej na temat: Klasa CTokenPrivileges'
title: Klasa CTokenPrivileges
ms.date: 11/04/2016
f1_keywords:
- CTokenPrivileges
- ATLSECURITY/ATL::CTokenPrivileges
- ATLSECURITY/ATL::CTokenPrivileges::CTokenPrivileges
- ATLSECURITY/ATL::CTokenPrivileges::Add
- ATLSECURITY/ATL::CTokenPrivileges::Delete
- ATLSECURITY/ATL::CTokenPrivileges::DeleteAll
- ATLSECURITY/ATL::CTokenPrivileges::GetCount
- ATLSECURITY/ATL::CTokenPrivileges::GetDisplayNames
- ATLSECURITY/ATL::CTokenPrivileges::GetLength
- ATLSECURITY/ATL::CTokenPrivileges::GetLuidsAndAttributes
- ATLSECURITY/ATL::CTokenPrivileges::GetNamesAndAttributes
- ATLSECURITY/ATL::CTokenPrivileges::GetPTOKEN_PRIVILEGES
- ATLSECURITY/ATL::CTokenPrivileges::LookupPrivilege
helpviewer_keywords:
- CTokenPrivileges class
ms.assetid: 89590105-f001-4014-870d-142926091231
ms.openlocfilehash: 22953c0d2aa8c4fa7dd0b79b001e46797bd3ca25
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97140312"
---
# <a name="ctokenprivileges-class"></a>Klasa CTokenPrivileges

Ta klasa jest otoką dla `TOKEN_PRIVILEGES` struktury.

> [!IMPORTANT]
> Tej klasy i jej elementów członkowskich nie można używać w aplikacjach, które są wykonywane w środowisko wykonawcze systemu Windows.

## <a name="syntax"></a>Składnia

```
class CTokenPrivileges
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CTokenPrivileges::CTokenPrivileges](#ctokenprivileges)|Konstruktor.|
|[CTokenPrivileges:: ~ CTokenPrivileges](#dtor)|Destruktor.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CTokenPrivileges:: Add](#add)|Dodaje co najmniej jedno uprawnienia do `CTokenPrivileges` obiektu.|
|[CTokenPrivileges::D Usuń](#delete)|Usuwa uprawnienie z `CTokenPrivileges` obiektu.|
|[CTokenPrivileges::D eleteAll](#deleteall)|Usuwa wszystkie uprawnienia z `CTokenPrivileges` obiektu.|
|[CTokenPrivileges:: GetCount](#getcount)|Zwraca liczbę wpisów uprawnień w `CTokenPrivileges` obiekcie.|
|[CTokenPrivileges:: GetDisplayNames](#getdisplaynames)|Pobiera nazwy wyświetlane dla uprawnień zawartych w `CTokenPrivileges` obiekcie.|
|[CTokenPrivileges:: GetLength](#getlength)|Zwraca rozmiar buforu w bajtach wymaganych do przechowywania `TOKEN_PRIVILEGES` struktury reprezentowanej przez `CTokenPrivileges` obiekt.|
|[CTokenPrivileges::GetLuidsAndAttributes](#getluidsandattributes)|Pobiera lokalne unikatowe identyfikatory (LUID) i flagi atrybutów z `CTokenPrivileges` obiektu.|
|[CTokenPrivileges::GetNamesAndAttributes](#getnamesandattributes)|Pobiera nazwy uprawnień i flag atrybutów z `CTokenPrivileges` obiektu.|
|[CTokenPrivileges:: GetPTOKEN_PRIVILEGES](#getptoken_privileges)|Zwraca wskaźnik do `TOKEN_PRIVILEGES` struktury.|
|[CTokenPrivileges::LookupPrivilege](#lookupprivilege)|Pobiera atrybut skojarzony z daną nazwą uprawnienia.|

### <a name="public-operators"></a>Operatory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CTokenPrivileges:: operator const TOKEN_PRIVILEGES *](#operator_const_token_privileges__star)|Rzutuje wartość na wskaźnik do `TOKEN_PRIVILEGES` struktury.|
|[CTokenPrivileges:: operator =](#operator_eq)|Operator przypisania.|

## <a name="remarks"></a>Uwagi

[Token dostępu](/windows/win32/SecAuthZ/access-tokens) jest obiektem opisującym kontekst zabezpieczeń procesu lub wątku i jest przypisywany do każdego użytkownika zalogowanego w systemie Windows.

Token dostępu służy do opisywania różnych uprawnień zabezpieczeń przyznanych każdemu użytkownikowi. Uprawnienie składa się z 64-bitowego numeru zwanego lokalnie unikatowym identyfikatorem ( [LUID](/windows/win32/api/winnt/ns-winnt-luid)) i ciągiem deskryptora.

`CTokenPrivileges`Klasa jest otoką dla struktury [TOKEN_PRIVILEGES](/windows/win32/api/winnt/ns-winnt-token_privileges) i zawiera 0 lub więcej uprawnień. Uprawnienia można dodawać, usuwać lub wykonywać zapytania przy użyciu podanych metod klasy.

Aby zapoznać się z wprowadzeniem do modelu kontroli dostępu w systemie Windows, zobacz [Access Control](/windows/win32/SecAuthZ/access-control) w Windows SDK.

## <a name="requirements"></a>Wymagania

**Nagłówek:** atlsecurity. h

## <a name="ctokenprivilegesadd"></a><a name="add"></a> CTokenPrivileges:: Add

Dodaje co najmniej jedno uprawnienia do `CTokenPrivileges` obiektu tokenu dostępu.

```
bool Add(LPCTSTR pszPrivilege, bool bEnable) throw(...);
void Add(const TOKEN_PRIVILEGES& rPrivileges) throw(...);
```

### <a name="parameters"></a>Parametry

*pszPrivilege*<br/>
Wskaźnik na ciąg zakończony znakiem null, który określa nazwę uprawnienia, zgodnie z definicją w WINNT. H plik nagłówkowy.

*bEnable*<br/>
Jeśli wartość jest równa true, uprawnienie jest włączone. Jeśli wartość jest równa false, uprawnienie jest wyłączone.

*rPrivileges*<br/>
Odwołanie do struktury [TOKEN_PRIVILEGES](/windows/win32/api/winnt/ns-winnt-token_privileges) . Uprawnienia i atrybuty są kopiowane z tej struktury i dodawane do `CTokenPrivileges` obiektu.

### <a name="return-value"></a>Wartość zwracana

Pierwsza forma tej metody zwraca wartość true, jeśli uprawnienia zostały pomyślnie dodane, w przeciwnym razie false.

## <a name="ctokenprivilegesctokenprivileges"></a><a name="ctokenprivileges"></a> CTokenPrivileges::CTokenPrivileges

Konstruktor.

```
CTokenPrivileges() throw();
CTokenPrivileges(const CTokenPrivileges& rhs) throw(... );
CTokenPrivileges(const TOKEN_PRIVILEGES& rPrivileges) throw(...);
```

### <a name="parameters"></a>Parametry

*RHS*<br/>
`CTokenPrivileges`Obiekt, który ma zostać przypisany do nowego obiektu.

*rPrivileges*<br/>
Struktura [TOKEN_PRIVILEGES](/windows/win32/api/winnt/ns-winnt-token_privileges) , która ma zostać przypisana do nowego `CTokenPrivileges` obiektu.

### <a name="remarks"></a>Uwagi

`CTokenPrivileges`Obiekt można opcjonalnie utworzyć przy użyciu `TOKEN_PRIVILEGES` struktury lub wcześniej zdefiniowanego `CTokenPrivileges` obiektu.

## <a name="ctokenprivilegesctokenprivileges"></a><a name="dtor"></a> CTokenPrivileges:: ~ CTokenPrivileges

Destruktor.

```
virtual ~CTokenPrivileges() throw();
```

### <a name="remarks"></a>Uwagi

Destruktor zwalnia wszystkie przydzieloną zasoby.

## <a name="ctokenprivilegesdelete"></a><a name="delete"></a> CTokenPrivileges::D Usuń

Usuwa uprawnienie z `CTokenPrivileges` obiektu token dostępu.

```
bool Delete(LPCTSTR pszPrivilege) throw();
```

### <a name="parameters"></a>Parametry

*pszPrivilege*<br/>
Wskaźnik na ciąg zakończony znakiem null, który określa nazwę uprawnienia, zgodnie z definicją w WINNT. H plik nagłówkowy. Na przykład ten parametr może określać stałą SE_SECURITY_NAME lub odpowiedni ciąg "SeSecurityPrivilege".

### <a name="return-value"></a>Wartość zwracana

Zwraca wartość PRAWDA, jeśli uprawnienie zostało pomyślnie usunięte, w przeciwnym razie false.

### <a name="remarks"></a>Uwagi

Ta metoda jest przydatna jako narzędzie do tworzenia tokenów z ograniczeniami.

## <a name="ctokenprivilegesdeleteall"></a><a name="deleteall"></a> CTokenPrivileges::D eleteAll

Usuwa wszystkie uprawnienia z `CTokenPrivileges` obiektu token dostępu.

```cpp
void DeleteAll() throw();
```

### <a name="remarks"></a>Uwagi

Usuwa wszystkie uprawnienia zawarte w `CTokenPrivileges` obiekcie tokenu dostępu.

## <a name="ctokenprivilegesgetdisplaynames"></a><a name="getdisplaynames"></a> CTokenPrivileges:: GetDisplayNames

Pobiera nazwy wyświetlane dla uprawnień zawartych w `CTokenPrivileges` obiekcie tokenu dostępu.

```cpp
void GetDisplayNames(CNames* pDisplayNames) const throw(...);
```

### <a name="parameters"></a>Parametry

*pDisplayNames*<br/>
Wskaźnik do tablicy `CString` obiektów. `CNames` jest zdefiniowany jako element typedef: `CTokenPrivileges::CAtlArray<CString>` .

### <a name="remarks"></a>Uwagi

Parametr `pDisplayNames` jest wskaźnikiem do tablicy `CString` obiektów, które otrzymają nazwy wyświetlane odpowiadające uprawnienia zawarte w `CTokenPrivileges` obiekcie. Ta metoda pobiera nazwy wyświetlane tylko dla uprawnień określonych w sekcji zdefiniowane uprawnienia w pliku WINNT. H.

Ta metoda pobiera nazwę, którą można wyświetlić: na przykład, jeśli nazwa atrybutu jest SE_REMOTE_SHUTDOWN_NAME, nazwa wyświetlana to "Wymuś zamknięcie z systemu zdalnego". Aby uzyskać nazwę systemu, należy użyć [CTokenPrivileges:: GetNamesAndAttributes](#getnamesandattributes).

## <a name="ctokenprivilegesgetcount"></a><a name="getcount"></a> CTokenPrivileges:: GetCount

Zwraca liczbę wpisów uprawnień w `CTokenPrivileges` obiekcie.

```
UINT GetCount() const throw();
```

### <a name="return-value"></a>Wartość zwracana

Zwraca liczbę uprawnień zawartych w `CTokenPrivileges` obiekcie.

## <a name="ctokenprivilegesgetlength"></a><a name="getlength"></a> CTokenPrivileges:: GetLength

Zwraca długość `CTokenPrivileges` obiektu.

```
UINT GetLength() const throw();
```

### <a name="return-value"></a>Wartość zwracana

Zwraca liczbę bajtów wymaganą do przechowywania `TOKEN_PRIVILEGES` struktury reprezentowanej przez `CTokenPrivileges` obiekt, łącznie ze wszystkimi wpisami uprawnień, które zawiera.

## <a name="ctokenprivilegesgetluidsandattributes"></a><a name="getluidsandattributes"></a> CTokenPrivileges::GetLuidsAndAttributes

Pobiera lokalne unikatowe identyfikatory (LUID) i flagi atrybutów z `CTokenPrivileges` obiektu.

```cpp
void GetLuidsAndAttributes(
    CLUIDArray* pPrivileges,
    CAttributes* pAttributes = NULL) const throw(...);
```

### <a name="parameters"></a>Parametry

*pPrivileges*<br/>
Wskaźnik do tablicy obiektów [LUID](/windows/win32/api/winnt/ns-winnt-luid) . `CLUIDArray` jest elementem TypeDef zdefiniowanym jako `CAtlArray<LUID> CLUIDArray` .

*pAttributes*<br/>
Wskaźnik na tablicę obiektów typu DWORD. Jeśli ten parametr zostanie pominięty lub ma wartość NULL, atrybuty nie zostaną pobrane. `CAttributes` jest elementem TypeDef zdefiniowanym jako `CAtlArray <DWORD> CAttributes` .

### <a name="remarks"></a>Uwagi

Ta metoda spowoduje Wyliczenie wszystkich uprawnień zawartych w `CTokenPrivileges` obiekcie token dostępu i umieszczenie pojedynczych identyfikatorów LUID oraz (opcjonalnie) flag atrybutów do obiektów array.

## <a name="ctokenprivilegesgetnamesandattributes"></a><a name="getnamesandattributes"></a> CTokenPrivileges::GetNamesAndAttributes

Pobiera nazwy i flagi atrybutów z `CTokenPrivileges` obiektu.

```cpp
void GetNamesAndAttributes(
    CNames* pNames,
    CAttributes* pAttributes = NULL) const throw(...);
```

### <a name="parameters"></a>Parametry

*pNames*<br/>
Wskaźnik na tablicę `CString` obiektów. `CNames` jest elementem TypeDef zdefiniowanym jako `CAtlArray <CString> CNames` .

*pAttributes*<br/>
Wskaźnik na tablicę obiektów typu DWORD. Jeśli ten parametr zostanie pominięty lub ma wartość NULL, atrybuty nie zostaną pobrane. `CAttributes` jest elementem TypeDef zdefiniowanym jako `CAtlArray <DWORD> CAttributes` .

### <a name="remarks"></a>Uwagi

Ta metoda wylicza wszystkie uprawnienia zawarte w `CTokenPrivileges` obiekcie, umieszczając nazwę i (opcjonalnie) flagi atrybutów do obiektów array.

Ta metoda pobiera nazwę atrybutu, a nie nazwę, która ma być wyświetlana: na przykład, jeśli nazwa atrybutu jest SE_REMOTE_SHUTDOWN_NAME, Nazwa systemowa to "SeRemoteShutdownPrivilege". Aby uzyskać nazwę, użyj metody [CTokenPrivileges:: GetDisplayNames](#getdisplaynames).

## <a name="ctokenprivilegesgetptoken_privileges"></a><a name="getptoken_privileges"></a> CTokenPrivileges:: GetPTOKEN_PRIVILEGES

Zwraca wskaźnik do `TOKEN_PRIVILEGES` struktury.

```
const TOKEN_PRIVILEGES* GetPTOKEN_PRIVILEGES() const throw(...);
```

### <a name="return-value"></a>Wartość zwracana

Zwraca wskaźnik do struktury [TOKEN_PRIVILEGES](/windows/win32/api/winnt/ns-winnt-token_privileges) .

## <a name="ctokenprivilegeslookupprivilege"></a><a name="lookupprivilege"></a> CTokenPrivileges::LookupPrivilege

Pobiera atrybut skojarzony z daną nazwą uprawnienia.

```
bool LookupPrivilege(
    LPCTSTR pszPrivilege,
    DWORD* pdwAttributes = NULL) const throw(...);
```

### <a name="parameters"></a>Parametry

*pszPrivilege*<br/>
Wskaźnik na ciąg zakończony znakiem null, który określa nazwę uprawnienia, zgodnie z definicją w WINNT. H plik nagłówkowy. Na przykład ten parametr może określać stałą SE_SECURITY_NAME lub odpowiedni ciąg "SeSecurityPrivilege".

*pdwAttributes*<br/>
Wskaźnik do zmiennej, która otrzymuje atrybuty.

### <a name="return-value"></a>Wartość zwracana

Zwraca wartość true, jeśli atrybut został pobrany pomyślnie, w przeciwnym razie false.

## <a name="ctokenprivilegesoperator-"></a><a name="operator_eq"></a> CTokenPrivileges:: operator =

Operator przypisania.

```
CTokenPrivileges& operator= (const TOKEN_PRIVILEGES& rPrivileges) throw(...);
CTokenPrivileges& operator= (const CTokenPrivileges& rhs) throw(...);
```

### <a name="parameters"></a>Parametry

*rPrivileges*<br/>
Struktura [TOKEN_PRIVILEGES](/windows/win32/api/winnt/ns-winnt-token_privileges) , która ma zostać przypisana do `CTokenPrivileges` obiektu.

*RHS*<br/>
`CTokenPrivileges`Obiekt, który ma zostać przypisany do obiektu.

### <a name="return-value"></a>Wartość zwracana

Zwraca zaktualizowany `CTokenPrivileges` obiekt.

## <a name="ctokenprivilegesoperator-const-token_privileges-"></a><a name="operator_const_token_privileges__star"></a> CTokenPrivileges:: operator const TOKEN_PRIVILEGES \*

Rzutuje wartość na wskaźnik do `TOKEN_PRIVILEGES` struktury.

```
operator const TOKEN_PRIVILEGES *() const throw(...);
```

### <a name="remarks"></a>Uwagi

Rzutuje wartość na wskaźnik do struktury [TOKEN_PRIVILEGES](/windows/win32/api/winnt/ns-winnt-token_privileges) .

## <a name="see-also"></a>Zobacz też

[Przykład zabezpieczeń](../../overview/visual-cpp-samples.md)<br/>
[TOKEN_PRIVILEGES](/windows/win32/api/winnt/ns-winnt-token_privileges)<br/>
[LUID](/windows/win32/api/winnt/ns-winnt-luid)<br/>
[LUID_AND_ATTRIBUTES](/windows/win32/api/winnt/ns-winnt-luid_and_attributes)<br/>
[Przegląd klas](../../atl/atl-class-overview.md)<br/>
[Funkcje globalne zabezpieczeń](../../atl/reference/security-global-functions.md)
