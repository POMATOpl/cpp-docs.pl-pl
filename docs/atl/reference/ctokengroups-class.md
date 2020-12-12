---
description: 'Dowiedz się więcej na temat: Klasa CTokenGroups'
title: Klasa CTokenGroups
ms.date: 11/04/2016
f1_keywords:
- CTokenGroups
- ATLSECURITY/ATL::CTokenGroups
- ATLSECURITY/ATL::CTokenGroups::CTokenGroups
- ATLSECURITY/ATL::CTokenGroups::Add
- ATLSECURITY/ATL::CTokenGroups::Delete
- ATLSECURITY/ATL::CTokenGroups::DeleteAll
- ATLSECURITY/ATL::CTokenGroups::GetCount
- ATLSECURITY/ATL::CTokenGroups::GetLength
- ATLSECURITY/ATL::CTokenGroups::GetPTOKEN_GROUPS
- ATLSECURITY/ATL::CTokenGroups::GetSidsAndAttributes
- ATLSECURITY/ATL::CTokenGroups::LookupSid
helpviewer_keywords:
- CTokenGroups class
ms.assetid: 2ab08076-4b08-4487-bc70-ec6dee304190
ms.openlocfilehash: 3d6633afbd649aa175196f1fae8e62afdf784f99
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97140351"
---
# <a name="ctokengroups-class"></a>Klasa CTokenGroups

Ta klasa jest otoką dla `TOKEN_GROUPS` struktury.

> [!IMPORTANT]
> Tej klasy i jej elementów członkowskich nie można używać w aplikacjach, które są wykonywane w środowisko wykonawcze systemu Windows.

## <a name="syntax"></a>Składnia

