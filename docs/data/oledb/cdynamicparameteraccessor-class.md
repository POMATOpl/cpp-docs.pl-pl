---
description: 'Dowiedz się więcej na temat: Klasa CDynamicParameterAccessor'
title: CDynamicParameterAccessor — Klasa
ms.date: 02/14/2018
f1_keywords:
- ATL.CDynamicParameterAccessor
- ATL::CDynamicParameterAccessor
- CDynamicParameterAccessor
- CDynamicParameterAccessor::CDynamicParameterAccessor
- CDynamicParameterAccessor.CDynamicParameterAccessor
- CDynamicParameterAccessor::GetParam
- ATL.CDynamicParameterAccessor.GetParam
- CDynamicParameterAccessor::GetParam<ctype>
- CDynamicParameterAccessor.GetParam
- GetParam
- ATL::CDynamicParameterAccessor::GetParam<ctype>
- ATL::CDynamicParameterAccessor::GetParam
- ATL::CDynamicParameterAccessor::GetParamCount
- CDynamicParameterAccessor::GetParamCount
- CDynamicParameterAccessor.GetParamCount
- GetParamCount
- ATL.CDynamicParameterAccessor.GetParamCount
- GetParamIO
- CDynamicParameterAccessor::GetParamIO
- ATL.CDynamicParameterAccessor.GetParamIO
- CDynamicParameterAccessor.GetParamIO
- ATL::CDynamicParameterAccessor::GetParamIO
- ATL::CDynamicParameterAccessor::GetParamLength
- ATL.CDynamicParameterAccessor.GetParamLength
- CDynamicParameterAccessor.GetParamLength
- CDynamicParameterAccessor::GetParamLength
- GetParamLength
- CDynamicParameterAccessor::GetParamName
- ATL.CDynamicParameterAccessor.GetParamName
- GetParamName
- CDynamicParameterAccessor.GetParamName
- ATL::CDynamicParameterAccessor::GetParamName
- CDynamicParameterAccessor::GetParamStatus
- CDynamicParameterAccessor.GetParamStatus
- ATL.CDynamicParameterAccessor.GetParamStatus
- ATL::CDynamicParameterAccessor::GetParamStatus
- GetParamStatus
- CDynamicParameterAccessor.GetParamString
- GetParamString
- CDynamicParameterAccessor::GetParamString
- ATL.CDynamicParameterAccessor.GetParamString
- ATL::CDynamicParameterAccessor::GetParamString
- CDynamicParameterAccessor.GetParamType
- CDynamicParameterAccessor:GetParamType
- CDynamicParameterAccessor::GetParamType
- ATL.CDynamicParameterAccessor.GetParamType
- GetParamType
- ATL::CDynamicParameterAccessor::GetParamType
- ATL::CDynamicParameterAccessor::SetParam
- ATL::CDynamicParameterAccessor::SetParam<ctype>
- CDynamicParameterAccessor.SetParam
- ATL.CDynamicParameterAccessor.SetParam
- SetParam
- CDynamicParameterAccessor:SetParam
- CDynamicParameterAccessor::SetParam<ctype>
- CDynamicParameterAccessor::SetParam
- ATL::CDynamicParameterAccessor::SetParamLength
- CDynamicParameterAccessor.SetParamLength
- ATL.CDynamicParameterAccessor.SetParamLength
- CDynamicParameterAccessor::SetParamLength
- SetParamLength
- CDynamicParameterAccessor::SetParamStatus
- ATL.CDynamicParameterAccessor.SetParamStatus
- ATL::CDynamicParameterAccessor::SetParamStatus
- CDynamicParameterAccessor.SetParamStatus
- SetParamStatus
- ATL.CDynamicParameterAccessor.SetParamString
- ATL::CDynamicParameterAccessor::SetParamString
- SetParamString
- CDynamicParameterAccessor::SetParamString
- CDynamicParameterAccessor.SetParamString
helpviewer_keywords:
- CDynamicParameterAccessor class
- CDynamicParameterAccessor class, constructor
- CDynamicParameterAccessor method
- GetParam method
- GetParamCount method
- GetParamIO method
- GetParamLength method
- GetParamName method
- GetParamStatus method
- GetParamString method
- GetParamType method
- SetParam method
- SetParamLength method
- SetParamStatus method
- SetParamString method
ms.assetid: 5f22626e-e80d-491f-8b3b-cedc50331960
ms.openlocfilehash: 5470ced8b4479124f0db3878fe2562a658547f9f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97170779"
---
# <a name="cdynamicparameteraccessor-class"></a>CDynamicParameterAccessor — Klasa

