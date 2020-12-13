---
description: 'Dowiedz się więcej na temat: Klasa CDacl'
title: Klasa CDacl
ms.date: 11/04/2016
f1_keywords:
- CDacl
- ATLSECURITY/ATL::CDacl
- ATLSECURITY/ATL::CDacl::CDacl
- ATLSECURITY/ATL::CDacl::AddAllowedAce
- ATLSECURITY/ATL::CDacl::AddDeniedAce
- ATLSECURITY/ATL::CDacl::GetAceCount
- ATLSECURITY/ATL::CDacl::RemoveAce
- ATLSECURITY/ATL::CDacl::RemoveAllAces
helpviewer_keywords:
- CDacl class
ms.assetid: 2dc76616-6362-4967-b6cf-e2d39ca37ddd
ms.openlocfilehash: 0f071cbf426fe9cf89752defa19ff7f212e142d1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97142002"
---
# <a name="cdacl-class"></a>Klasa CDacl

Ta klasa jest otoką dla struktury DACL (lista arbitralnej kontroli dostępu).

> [!IMPORTANT]
> Tej klasy i jej elementów członkowskich nie można używać w aplikacjach, które są wykonywane w środowisko wykonawcze systemu Windows.

## <a name="syntax"></a>Składnia

```
class CDacl : public CAcl
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CDacl::CDacl](#cdacl)|Konstruktor.|
|[CDacl:: ~ CDacl](#dtor)|Destruktor.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CDacl::AddAllowedAce](#addallowedace)|Dodaje do obiektu dozwolony (wpis kontroli dostępu) `CDacl` .|
|[CDacl::AddDeniedAce](#adddeniedace)|Dodaje odmowę dostępu do `CDacl` obiektu.|
|[CDacl::GetAceCount](#getacecount)|Zwraca liczbę ACE (wpisów kontroli dostępu) w `CDacl` obiekcie.|
|[CDacl::RemoveAce](#removeace)|Usuwa określony element ACE (wpis kontroli dostępu) z `CDacl` obiektu.|
|[CDacl::RemoveAllAces](#removeallaces)|Usuwa wszystkie wpisy ACE zawarte w `CDacl` obiekcie.|

### <a name="public-operators"></a>Operatory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CDacl:: operator =](#operator_eq)|Operator przypisania.|

## <a name="remarks"></a>Uwagi

Deskryptor zabezpieczeń obiektu może zawierać listę DACL. Lista DACL zawiera zero lub więcej ACE (wpisy kontroli dostępu), które identyfikują użytkowników i grupy, które mogą uzyskać dostęp do obiektu. Jeśli lista DACL jest pusta (oznacza to, że nie ma żadnych ACE), dostęp nie zostanie jawnie udzielony, dlatego dostęp jest niejawnie zabroniony. Jeśli jednak deskryptor zabezpieczeń obiektu nie ma listy DACL, obiekt jest niechroniony i wszyscy mają pełny dostęp.

Aby pobrać listę DACL obiektu, musisz być właścicielem obiektu lub mieć READ_CONTROL dostęp do obiektu. Aby zmienić listę DACL obiektu, musisz mieć WRITE_DAC dostępu do obiektu.

Użyj metod klasy dostarczonych do tworzenia, dodawania, usuwania i usuwania kontroli dostępu z `CDacl` obiektu. Zobacz również [AtlGetDacl](security-global-functions.md#atlgetdacl) i [AtlSetDacl](security-global-functions.md#atlsetdacl).

Aby zapoznać się z wprowadzeniem do modelu kontroli dostępu w systemie Windows, zobacz [Access Control](/windows/win32/SecAuthZ/access-control) w Windows SDK.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[Cacls](../../atl/reference/cacl-class.md)

`CDacl`

## <a name="requirements"></a>Wymagania

**Nagłówek:** atlsecurity. h

## <a name="cdacladdallowedace"></a><a name="addallowedace"></a> CDacl::AddAllowedAce

Dodaje do obiektu dozwolony (wpis kontroli dostępu) `CDacl` .

```
bool AddAllowedAce(
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    BYTE AceFlags = 0) throw(...);

bool AddAllowedAce(
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    BYTE AceFlags,
    const GUID* pObjectType,
    const GUID* pInheritedObjectType) throw(...);
```

### <a name="parameters"></a>Parametry

*rSid*<br/>
Obiekt [CSid](../../atl/reference/csid-class.md) .

*AccessMask*<br/>
Określa maskę praw dostępu, która ma być dozwolona dla określonego `CSid` obiektu.

*AceFlags*<br/>
Zestaw flag bitowych kontrolujących dziedziczenie ACE.

*pObjectType*<br/>
Typ obiektu.

*pInheritedObjectType*<br/>
Typ dziedziczonego obiektu.

### <a name="return-value"></a>Wartość zwracana

Zwraca wartość TRUE, jeśli do obiektu zostanie dodany wpis ACE `CDacl` , wartość false w przypadku niepowodzenia.

### <a name="remarks"></a>Uwagi

`CDacl`Obiekt zawiera zero lub więcej ACE (wpisy kontroli dostępu), które identyfikują użytkowników i grupy, które mogą uzyskać dostęp do obiektu. Ta metoda dodaje wpis ACE, który umożliwia dostęp do `CDacl` obiektu.

Aby [](/windows/win32/api/winnt/ns-winnt-ace_header) uzyskać opis różnych flag, które można ustawić w parametrze, Zobacz ACE_HEADER `AceFlags` .

## <a name="cdacladddeniedace"></a><a name="adddeniedace"></a> CDacl::AddDeniedAce

Dodaje odrzucony element ACE (wpis kontroli dostępu) do `CDacl` obiektu.

```
bool AddDeniedAce(
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    BYTE AceFlags = 0) throw(...);