```
class CTokenGroups
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CTokenGroups::CTokenGroups](#ctokengroups)|Konstruktor.|
|[CTokenGroups:: ~ CTokenGroups](#dtor)|Destruktor.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CTokenGroups:: Add](#add)|Dodaje `CSid` lub istniejącą `TOKEN_GROUPS` strukturę do `CTokenGroups` obiektu.|
|[CTokenGroups::D Usuń](#delete)|Usuwa `CSid` z obiektu i skojarzone z nim atrybuty `CTokenGroups` .|
|[CTokenGroups::D eleteAll](#deleteall)|Usuwa wszystkie `CSid` obiekty i skojarzone z nimi atrybuty z `CTokenGroups` obiektu.|
|[CTokenGroups:: GetCount](#getcount)|Zwraca liczbę `CSid` obiektów i skojarzonych z nimi atrybutów zawartych w `CTokenGroups` obiekcie.|
|[CTokenGroups:: GetLength](#getlength)|Zwraca rozmiar `CTokenGroups` obiektu.|
|[CTokenGroups:: GetPTOKEN_GROUPS](#getptoken_groups)|Pobiera wskaźnik do `TOKEN_GROUPS` struktury.|
|[CTokenGroups::GetSidsAndAttributes](#getsidsandattributes)|Pobiera `CSid` obiekty i atrybuty należące do `CTokenGroups` obiektu.|
|[CTokenGroups::LookupSid](#lookupsid)|Pobiera atrybuty skojarzone z `CSid` obiektem.|

### <a name="public-operators"></a>Operatory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CTokenGroups:: operator const TOKEN_GROUPS *](#operator_const_token_groups__star)|Rzutuje `CTokenGroups` obiekt na wskaźnik do `TOKEN_GROUPS` struktury.|
|[CTokenGroups:: operator =](#operator_eq)|Operator przypisania.|

## <a name="remarks"></a>Uwagi

[Token dostępu](/windows/win32/SecAuthZ/access-tokens) jest obiektem opisującym kontekst zabezpieczeń procesu lub wątku i jest przypisywany do każdego użytkownika zalogowanego w systemie Windows.

`CTokenGroups`Klasa jest otoką dla struktury [TOKEN_GROUPS](/windows/win32/api/winnt/ns-winnt-token_groups) zawierającej informacje o identyfikatorach zabezpieczeń grupy (SID) w tokenie dostępu.

Aby zapoznać się z wprowadzeniem do modelu kontroli dostępu w systemie Windows, zobacz [Access Control](/windows/win32/SecAuthZ/access-control) w Windows SDK.

## <a name="requirements"></a>Wymagania

**Nagłówek:** atlsecurity. h

## <a name="ctokengroupsadd"></a><a name="add"></a> CTokenGroups:: Add

Dodaje `CSid` lub istniejącą `TOKEN_GROUPS` strukturę do `CTokenGroups` obiektu.

```cpp
void Add(const CSid& rSid, DWORD dwAttributes) throw(... );
void Add(const TOKEN_GROUPS& rTokenGroups) throw(...);
```

### <a name="parameters"></a>Parametry

*rSid*<br/>
Obiekt [CSid](../../atl/reference/csid-class.md) .

*dwAttributes*<br/>
Atrybuty, które mają zostać skojarzone z `CSid` obiektem.

*rTokenGroups*<br/>
Struktura [TOKEN_GROUPS](/windows/win32/api/winnt/ns-winnt-token_groups) .

### <a name="remarks"></a>Uwagi

Te metody dodają jeden lub więcej `CSid` obiektów i skojarzonych z nimi atrybutów do `CTokenGroups` obiektu.

## <a name="ctokengroupsctokengroups"></a><a name="ctokengroups"></a> CTokenGroups::CTokenGroups

Konstruktor.

```
CTokenGroups() throw();
CTokenGroups(const CTokenGroups& rhs) throw(... );
CTokenGroups(const TOKEN_GROUPS& rhs) throw(...);
```

### <a name="parameters"></a>Parametry

*RHS*<br/>
`CTokenGroups`Struktura obiektu lub [TOKEN_GROUPS](/windows/win32/api/winnt/ns-winnt-token_groups) , z którym ma zostać skonstruowany `CTokenGroups` obiekt.

### <a name="remarks"></a>Uwagi

`CTokenGroups`Obiekt można opcjonalnie utworzyć przy użyciu `TOKEN_GROUPS` struktury lub wcześniej zdefiniowanego `CTokenGroups` obiektu.

## <a name="ctokengroupsctokengroups"></a><a name="dtor"></a> CTokenGroups:: ~ CTokenGroups

Destruktor.

```
virtual ~CTokenGroups() throw();
```

### <a name="remarks"></a>Uwagi

Destruktor zwalnia wszystkie przydzieloną zasoby.

## <a name="ctokengroupsdelete"></a><a name="delete"></a> CTokenGroups::D Usuń

Usuwa `CSid` z obiektu i skojarzone z nim atrybuty `CTokenGroups` .

```
bool Delete(const CSid& rSid) throw();
```

### <a name="parameters"></a>Parametry

*rSid*<br/>
Obiekt [CSid](../../atl/reference/csid-class.md) , dla którego należy usunąć identyfikator zabezpieczeń (SID) i atrybuty.

### <a name="return-value"></a>Wartość zwracana

Zwraca wartość true `CSid` , jeśli jest usuwany, w przeciwnym razie false.

## <a name="ctokengroupsdeleteall"></a><a name="deleteall"></a> CTokenGroups::D eleteAll

Usuwa wszystkie `CSid` obiekty i skojarzone z nimi atrybuty z `CTokenGroups` obiektu.

```cpp
void DeleteAll() throw();
```

## <a name="ctokengroupsgetcount"></a><a name="getcount"></a> CTokenGroups:: GetCount

Zwraca liczbę `CSid` obiektów zawartych w elemencie `CTokenGroups` .

```
UINT GetCount() const throw();
```

### <a name="return-value"></a>Wartość zwracana

Zwraca liczbę obiektów [CSid](../../atl/reference/csid-class.md) i skojarzonych z nimi atrybutów zawartych w `CTokenGroups` obiekcie.

## <a name="ctokengroupsgetlength"></a><a name="getlength"></a> CTokenGroups:: GetLength

Zwraca rozmiar `CTokenGroup` obiektu.

```
UINT GetLength() const throw();
```

### <a name="remarks"></a>Uwagi

Zwraca łączny rozmiar `CTokenGroup` obiektu w bajtach.

## <a name="ctokengroupsgetptoken_groups"></a><a name="getptoken_groups"></a> CTokenGroups:: GetPTOKEN_GROUPS

Pobiera wskaźnik do `TOKEN_GROUPS` struktury.

```
const TOKEN_GROUPS* GetPTOKEN_GROUPS() const throw(...);
```

### <a name="return-value"></a>Wartość zwracana

Pobiera wskaźnik do struktury [TOKEN_GROUPS](/windows/win32/api/winnt/ns-winnt-token_groups) należącej do `CTokenGroups` obiektu tokenu dostępu.

## <a name="ctokengroupsgetsidsandattributes"></a><a name="getsidsandattributes"></a> CTokenGroups::GetSidsAndAttributes

Pobiera `CSid` obiekty i (opcjonalnie) atrybuty należące do `CTokenGroups` obiektu.

```cpp
void GetSidsAndAttributes(
    CSid::CSidArray* pSids,
    CAtlArray<DWORD>* pAttributes = NULL) const throw(...);