Podobnie jak w przypadku [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) , ale uzyskuje informacje o parametrach, które mają być ustawiane przez wywołanie interfejsu [ICommandWithParameters](/sql/relational-databases/native-client-ole-db-interfaces/icommandwithparameters) .

## <a name="syntax"></a>Składnia

```cpp
class CDynamicParameterAccessor : public CDynamicAccessor
```

## <a name="requirements"></a>Wymagania

**Nagłówek**: atldbcli. h

## <a name="members"></a>Elementy członkowskie

### <a name="methods"></a>Metody

| Nazwa | Opis |
|-|-|
|[CDynamicParameterAccessor](#cdynamicparameteraccessor)|Konstruktor.|
|[GetParam](#getparam)|Pobiera dane parametrów z bufora.|
|[GetParamCount](#getparamcount)|Pobiera liczbę parametrów w metodzie dostępu.|
|[GetParamIO](#getparamio)|Określa, czy określony parametr jest parametrem wejściowym, czy wyjściowym.|
|[GetParamLength](#getparamlength)|Pobiera długość określonego parametru przechowywanego w buforze.|
|[Getparamname](#getparamname)|Pobiera nazwę określonego parametru.|
|[GetParamStatus](#getparamstatus)|Pobiera stan określonego parametru przechowywanego w buforze.|
|[GetParamString](#getparamstring)|Pobiera dane ciągu określonego parametru przechowywane w buforze.|
|[GetParamType](#getparamtype)|Pobiera typ danych określonego parametru.|
|[SetParam](#setparam)|Ustawia bufor przy użyciu danych parametrów.|
|[SetParamLength](#setparamlength)|Ustawia długość określonego parametru przechowywanego w buforze.|
|[SetParamStatus](#setparamstatus)|Ustawia stan określonego parametru przechowywanego w buforze.|
|[SetParamString](#setparamstring)|Ustawia dane ciągu określonego parametru przechowywanego w buforze.|

## <a name="remarks"></a>Uwagi

Dostawca musi obsługiwać `ICommandWithParameters` użycie tej klasy przez konsumenta.

Informacje o parametrach są przechowywane w buforze utworzonym i zarządzanym przez tę klasę. Uzyskiwanie danych parametrów z buforu przy użyciu elementu [GetParam](#getparam) i [GetParamType](#getparamtype).

Aby zapoznać się z przykładem pokazującym, jak używać tej klasy do wykonywania SQL Server procedury składowanej i uzyskiwania wartości parametrów wyjściowych, zobacz przykładowy kod [DynamicConsumer](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/OLEDB/Consumer/DynamicConsumer) w repozytorium [Microsoft VCSamples](https://github.com/Microsoft/VCSamples) w witrynie GitHub.

## <a name="cdynamicparameteraccessorcdynamicparameteraccessor"></a><a name="cdynamicparameteraccessor"></a> CDynamicParameterAccessor:: CDynamicParameterAccessor

Konstruktor.

### <a name="syntax"></a>Składnia

```cpp
typedef CDynamicParameterAccessor _ParamClass;
CDynamicParameterAccessor(
   DBBLOBHANDLINGENUM eBlobHandling = DBBLOBHANDLING_DEFAULT,
   DBLENGTH nBlobSize = 8000 )
   : CDynamicAccessor(eBlobHandling, nBlobSize )
```

#### <a name="parameters"></a>Parametry

*eBlobHandling*<br/>
Określa, w jaki sposób dane obiektów BLOB mają być obsługiwane. Wartość domyślna to DBBLOBHANDLING_DEFAULT. Aby uzyskać opis wartości DBBLOBHANDLINGENUM, zobacz [CDynamicAccessor:: SetBlobHandling](./cdynamicaccessor-class.md#setblobhandling) .

*nBlobSize*<br/>
Maksymalny rozmiar obiektu BLOB w bajtach; dane kolumny za tą wartością są traktowane jako obiekty BLOB. Wartość domyślna to 8 000. Aby uzyskać szczegółowe informacje, zobacz [CDynamicAccessor:: SetBlobSizeLimit](./cdynamicaccessor-class.md#setblobsizelimit) .

### <a name="remarks"></a>Uwagi

Aby uzyskać więcej informacji na temat obsługi obiektów BLOB, zobacz Konstruktor [CDynamicAccessor:: CDynamicAccessor](./cdynamicaccessor-class.md#cdynamicaccessor) .

## <a name="cdynamicparameteraccessorgetparam"></a><a name="getparam"></a> CDynamicParameterAccessor:: GetParam

Pobiera dane nieciągu dla określonego parametru z buforu parametrów.

### <a name="syntax"></a>Składnia

```cpp
template <class ctype>bool GetParam(DBORDINAL nParam,
   ctype* pData) const throw();

template <class ctype> bool GetParam(TCHAR* pParamName,
   ctype* pData) const throw();

void* GetParam(DBORDINAL nParam) const throw();

void* GetParam(TCHAR* pParamName) const throw();
```

#### <a name="parameters"></a>Parametry

*CType*<br/>
Parametr z szablonem, który jest typem danych.

*nParam*<br/>
podczas Numer parametru (przesunięcie od 1). Parametr 0 jest zarezerwowany dla wartości zwracanych. Numer parametru jest indeksem parametru na podstawie jego kolejności w wywołaniu procedury SQL lub procedura składowana. Na przykład zobacz [SetParam](#setparam) .

*pParamName*<br/>
podczas Nazwa parametru.

*pData*<br/>
określoną Wskaźnik do pamięci zawierającej dane pobrane z bufora.

### <a name="return-value"></a>Wartość zwracana

W przypadku wersji nieszablonowych wskazuje pamięć zawierającą dane pobrane z bufora. W przypadku wersji z szablonem zwraca wartość **`true`** po powodzeniu lub **`false`** w przypadku niepowodzenia.

Służy `GetParam` do pobierania danych parametrów niebędących ciągami z bufora. Użyj [GetParamString](#getparamstring) , aby pobrać dane parametrów ciągu z buforu.

## <a name="cdynamicparameteraccessorgetparamcount"></a><a name="getparamcount"></a> CDynamicParameterAccessor:: GetParamCount

Pobiera liczbę parametrów przechowywanych w buforze.

### <a name="syntax"></a>Składnia

```cpp
DB_UPARAMS GetParamCount() const throw();
```

### <a name="return-value"></a>Wartość zwracana

Liczba parametrów.

## <a name="cdynamicparameteraccessorgetparamio"></a><a name="getparamio"></a> CDynamicParameterAccessor:: GetParamIO

Określa, czy określony parametr jest parametrem wejściowym, czy wyjściowym.

### <a name="syntax"></a>Składnia

```cpp
bool GetParamIO(DBORDINAL nParam,
   DBPARAMIO* pParamIO) const throw();
```

#### <a name="parameters"></a>Parametry

*nParam*<br/>
podczas Numer parametru (przesunięcie od 1). Parametr 0 jest zarezerwowany dla wartości zwracanych. Numer parametru jest indeksem parametru na podstawie jego kolejności w wywołaniu procedury SQL lub procedura składowana. Na przykład zobacz [SetParam](#setparam) .

*pParamIO*<br/>
Wskaźnik do zmiennej zawierającej `DBPARAMIO` Typ (dane wejściowe lub wyjściowe) określonego parametru. Jest on definiowany w następujący sposób:

```cpp
typedef DWORD DBPARAMIO;

enum DBPARAMIOENUM {
    DBPARAMIO_NOTPARAM   = 0,
    DBPARAMIO_INPUT      = 0x1,
    DBPARAMIO_OUTPUT     = 0x2
};
```

### <a name="return-value"></a>Wartość zwracana

Zwraca **`true`** po powodzeniu lub **`false`** w przypadku niepowodzenia.

## <a name="cdynamicparameteraccessorgetparamlength"></a><a name="getparamlength"></a> CDynamicParameterAccessor:: GetParamLength

Pobiera długość określonego parametru przechowywanego w buforze.

### <a name="syntax"></a>Składnia

```cpp
bool GetParamLength(DBORDINAL nParam,
   DBLENGTH* pLength);

DBLENGTH* GetParamLength(DBORDINAL nParam) const throw();
```

#### <a name="parameters"></a>Parametry

*nParam*<br/>
podczas Numer parametru (przesunięcie od 1). Parametr 0 jest zarezerwowany dla wartości zwracanych. Numer parametru jest indeksem parametru na podstawie jego kolejności w wywołaniu procedury SQL lub procedura składowana. Na przykład zobacz [SetParam](#setparam) .

*pLength*<br/>
określoną Wskaźnik do zmiennej zawierającej długość w bajtach określonego parametru.

### <a name="remarks"></a>Uwagi

Pierwsze zastąpienie zwraca wartość **`true`** na powodzenie lub **`false`** w przypadku niepowodzenia. Drugie przesłonięcie wskazuje na pamięć zawierającą długość parametru.

## <a name="cdynamicparameteraccessorgetparamname"></a><a name="getparamname"></a> CDynamicParameterAccessor:: getparamname

Pobiera nazwę określonego parametru.

### <a name="syntax"></a>Składnia

```cpp
LPOLESTR GetParamName(DBORDINAL nParam) const throw();
```

#### <a name="parameters"></a>Parametry

*nParam*<br/>
podczas Numer parametru (przesunięcie od 1). Parametr 0 jest zarezerwowany dla wartości zwracanych. Numer parametru jest indeksem parametru na podstawie jego kolejności w wywołaniu procedury SQL lub procedura składowana. Na przykład zobacz [SetParam](#setparam) .

### <a name="return-value"></a>Wartość zwracana

Nazwa określonego parametru.

## <a name="cdynamicparameteraccessorgetparamstatus"></a><a name="getparamstatus"></a> CDynamicParameterAccessor:: GetParamStatus

Pobiera stan określonego parametru przechowywanego w buforze.

### <a name="syntax"></a>Składnia

```cpp
bool GetParamStatus(DBORDINAL nParam,
   DBSTATUS* pStatus);

DBSTATUS* GetParamStatus(DBORDINAL nParam) const throw();
```

#### <a name="parameters"></a>Parametry

*nParam*<br/>
podczas Numer parametru (przesunięcie od 1). Parametr 0 jest zarezerwowany dla wartości zwracanych. Numer parametru jest indeksem parametru na podstawie jego kolejności w wywołaniu procedury SQL lub procedura składowana. Na przykład zobacz [SetParam](#setparam) .

*pStatus*<br/>
określoną Wskaźnik do zmiennej zawierającej stan DBSTATUS określonego parametru. Aby uzyskać informacje na temat wartości DBSTATUS, zobacz [status](/previous-versions/windows/desktop/ms722617(v=vs.85)) w *dokumentacji programisty OLE DB* lub Wyszukaj stan DBW OLEDB. h.

### <a name="remarks"></a>Uwagi

Pierwsze zastąpienie zwraca wartość **`true`** na powodzenie lub **`false`** w przypadku niepowodzenia. Drugie zastąpienie wskazuje pamięć zawierającą stan określonego parametru.

## <a name="cdynamicparameteraccessorgetparamstring"></a><a name="getparamstring"></a> CDynamicParameterAccessor:: GetParamString

Pobiera dane ciągu określonego parametru przechowywane w buforze.

### <a name="syntax"></a>Składnia

```cpp
bool GetParamString(DBORDINAL nParam,
   CSimpleStringA& strOutput) throw();

bool GetParamString(DBORDINAL nParam,
   CSimpleStringW& strOutput) throw();

bool GetParamString(DBORDINAL nParam,
   CHAR* pBuffer,
   size_t* pMaxLen) throw();

bool GetParamString(DBORDINAL nParam,
   WCHAR* pBuffer,
   size_t* pMaxLen) throw();
```

#### <a name="parameters"></a>Parametry

*nParam*<br/>
podczas Numer parametru (przesunięcie od 1). Parametr 0 jest zarezerwowany dla wartości zwracanych. Numer parametru jest indeksem parametru na podstawie jego kolejności w wywołaniu procedury SQL lub procedura składowana. Na przykład zobacz [SetParam](#setparam) .

*strOutput*<br/>
określoną `CSimpleStringA`Dane ciągu ANSI () lub Unicode ( `CSimpleStringW` ) określonego parametru. Należy przekazać parametr typu `CString` , na przykład:

[!code-cpp[NVC_OLEDB_Consumer#9](../../data/oledb/codesnippet/cpp/cdynamicparameteraccessor-getparamstring_1.cpp)]

*pBuffer*<br/>
określoną Wskaźnik do danych ciągu ANSI (**char**) lub Unicode (**WCHAR**) określonego parametru.

*pMaxLen*<br/>
określoną Wskaźnik do rozmiaru buforu wskazywanego przez *pBuffer* (w znakach, łącznie z kończącą się wartością null).

### <a name="remarks"></a>Uwagi

Zwraca **`true`** po powodzeniu lub **`false`** w przypadku niepowodzenia.

Jeśli *pBuffer* ma wartość null, ta metoda ustawi wymagany rozmiar buforu w pamięci wskazywanej przez *pMaxLen* i zwraca **`true`** bez kopiowania danych.

Ta metoda zakończy się niepowodzeniem, jeśli bufor *pBuffer* nie jest wystarczająco duży, aby można było zawierać cały ciąg.

Służy `GetParamString` do pobierania danych parametrów ciągu z buforu. Użyj [GetParam](#getparam) do pobrania danych parametrów niebędących ciągami z bufora.

## <a name="cdynamicparameteraccessorgetparamtype"></a><a name="getparamtype"></a> CDynamicParameterAccessor:: GetParamType

Pobiera typ danych określonego parametru.

### <a name="syntax"></a>Składnia

```cpp
bool GetParamType(DBORDINAL nParam,
   DBTYPE* pType) const throw();
```

#### <a name="parameters"></a>Parametry

*nParam*<br/>
podczas Numer parametru (przesunięcie od 1). Parametr 0 jest zarezerwowany dla wartości zwracanych. Numer parametru jest indeksem parametru na podstawie jego kolejności w wywołaniu procedury SQL lub procedura składowana. Na przykład zobacz [SetParam](#setparam) .

*pType*<br/>
określoną Wskaźnik do zmiennej zawierającej typ danych określonego parametru.

### <a name="return-value"></a>Wartość zwracana

Zwraca **`true`** po powodzeniu lub **`false`** w przypadku niepowodzenia.

## <a name="cdynamicparameteraccessorsetparam"></a><a name="setparam"></a> CDynamicParameterAccessor:: setParam

Ustawia bufor parametrów przy użyciu określonych danych (niebędących ciągami).

### <a name="syntax"></a>Składnia

```cpp
template <class ctype>
bool SetParam(DBORDINAL nParam,
   constctype* pData,
   DBSTATUS status = DBSTATUS_S_OK) throw();

template <class ctype>
bool SetParam(TCHAR* pParamName,
   const ctype* pData,
   DBSTATUS status = DBSTATUS_S_OK) throw();
```

#### <a name="parameters"></a>Parametry

*CType*<br/>
Parametr z szablonem, który jest typem danych.

*nParam*<br/>
podczas Numer parametru (przesunięcie od 1). Parametr 0 jest zarezerwowany dla wartości zwracanych. Numer parametru jest indeksem parametru na podstawie jego kolejności w wywołaniu procedury SQL lub procedura składowana. Na przykład:

[!code-cpp[NVC_OLEDB_Consumer#8](../../data/oledb/codesnippet/cpp/cdynamicparameteraccessor-setparam_1.cpp)]

*pParamName*<br/>
podczas Nazwa parametru.

*pData*<br/>
podczas Wskaźnik do pamięci zawierającej dane, które mają być zapisywane w buforze.

*Stany*<br/>
podczas Stan kolumny DBSTATUS. Aby uzyskać informacje na temat wartości DBSTATUS, zobacz [status](/previous-versions/windows/desktop/ms722617(v=vs.85)) w *dokumentacji programisty OLE DB* lub Wyszukaj stan DBW OLEDB. h.

### <a name="return-value"></a>Wartość zwracana

Zwraca **`true`** po powodzeniu lub **`false`** w przypadku niepowodzenia.

Służy `SetParam` do ustawiania danych parametrów niebędących ciągami w buforze. Użyj [SetParamString](#setparamstring) , aby ustawić dane parametrów ciągu w buforze.

## <a name="cdynamicparameteraccessorsetparamlength"></a><a name="setparamlength"></a> CDynamicParameterAccessor:: SetParamLength

Ustawia długość określonego parametru przechowywanego w buforze.

### <a name="syntax"></a>Składnia

```cpp
bool SetParamLength(DBORDINAL nParam,
   DBLENGTH length);
```

#### <a name="parameters"></a>Parametry

*nParam*<br/>
podczas Numer parametru (przesunięcie od 1). Parametr 0 jest zarezerwowany dla wartości zwracanych. Numer parametru jest indeksem parametru na podstawie jego kolejności w wywołaniu procedury SQL lub procedura składowana. Na przykład zobacz [SetParam](#setparam) .

*length*<br/>
podczas Długość w bajtach określonego parametru.

### <a name="remarks"></a>Uwagi

Zwraca **`true`** po powodzeniu lub **`false`** w przypadku niepowodzenia.

## <a name="cdynamicparameteraccessorsetparamstatus"></a><a name="setparamstatus"></a> CDynamicParameterAccessor:: SetParamStatus

Ustawia stan określonego parametru przechowywanego w buforze.

### <a name="syntax"></a>Składnia

```cpp
bool SetParamStatus(DBORDINAL nParam,
   DBSTATUS status);
```

#### <a name="parameters"></a>Parametry

*nParam*<br/>
podczas Numer parametru (przesunięcie od 1). Parametr 0 jest zarezerwowany dla wartości zwracanych. Numer parametru jest indeksem parametru na podstawie jego kolejności w wywołaniu procedury SQL lub procedura składowana. Na przykład zobacz [SetParam](#setparam) .

*Stany*<br/>
podczas Stan DBSTATUS określonego parametru. Aby uzyskać informacje na temat wartości DBSTATUS, zobacz [status](/previous-versions/windows/desktop/ms722617(v=vs.85)) w *dokumentacji programisty OLE DB* lub Wyszukaj stan DBW OLEDB. h.

### <a name="remarks"></a>Uwagi

Zwraca **`true`** po powodzeniu lub **`false`** w przypadku niepowodzenia.

## <a name="cdynamicparameteraccessorsetparamstring"></a><a name="setparamstring"></a> CDynamicParameterAccessor:: SetParamString

Ustawia dane ciągu określonego parametru przechowywanego w buforze.

### <a name="syntax"></a>Składnia

```cpp
bool SetParamString(DBORDINAL nParam,
   constCHAR* pString,
   DBSTATUS status = DBSTATUS_S_OK) throw();bool SetParamString(DBORDINAL nParam,
   constWCHAR* pString,
   DBSTATUS status = DBSTATUS_S_OK) throw();
```

#### <a name="parameters"></a>Parametry

*nParam*<br/>
podczas Numer parametru (przesunięcie od 1). Parametr 0 jest zarezerwowany dla wartości zwracanych. Numer parametru jest indeksem parametru na podstawie jego kolejności w wywołaniu procedury SQL lub procedura składowana. Na przykład zobacz [SetParam](#setparam) .

*pString*<br/>
podczas Wskaźnik do danych ciągu ANSI (**char**) lub Unicode (**WCHAR**) określonego parametru. Zobacz DBSTATUS w OLEDB. h.

*Stany*<br/>
podczas Stan DBSTATUS określonego parametru. Aby uzyskać informacje na temat wartości DBSTATUS, zobacz [status](/previous-versions/windows/desktop/ms722617(v=vs.85)) w *dokumentacji programisty OLE DB* lub Wyszukaj stan DBW OLEDB. h.

### <a name="remarks"></a>Uwagi

Zwraca **`true`** po powodzeniu lub **`false`** w przypadku niepowodzenia.

`SetParamString` zakończy się niepowodzeniem, jeśli spróbujesz ustawić ciąg, który jest większy niż maksymalny rozmiar określony dla *pString*.

Służy `SetParamString` do ustawiania danych parametrów ciągu w buforze. Użyj [SetParam](#setparam) , aby ustawić dane parametrów niebędących ciągami w buforze.

## <a name="see-also"></a>Zobacz też

[OLE DB Szablony konsumentów](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[Dokumentacja szablonów klientów OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)<br/>
[Klasa CAccessor](../../data/oledb/caccessor-class.md)<br/>
[Klasa CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md)<br/>
[Klasa CManualAccessor](../../data/oledb/cmanualaccessor-class.md)