bool AddDeniedAce(
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    BYTE AceFlags,
    const GUID* pObjectType,
    const GUID* pInheritedObjectType) throw(...);
```

### <a name="parameters"></a>Parametry

*rSid*<br/>
Obiekt `CSid`.

*AccessMask*<br/>
Określa maskę praw dostępu, która ma zostać odrzucona dla określonego `CSid` obiektu.

*AceFlags*<br/>
Zestaw flag bitowych kontrolujących dziedziczenie ACE. Wartość domyślna to 0 w pierwszej postaci metody.

*pObjectType*<br/>
Typ obiektu.

*pInheritedObjectType*<br/>
Typ dziedziczonego obiektu.

### <a name="return-value"></a>Wartość zwracana

Zwraca wartość TRUE, jeśli do obiektu zostanie dodany wpis ACE `CDacl` , wartość false w przypadku niepowodzenia.

### <a name="remarks"></a>Uwagi

`CDacl`Obiekt zawiera zero lub więcej ACE (wpisy kontroli dostępu), które identyfikują użytkowników i grupy, które mogą uzyskać dostęp do obiektu. Ta metoda dodaje wpis ACE, który odmówi dostępu do `CDacl` obiektu.

Aby [](/windows/win32/api/winnt/ns-winnt-ace_header) uzyskać opis różnych flag, które można ustawić w parametrze, Zobacz ACE_HEADER `AceFlags` .

## <a name="cdaclcdacl"></a><a name="cdacl"></a> CDacl::CDacl

Konstruktor.

```
CDacl (const ACL& rhs) throw(...);
CDacl () throw();
```

### <a name="parameters"></a>Parametry

*RHS*<br/>
Istniejąca `ACL` Struktura (lista kontroli dostępu).

### <a name="remarks"></a>Uwagi

`CDacl`Obiekt można opcjonalnie utworzyć przy użyciu istniejącej `ACL` struktury. Należy pamiętać, że tylko lista DACL (poufnej listy kontroli dostępu), a nie SACL (lista kontroli dostępu do systemu) powinna zostać przeniesiona jako ten parametr. W przypadku kompilacji debugowania przekazanie listy SACL spowoduje wystąpienie potwierdzenia. W kompilacjach wydania przekazanie listy SACL spowoduje ignorowanie wpisów ACE (wpisy kontroli dostępu) na liście ACL i nie wystąpił żaden błąd.

## <a name="cdaclcdacl"></a><a name="dtor"></a> CDacl:: ~ CDacl

Destruktor.

```
~CDacl () throw();
```

### <a name="remarks"></a>Uwagi

Destruktor zwalnia wszystkie zasoby uzyskane przez obiekt, w tym wszystkie ACE (wpisy kontroli dostępu) za pomocą [CDacl:: RemoveAllAces](#removeallaces).

## <a name="cdaclgetacecount"></a><a name="getacecount"></a> CDacl::GetAceCount

Zwraca liczbę ACE (wpisów kontroli dostępu) w `CDacl` obiekcie.

```
UINT GetAceCount() const throw();
```

### <a name="return-value"></a>Wartość zwracana

Zwraca liczbę ACE zawartą w `CDacl` obiekcie.

## <a name="cdacloperator-"></a><a name="operator_eq"></a> CDacl:: operator =

Operator przypisania.

```
CDacl& operator= (const ACL& rhs) throw(...);
```

### <a name="parameters"></a>Parametry

*RHS*<br/>
Lista ACL (Access-Control List) do przypisania do istniejącego obiektu.

### <a name="return-value"></a>Wartość zwracana

Zwraca odwołanie do zaktualizowanego `CDacl` obiektu.

### <a name="remarks"></a>Uwagi

Należy upewnić się, że do tej funkcji jest przekazywany tylko poufny list kontroli dostępu (poufny). Przekazanie listy SACL (systemowa lista kontroli dostępu) do tej funkcji spowoduje, że zostanie potwierdzone kompilacje debugowania, ale nie spowoduje to błędu w kompilacjach wydania.

## <a name="cdaclremoveace"></a><a name="removeace"></a> CDacl::RemoveAce

Usuwa określony element ACE (wpis kontroli dostępu) z `CDacl` obiektu.

```cpp
void RemoveAce(UINT nIndex) throw();
```

### <a name="parameters"></a>Parametry

*nIndex*<br/>
Indeks wpisu ACE do usunięcia.

### <a name="remarks"></a>Uwagi

Ta metoda pochodzi z [CAtlArray:: RemoveAt](../../atl/reference/catlarray-class.md#removeat).

## <a name="cdaclremoveallaces"></a><a name="removeallaces"></a> CDacl::RemoveAllAces

Usuwa wszystkie asy (wpisy kontroli dostępu) zawarte w `CDacl` obiekcie.

```cpp
void RemoveAllAces() throw();
```

### <a name="remarks"></a>Uwagi

Usuwa każdą `ACE` (jeśli istnieje) strukturę (wpis kontroli dostępu) w `CDacl` obiekcie.

## <a name="see-also"></a>Zobacz też

[Przykład zabezpieczeń](../../overview/visual-cpp-samples.md)<br/>
[Cacls — Klasa](../../atl/reference/cacl-class.md)<br/>
[ACL](/windows/win32/SecAuthZ/access-control-lists)<br/>
[Kontrola](/windows/win32/SecAuthZ/access-control-entries)<br/>
[Przegląd klas](../../atl/atl-class-overview.md)<br/>
[Funkcje globalne zabezpieczeń](../../atl/reference/security-global-functions.md)