```

### <a name="parameters"></a>Parametry

*pSids*<br/>
Wskaźnik do tablicy obiektów [CSid](../../atl/reference/csid-class.md) .

*pAttributes*<br/>
Wskaźnik na tablicę wartości typu DWORD. Jeśli ten parametr zostanie pominięty lub ma wartość NULL, atrybuty nie zostaną pobrane.

### <a name="remarks"></a>Uwagi

Ta metoda spowoduje Wyliczenie wszystkich `CSid` obiektów zawartych w `CTokenGroups` obiekcie i umieszczenie ich oraz (opcjonalnie) flag atrybutów w obiektach Array.

## <a name="ctokengroupslookupsid"></a><a name="lookupsid"></a> CTokenGroups::LookupSid

Pobiera atrybuty skojarzone z `CSid` obiektem.

```
bool LookupSid(
    const CSid& rSid,
    DWORD* pdwAttributes = NULL) const throw();
```

### <a name="parameters"></a>Parametry

*rSid*<br/>
Obiekt [CSid](../../atl/reference/csid-class.md) .

*pdwAttributes*<br/>
Wskaźnik na wartość typu DWORD, która będzie akceptować `CSid` atrybut obiektu. W przypadku pominięcia lub wartości NULL atrybut nie zostanie pobrany.

### <a name="return-value"></a>Wartość zwracana

Zwraca wartość PRAWDA `CSid` , jeśli znaleziono, w przeciwnym razie false.

### <a name="remarks"></a>Uwagi

Ustawienie *pdwAttributes* na null umożliwia potwierdzenie istnienia `CSid` bez uzyskiwania dostępu do atrybutu. Należy zauważyć, że tej metody nie należy używać do sprawdzania praw dostępu. Aplikacje powinny zamiast tego używać metody [CAccessToken:: CheckTokenMembership](../../atl/reference/caccesstoken-class.md#checktokenmembership) .

## <a name="ctokengroupsoperator-"></a><a name="operator_eq"></a> CTokenGroups:: operator =

Operator przypisania.

```
CTokenGroups& operator= (const TOKEN_GROUPS& rhs) throw(...);
CTokenGroups& operator= (const CTokenGroups& rhs) throw(...);
```

### <a name="parameters"></a>Parametry

*RHS*<br/>
`CTokenGroups`Struktura obiektu lub [TOKEN_GROUPS](/windows/win32/api/winnt/ns-winnt-token_groups) , która ma zostać przypisana do `CTokenGroups` obiektu.

### <a name="return-value"></a>Wartość zwracana

Zwraca zaktualizowany `CTokenGroups` obiekt.

## <a name="ctokengroupsoperator-const-token_groups-"></a><a name="operator_const_token_groups__star"></a> CTokenGroups:: operator const TOKEN_GROUPS *

Rzutuje wartość na wskaźnik do `TOKEN_GROUPS` struktury.

```
operator const TOKEN_GROUPS *() const throw(...);
```

### <a name="remarks"></a>Uwagi

Rzutuje wartość na wskaźnik do struktury [TOKEN_GROUPS](/windows/win32/api/winnt/ns-winnt-token_groups) .

## <a name="see-also"></a>Zobacz też

[Przykład zabezpieczeń](../../overview/visual-cpp-samples.md)<br/>
[CSid, Klasa](../../atl/reference/csid-class.md)<br/>
[Przegląd klas](../../atl/atl-class-overview.md)<br/>
[Funkcje globalne zabezpieczeń](../../atl/reference/security-global-functions.md)
