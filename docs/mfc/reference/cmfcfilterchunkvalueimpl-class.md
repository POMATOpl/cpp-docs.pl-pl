---
description: 'Dowiedz się więcej na temat: Klasa CMFCFilterChunkValueImpl'
title: Klasa CMFCFilterChunkValueImpl
ms.date: 11/04/2016
f1_keywords:
- CMFCFilterChunkValueImpl
- AFXWIN/CMFCFilterChunkValueImpl
- AFXWIN/CMFCFilterChunkValueImpl::CMFCFilterChunkValueImpl
- AFXWIN/CMFCFilterChunkValueImpl::Clear
- AFXWIN/CMFCFilterChunkValueImpl::CopyChunk
- AFXWIN/CMFCFilterChunkValueImpl::CopyFrom
- AFXWIN/CMFCFilterChunkValueImpl::GetChunkGUID
- AFXWIN/CMFCFilterChunkValueImpl::GetChunkPID
- AFXWIN/CMFCFilterChunkValueImpl::GetChunkType
- AFXWIN/CMFCFilterChunkValueImpl::GetString
- AFXWIN/CMFCFilterChunkValueImpl::GetValue
- AFXWIN/CMFCFilterChunkValueImpl::GetValueNoAlloc
- AFXWIN/CMFCFilterChunkValueImpl::IsValid
- AFXWIN/CMFCFilterChunkValueImpl::SetBoolValue
- AFXWIN/CMFCFilterChunkValueImpl::SetDwordValue
- AFXWIN/CMFCFilterChunkValueImpl::SetFileTimeValue
- AFXWIN/CMFCFilterChunkValueImpl::SetInt64Value
- AFXWIN/CMFCFilterChunkValueImpl::SetIntValue
- AFXWIN/CMFCFilterChunkValueImpl::SetLongValue
- AFXWIN/CMFCFilterChunkValueImpl::SetSystemTimeValue
- AFXWIN/CMFCFilterChunkValueImpl::SetTextValue
- AFXWIN/CMFCFilterChunkValueImpl::SetChunk
helpviewer_keywords:
- CMFCFilterChunkValueImpl [MFC], CMFCFilterChunkValueImpl
- CMFCFilterChunkValueImpl [MFC], Clear
- CMFCFilterChunkValueImpl [MFC], CopyChunk
- CMFCFilterChunkValueImpl [MFC], CopyFrom
- CMFCFilterChunkValueImpl [MFC], GetChunkGUID
- CMFCFilterChunkValueImpl [MFC], GetChunkPID
- CMFCFilterChunkValueImpl [MFC], GetChunkType
- CMFCFilterChunkValueImpl [MFC], GetString
- CMFCFilterChunkValueImpl [MFC], GetValue
- CMFCFilterChunkValueImpl [MFC], GetValueNoAlloc
- CMFCFilterChunkValueImpl [MFC], IsValid
- CMFCFilterChunkValueImpl [MFC], SetBoolValue
- CMFCFilterChunkValueImpl [MFC], SetDwordValue
- CMFCFilterChunkValueImpl [MFC], SetFileTimeValue
- CMFCFilterChunkValueImpl [MFC], SetInt64Value
- CMFCFilterChunkValueImpl [MFC], SetIntValue
- CMFCFilterChunkValueImpl [MFC], SetLongValue
- CMFCFilterChunkValueImpl [MFC], SetSystemTimeValue
- CMFCFilterChunkValueImpl [MFC], SetTextValue
- CMFCFilterChunkValueImpl [MFC], SetChunk
ms.assetid: 3c833f23-5b88-4d08-9e09-ca6a8aec88bf
ms.openlocfilehash: f2db7fdf6d6d24cb906b3190d34310e1f6724194
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97265470"
---
# <a name="cmfcfilterchunkvalueimpl-class"></a>Klasa CMFCFilterChunkValueImpl

Jest to Klasa, która upraszcza logikę pary par i wartości właściwości.

## <a name="syntax"></a>Składnia

```
class CMFCFilterChunkValueImpl : public ATL::IFilterChunkValue;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CMFCFilterChunkValueImpl:: ~ CMFCFilterChunkValueImpl](#_dtorcmfcfilterchunkvalueimpl)|Destruktor obiektu.|
|[CMFCFilterChunkValueImpl::CMFCFilterChunkValueImpl](#cmfcfilterchunkvalueimpl)|Konstruuje obiekt.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CMFCFilterChunkValueImpl:: Clear](#clear)|Czyści ChunkValue.|
|[CMFCFilterChunkValueImpl:: poziomie funkcja copychunk](#copychunk)|Kopiuje ten fragment do struktury opisującej charakterystykę fragmentu.|
|[CMFCFilterChunkValueImpl::CopyFrom](#copyfrom)|Inicjuje tę wartość fragmentu z drugiej wartości.|
|[CMFCFilterChunkValueImpl::GetChunkGUID](#getchunkguid)|Pobiera identyfikator GUID fragmentu.|
|[CMFCFilterChunkValueImpl::GetChunkPID](#getchunkpid)|Pobiera identyfikator PID fragmentu (identyfikator właściwości).|
|[CMFCFilterChunkValueImpl:: getfragmenttype](#getchunktype)|Pobiera typ fragmentu.|
|[CMFCFilterChunkValueImpl:: GetString](#getstring)|Pobiera wartość ciągu.|
|[CMFCFilterChunkValueImpl:: GetValue](#getvalue)|Pobiera wartość jako przydzieloną PROPVARIANT.|
|[CMFCFilterChunkValueImpl::GetValueNoAlloc](#getvaluenoalloc)|Zwraca wartość przydzieloną (wartość wewnętrzna).|
|[CMFCFilterChunkValueImpl:: IsValid](#isvalid)|Sprawdza, czy ta wartość właściwości jest prawidłowa.|
|[CMFCFilterChunkValueImpl::SetBoolValue](#setboolvalue)|Przeciążone. Ustawia właściwość według klucza na wartość logiczną.|
|[CMFCFilterChunkValueImpl::SetDwordValue](#setdwordvalue)|Ustawia właściwość według klucza na wartość typu DWORD.|
|[CMFCFilterChunkValueImpl::SetFileTimeValue](#setfiletimevalue)|Ustawia właściwość według klucza na FILETIME.|
|[CMFCFilterChunkValueImpl::SetInt64Value](#setint64value)|Ustawia właściwość według klucza na wartość typu Int64.|
|[CMFCFilterChunkValueImpl::SetIntValue](#setintvalue)|Ustawia właściwość według klucza na int.|
|[CMFCFilterChunkValueImpl::SetLongValue](#setlongvalue)|Ustawia właściwość według klucza na wartość LONG.|
|[CMFCFilterChunkValueImpl::SetSystemTimeValue](#setsystemtimevalue)|Ustawia właściwość według klucza na SystemTime.|
|[CMFCFilterChunkValueImpl::SetTextValue](#settextvalue)|Ustawia właściwość według klucza na ciąg Unicode.|

### <a name="protected-methods"></a>Metody chronione

|Nazwa|Opis|
|----------|-----------------|
|[CMFCFilterChunkValueImpl:: setfragment](#setchunk)|Funkcja pomocnika, która ustawia wspólne właściwości fragmentu.|

## <a name="remarks"></a>Uwagi

Aby użyć, wystarczy utworzyć klasę CMFCFilterChunkValueImpl o odpowiednim rodzaju

Przykład:

Fragment CMFCFilterChunkValueImpl;

HR = fragment. SetBoolValue (PKEY_IsAttachment, prawda);

lub

HR = fragment. SetFileTimeValue (PKEY_ItemDate, ftLastModified);

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`ATL::IFilterChunkValue`

[CMFCFilterChunkValueImpl](../../mfc/reference/cmfcfilterchunkvalueimpl-class.md)

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxwin. h

## <a name="cmfcfilterchunkvalueimplclear"></a><a name="clear"></a> CMFCFilterChunkValueImpl:: Clear

Czyści ChunkValue.

```cpp
void Clear();
```

### <a name="remarks"></a>Uwagi

## <a name="cmfcfilterchunkvalueimplcmfcfilterchunkvalueimpl"></a><a name="cmfcfilterchunkvalueimpl"></a> CMFCFilterChunkValueImpl::CMFCFilterChunkValueImpl

Konstruuje obiekt.

```
CMFCFilterChunkValueImpl();
```

### <a name="remarks"></a>Uwagi

## <a name="cmfcfilterchunkvalueimplcmfcfilterchunkvalueimpl"></a><a name="_dtorcmfcfilterchunkvalueimpl"></a> CMFCFilterChunkValueImpl:: ~ CMFCFilterChunkValueImpl

Destruktor obiektu.

```
virtual ~CMFCFilterChunkValueImpl();
```

### <a name="remarks"></a>Uwagi

## <a name="cmfcfilterchunkvalueimplcopychunk"></a><a name="copychunk"></a> CMFCFilterChunkValueImpl:: poziomie funkcja copychunk

Kopiuje ten fragment do struktury opisującej charakterystykę fragmentu.

```
HRESULT CopyChunk(STAT_CHUNK* pStatChunk);
```

### <a name="parameters"></a>Parametry

*pStatChunk*<br/>
Wskaźnik do wartości docelowej opisującej charakterystykę fragmentu.

### <a name="return-value"></a>Wartość zwracana

S_OK, jeśli się to powiedzie; w przeciwnym razie kod błędu.

### <a name="remarks"></a>Uwagi

## <a name="cmfcfilterchunkvalueimplcopyfrom"></a><a name="copyfrom"></a> CMFCFilterChunkValueImpl::CopyFrom

Inicjuje tę wartość fragmentu z drugiej wartości.

```cpp
void CopyFrom (IFilterChunkValue* pValue);
```

### <a name="parameters"></a>Parametry

*pValue*<br/>
Określa wartość źródłową, z której ma zostać skopiowane.

### <a name="remarks"></a>Uwagi

## <a name="cmfcfilterchunkvalueimplgetchunkguid"></a><a name="getchunkguid"></a> CMFCFilterChunkValueImpl::GetChunkGUID

Pobiera identyfikator GUID fragmentu.

```
REFGUID GetChunkGUID() const;
```

### <a name="return-value"></a>Wartość zwracana

Odwołanie do identyfikatora GUID identyfikującego fragment.

### <a name="remarks"></a>Uwagi

## <a name="cmfcfilterchunkvalueimplgetchunkpid"></a><a name="getchunkpid"></a> CMFCFilterChunkValueImpl::GetChunkPID

Pobiera identyfikator PID fragmentu (identyfikator właściwości).

```
DWORD GetChunkPID() const;
```

### <a name="return-value"></a>Wartość zwracana

Wartość DWORD zawierająca identyfikator właściwości.

### <a name="remarks"></a>Uwagi

## <a name="cmfcfilterchunkvalueimplgetchunktype"></a><a name="getchunktype"></a> CMFCFilterChunkValueImpl:: getfragmenttype

Pobiera typ fragmentu.

```
CHUNKSTATE GetChunkType() const;
```

### <a name="return-value"></a>Wartość zwracana

Wartość wyliczana CHUNKSTATE, która określa, czy bieżący fragment jest właściwością typu text lub właściwością typu wartości.

### <a name="remarks"></a>Uwagi

## <a name="cmfcfilterchunkvalueimplgetstring"></a><a name="getstring"></a> CMFCFilterChunkValueImpl:: GetString

Pobiera wartość ciągu.

```
CString &GetString();
```

### <a name="return-value"></a>Wartość zwracana

Ciąg zawierający wartość fragmentu.

### <a name="remarks"></a>Uwagi

## <a name="cmfcfilterchunkvalueimplgetvalue"></a><a name="getvalue"></a> CMFCFilterChunkValueImpl:: GetValue

Pobiera wartość jako przydzieloną PROPVARIANT.

```
HRESULT GetValue(PROPVARIANT** ppPropVariant);
```

### <a name="parameters"></a>Parametry

*ppPropVariant*<br/>
Gdy funkcja zwraca, ten parametr zawiera wartość fragmentu.

### <a name="return-value"></a>Wartość zwracana

S_OK, jeśli PROPVARIANT został pomyślnie alokowany i wartość fragmentu została pomyślnie skopiowana do *ppPropVariant*; w przeciwnym razie kod błędu.

### <a name="remarks"></a>Uwagi

## <a name="cmfcfilterchunkvalueimplgetvaluenoalloc"></a><a name="getvaluenoalloc"></a> CMFCFilterChunkValueImpl::GetValueNoAlloc

Zwraca wartość przydzieloną (wartość wewnętrzna).

```
PROPVARIANT GetValueNoAlloc ();
```

### <a name="return-value"></a>Wartość zwracana

Zwraca bieżącą wartość fragmentu.

### <a name="remarks"></a>Uwagi

## <a name="cmfcfilterchunkvalueimplisvalid"></a><a name="isvalid"></a> CMFCFilterChunkValueImpl:: IsValid

Sprawdza, czy ta wartość właściwości jest prawidłowa.

```
BOOL IsValid() const;
```

### <a name="return-value"></a>Wartość zwracana

Ma wartość TRUE, jeśli bieżąca wartość fragmentu jest prawidłowa; w przeciwnym razie FALSE.

### <a name="remarks"></a>Uwagi

## <a name="cmfcfilterchunkvalueimplsetboolvalue"></a><a name="setboolvalue"></a> CMFCFilterChunkValueImpl::SetBoolValue

Przeciążone. Ustawia właściwość według klucza na wartość logiczną.

```
HRESULT SetBoolValue(
    REFPROPERTYKEY pkey,
    BOOL bVal,
    CHUNKSTATE chunkType = CHUNK_VALUE,
    LCID locale = 0,
    DWORD cwcLenSource = 0,
    DWORD cwcStartSource = 0,
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);

HRESULT SetBoolValue(
    REFPROPERTYKEY pkey,
    VARIANT_BOOL bVal,
    CHUNKSTATE chunkType = CHUNK_VALUE,
    LCID locale = 0,
    DWORD cwcLenSource = 0,
    DWORD cwcStartSource = 0,
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);
```

### <a name="parameters"></a>Parametry

*pkey*<br/>
Określa klucz właściwości.

*bVal*<br/>
Określa wartość fragmentu do ustawienia.

*fragment*<br/>
Flagi wskazują, czy ten fragment zawiera typ tekstowy lub właściwość typu wartości. Wartości flag są pobierane z wyliczenia CHUNKSTATE.

*locale*<br/>
Język i podjęzyk skojarzone z fragmentem tekstu. Ustawienia regionalne fragmentów są używane przez indeksatory dokumentów do wykonywania poprawnego fragmentu tekstu. Jeśli fragment nie jest typem tekstowym ani typem wartości z typem danych VT_LPWSTR, VT_LPSTR lub VT_BSTR, to pole jest ignorowane.

*cwcLenSource*<br/>
Długość (w znakach) tekstu źródłowego, z którego pochodzi bieżący fragment. Wartość zerowa oznacza dwuznakową zgodność między tekstem źródłowym a tekstem pochodnym. Wartość różna od zera oznacza, że taka korespondencja bezpośrednia nie istnieje.

*cwcStartSource*<br/>
Przesunięcie, od którego tekst źródłowy fragmentu zostanie uruchomiony w źródłowym fragmencie.

*chunkBreakType*<br/>
Typ przerwy oddzielający poprzedni fragment od bieżącego fragmentu. Wartości pochodzą z wyliczenia CHUNK_BREAKTYPE.

### <a name="return-value"></a>Wartość zwracana

S_OK, jeśli się to powiedzie; w przeciwnym razie kod błędu.

### <a name="remarks"></a>Uwagi

## <a name="cmfcfilterchunkvalueimplsetchunk"></a><a name="setchunk"></a> CMFCFilterChunkValueImpl:: setfragment

Funkcja pomocnika, która ustawia wspólne właściwości fragmentu.

```
HRESULT SetChunk(
    REFPROPERTYKEY pkey,
    CHUNKSTATE chunkType=CHUNK_VALUE,
    LCID locale=0,
    DWORD cwcLenSource=0,
    DWORD cwcStartSource=0,
    CHUNK_BREAKTYPE chunkBreakType=CHUNK_NO_BREAK);
```

### <a name="parameters"></a>Parametry

*pkey*<br/>
Określa klucz właściwości.

*fragment*<br/>
Flagi wskazują, czy ten fragment zawiera typ tekstowy lub właściwość typu wartości. Wartości flag są pobierane z wyliczenia CHUNKSTATE.

*locale*<br/>
Język i podjęzyk skojarzone z fragmentem tekstu. Ustawienia regionalne fragmentów są używane przez indeksatory dokumentów do wykonywania poprawnego fragmentu tekstu. Jeśli fragment nie jest typem tekstowym ani typem wartości z typem danych VT_LPWSTR, VT_LPSTR lub VT_BSTR, to pole jest ignorowane.

*cwcLenSource*<br/>
Długość (w znakach) tekstu źródłowego, z którego pochodzi bieżący fragment. Wartość zerowa oznacza dwuznakową zgodność między tekstem źródłowym a tekstem pochodnym. Wartość różna od zera oznacza, że taka korespondencja bezpośrednia nie istnieje.

*cwcStartSource*<br/>
Przesunięcie, od którego tekst źródłowy fragmentu zostanie uruchomiony w źródłowym fragmencie.

*chunkBreakType*<br/>
Typ przerwy oddzielający poprzedni fragment od bieżącego fragmentu. Wartości pochodzą z wyliczenia CHUNK_BREAKTYPE.

### <a name="return-value"></a>Wartość zwracana

S_OK, jeśli się to powiedzie; w przeciwnym razie kod błędu.

### <a name="remarks"></a>Uwagi

## <a name="cmfcfilterchunkvalueimplsetdwordvalue"></a><a name="setdwordvalue"></a> CMFCFilterChunkValueImpl::SetDwordValue

Ustaw właściwość według klucza na wartość typu DWORD.

```
HRESULT SetDwordValue(
    REFPROPERTYKEY pkey,
    DWORD dwVal,
    CHUNKSTATE chunkType = CHUNK_VALUE,
    LCID locale = 0,
    DWORD cwcLenSource = 0,
    DWORD cwcStartSource = 0,
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);
```

### <a name="parameters"></a>Parametry

*pkey*<br/>
Określa klucz właściwości.

*dwVal*<br/>
Określa wartość fragmentu do ustawienia.

*fragment*<br/>
Flagi wskazują, czy ten fragment zawiera typ tekstowy lub właściwość typu wartości. Wartości flag są pobierane z wyliczenia CHUNKSTATE.

*locale*<br/>
Język i podjęzyk skojarzone z fragmentem tekstu. Ustawienia regionalne fragmentów są używane przez indeksatory dokumentów do wykonywania poprawnego fragmentu tekstu. Jeśli fragment nie jest typem tekstowym ani typem wartości z typem danych VT_LPWSTR, VT_LPSTR lub VT_BSTR, to pole jest ignorowane.

*cwcLenSource*<br/>
Długość (w znakach) tekstu źródłowego, z którego pochodzi bieżący fragment. Wartość zerowa oznacza dwuznakową zgodność między tekstem źródłowym a tekstem pochodnym. Wartość różna od zera oznacza, że taka korespondencja bezpośrednia nie istnieje.

*cwcStartSource*<br/>
Przesunięcie, od którego tekst źródłowy fragmentu zostanie uruchomiony w źródłowym fragmencie.

*chunkBreakType*<br/>
Typ przerwy oddzielający poprzedni fragment od bieżącego fragmentu. Wartości pochodzą z wyliczenia CHUNK_BREAKTYPE.

### <a name="return-value"></a>Wartość zwracana

S_OK, jeśli się to powiedzie; w przeciwnym razie kod błędu.

### <a name="remarks"></a>Uwagi

## <a name="cmfcfilterchunkvalueimplsetfiletimevalue"></a><a name="setfiletimevalue"></a> CMFCFilterChunkValueImpl::SetFileTimeValue

Ustaw właściwość według klucza na FILETIME.

```
HRESULT SetFileTimeValue(
    REFPROPERTYKEY pkey,
    FILETIME dtVal,
    CHUNKSTATE chunkType = CHUNK_VALUE,
    LCID locale = 0,
    DWORD cwcLenSource = 0,
    DWORD cwcStartSource = 0,
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);
```

### <a name="parameters"></a>Parametry

*pkey*<br/>
Określa klucz właściwości.

*dtVal*<br/>
Określa wartość fragmentu do ustawienia.

*fragment*<br/>
Flagi wskazują, czy ten fragment zawiera typ tekstowy lub właściwość typu wartości. Wartości flag są pobierane z wyliczenia CHUNKSTATE.

*locale*<br/>
Język i podjęzyk skojarzone z fragmentem tekstu. Ustawienia regionalne fragmentów są używane przez indeksatory dokumentów do wykonywania poprawnego fragmentu tekstu. Jeśli fragment nie jest typem tekstowym ani typem wartości z typem danych VT_LPWSTR, VT_LPSTR lub VT_BSTR, to pole jest ignorowane.

*cwcLenSource*<br/>
Długość (w znakach) tekstu źródłowego, z którego pochodzi bieżący fragment. Wartość zerowa oznacza dwuznakową zgodność między tekstem źródłowym a tekstem pochodnym. Wartość różna od zera oznacza, że taka korespondencja bezpośrednia nie istnieje.

*cwcStartSource*<br/>
Przesunięcie, od którego tekst źródłowy fragmentu zostanie uruchomiony w źródłowym fragmencie.

*chunkBreakType*<br/>
Typ przerwy oddzielający poprzedni fragment od bieżącego fragmentu. Wartości pochodzą z wyliczenia CHUNK_BREAKTYPE.

### <a name="return-value"></a>Wartość zwracana

S_OK, jeśli się to powiedzie; w przeciwnym razie kod błędu.

### <a name="remarks"></a>Uwagi

## <a name="cmfcfilterchunkvalueimplsetint64value"></a><a name="setint64value"></a> CMFCFilterChunkValueImpl::SetInt64Value

Ustaw właściwość według klucza na wartość typu Int64.

```
HRESULT SetInt64Value(
    REFPROPERTYKEY pkey,
    __int64 nVal,
    CHUNKSTATE chunkType = CHUNK_VALUE,
    LCID locale = 0,
    DWORD cwcLenSource = 0,
    DWORD cwcStartSource = 0,
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);
```

### <a name="parameters"></a>Parametry

*pkey*<br/>
Określa klucz właściwości.

*nVal*<br/>
Określa wartość fragmentu do ustawienia.

*fragment*<br/>
Flagi wskazują, czy ten fragment zawiera typ tekstowy lub właściwość typu wartości. Wartości flag są pobierane z wyliczenia CHUNKSTATE.

*locale*<br/>
Język i podjęzyk skojarzone z fragmentem tekstu. Ustawienia regionalne fragmentów są używane przez indeksatory dokumentów do wykonywania poprawnego fragmentu tekstu. Jeśli fragment nie jest typem tekstowym ani typem wartości z typem danych VT_LPWSTR, VT_LPSTR lub VT_BSTR, to pole jest ignorowane.

*cwcLenSource*<br/>
Długość (w znakach) tekstu źródłowego, z którego pochodzi bieżący fragment. Wartość zerowa oznacza dwuznakową zgodność między tekstem źródłowym a tekstem pochodnym. Wartość różna od zera oznacza, że taka korespondencja bezpośrednia nie istnieje.

*cwcStartSource*<br/>
Przesunięcie, od którego tekst źródłowy fragmentu zostanie uruchomiony w źródłowym fragmencie.

*chunkBreakType*<br/>
Typ przerwy oddzielający poprzedni fragment od bieżącego fragmentu. Wartości pochodzą z wyliczenia CHUNK_BREAKTYPE.

### <a name="return-value"></a>Wartość zwracana

S_OK, jeśli się to powiedzie; w przeciwnym razie kod błędu.

### <a name="remarks"></a>Uwagi

## <a name="cmfcfilterchunkvalueimplsetintvalue"></a><a name="setintvalue"></a> CMFCFilterChunkValueImpl::SetIntValue

Ustaw właściwość według klucza na int.

```
HRESULT SetIntValue(
    REFPROPERTYKEY pkey,
    int nVal,
    CHUNKSTATE chunkType = CHUNK_VALUE,
    LCID locale = 0,
    DWORD cwcLenSource = 0,
    DWORD cwcStartSource = 0,
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);
```

### <a name="parameters"></a>Parametry

*pkey*<br/>
Określa klucz właściwości.

*nVal*<br/>
Określa wartość fragmentu do ustawienia.

*fragment*<br/>
Flagi wskazują, czy ten fragment zawiera typ tekstowy lub właściwość typu wartości. Wartości flag są pobierane z wyliczenia CHUNKSTATE.

*locale*<br/>
Język i podjęzyk skojarzone z fragmentem tekstu. Ustawienia regionalne fragmentów są używane przez indeksatory dokumentów do wykonywania poprawnego fragmentu tekstu. Jeśli fragment nie jest typem tekstowym ani typem wartości z typem danych VT_LPWSTR, VT_LPSTR lub VT_BSTR, to pole jest ignorowane.

*cwcLenSource*<br/>
Długość (w znakach) tekstu źródłowego, z którego pochodzi bieżący fragment. Wartość zerowa oznacza dwuznakową zgodność między tekstem źródłowym a tekstem pochodnym. Wartość różna od zera oznacza, że taka korespondencja bezpośrednia nie istnieje.

*cwcStartSource*<br/>
Przesunięcie, od którego tekst źródłowy fragmentu zostanie uruchomiony w źródłowym fragmencie.

*chunkBreakType*<br/>
Typ przerwy oddzielający poprzedni fragment od bieżącego fragmentu. Wartości pochodzą z wyliczenia CHUNK_BREAKTYPE.

### <a name="return-value"></a>Wartość zwracana

S_OK, jeśli się to powiedzie; w przeciwnym razie kod błędu.

### <a name="remarks"></a>Uwagi

## <a name="cmfcfilterchunkvalueimplsetlongvalue"></a><a name="setlongvalue"></a> CMFCFilterChunkValueImpl::SetLongValue

Ustaw właściwość według klucza na wartość LONG.

```
HRESULT SetLongValue(
    REFPROPERTYKEY pkey,
    long lVal,
    CHUNKSTATE chunkType = CHUNK_VALUE,
    LCID locale = 0,
    DWORD cwcLenSource = 0,
    DWORD cwcStartSource = 0,
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);
```

### <a name="parameters"></a>Parametry

*pkey*<br/>
Określa klucz właściwości.

*lVal*<br/>
Określa wartość fragmentu do ustawienia.

*fragment*<br/>
Flagi wskazują, czy ten fragment zawiera typ tekstowy lub właściwość typu wartości. Wartości flag są pobierane z wyliczenia CHUNKSTATE.

*locale*<br/>
Język i podjęzyk skojarzone z fragmentem tekstu. Ustawienia regionalne fragmentów są używane przez indeksatory dokumentów do wykonywania poprawnego fragmentu tekstu. Jeśli fragment nie jest typem tekstowym ani typem wartości z typem danych VT_LPWSTR, VT_LPSTR lub VT_BSTR, to pole jest ignorowane.

*cwcLenSource*<br/>
Długość (w znakach) tekstu źródłowego, z którego pochodzi bieżący fragment. Wartość zerowa oznacza dwuznakową zgodność między tekstem źródłowym a tekstem pochodnym. Wartość różna od zera oznacza, że taka korespondencja bezpośrednia nie istnieje.

*cwcStartSource*<br/>
Przesunięcie, od którego tekst źródłowy fragmentu zostanie uruchomiony w źródłowym fragmencie.

*chunkBreakType*<br/>
Typ przerwy oddzielający poprzedni fragment od bieżącego fragmentu. Wartości pochodzą z wyliczenia CHUNK_BREAKTYPE.

### <a name="return-value"></a>Wartość zwracana

S_OK, jeśli się to powiedzie; w przeciwnym razie kod błędu.

### <a name="remarks"></a>Uwagi

## <a name="cmfcfilterchunkvalueimplsetsystemtimevalue"></a><a name="setsystemtimevalue"></a> CMFCFilterChunkValueImpl::SetSystemTimeValue

Ustawia właściwość według klucza na SystemTime.

```
HRESULT SetSystemTimeValue(
    REFPROPERTYKEY pkey,
    const SYSTEMTIME& systemTime,
    CHUNKSTATE chunkType = CHUNK_VALUE,
    LCID locale=0,
    DWORD cwcLenSource=0,
    DWORD cwcStartSource=0,
    CHUNK_BREAKTYPE chunkBreakType=CHUNK_NO_BREAK);
```

### <a name="parameters"></a>Parametry

*pkey*<br/>
Określa klucz właściwości.

*systemTime*<br/>
Określa wartość fragmentu do ustawienia.

*fragment*<br/>
Flagi wskazują, czy ten fragment zawiera typ tekstowy lub właściwość typu wartości. Wartości flag są pobierane z wyliczenia CHUNKSTATE.

*locale*<br/>
Język i podjęzyk skojarzone z fragmentem tekstu. Ustawienia regionalne fragmentów są używane przez indeksatory dokumentów do wykonywania poprawnego fragmentu tekstu. Jeśli fragment nie jest typem tekstowym ani typem wartości z typem danych VT_LPWSTR, VT_LPSTR lub VT_BSTR, to pole jest ignorowane.

*cwcLenSource*<br/>
Długość (w znakach) tekstu źródłowego, z którego pochodzi bieżący fragment. Wartość zerowa oznacza dwuznakową zgodność między tekstem źródłowym a tekstem pochodnym. Wartość różna od zera oznacza, że taka korespondencja bezpośrednia nie istnieje.

*cwcStartSource*<br/>
Przesunięcie, od którego tekst źródłowy fragmentu zostanie uruchomiony w źródłowym fragmencie.

*chunkBreakType*<br/>
Typ przerwy oddzielający poprzedni fragment od bieżącego fragmentu. Wartości pochodzą z wyliczenia CHUNK_BREAKTYPE.

### <a name="return-value"></a>Wartość zwracana

S_OK, jeśli się to powiedzie; w przeciwnym razie kod błędu.

### <a name="remarks"></a>Uwagi

## <a name="cmfcfilterchunkvalueimplsettextvalue"></a><a name="settextvalue"></a> CMFCFilterChunkValueImpl::SetTextValue

Ustawia właściwość według klucza na ciąg Unicode.

```
HRESULT SetTextValue(
    REFPROPERTYKEY pkey,
    LPCTSTR pszValue,
    CHUNKSTATE chunkType = CHUNK_VALUE,
    LCID locale = 0,
    DWORD cwcLenSource = 0,
    DWORD cwcStartSource = 0,
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);
```

### <a name="parameters"></a>Parametry

*pkey*<br/>
Określa klucz właściwości.

*pszValue*<br/>
Określa wartość fragmentu do ustawienia.

*fragment*<br/>
Flagi wskazują, czy ten fragment zawiera typ tekstowy lub właściwość typu wartości. Wartości flag są pobierane z wyliczenia CHUNKSTATE.

*locale*<br/>
Język i podjęzyk skojarzone z fragmentem tekstu. Ustawienia regionalne fragmentów są używane przez indeksatory dokumentów do wykonywania poprawnego fragmentu tekstu. Jeśli fragment nie jest typem tekstowym ani typem wartości z typem danych VT_LPWSTR, VT_LPSTR lub VT_BSTR, to pole jest ignorowane.

*cwcLenSource*<br/>
Długość (w znakach) tekstu źródłowego, z którego pochodzi bieżący fragment. Wartość zerowa oznacza dwuznakową zgodność między tekstem źródłowym a tekstem pochodnym. Wartość różna od zera oznacza, że taka korespondencja bezpośrednia nie istnieje.

*cwcStartSource*<br/>
Przesunięcie, od którego tekst źródłowy fragmentu zostanie uruchomiony w źródłowym fragmencie.

*chunkBreakType*<br/>
Typ przerwy oddzielający poprzedni fragment od bieżącego fragmentu. Wartości pochodzą z wyliczenia CHUNK_BREAKTYPE.

### <a name="return-value"></a>Wartość zwracana

S_OK, jeśli się to powiedzie; w przeciwnym razie kod błędu.

### <a name="remarks"></a>Uwagi

## <a name="see-also"></a>Zobacz też

[Klasy](../../mfc/reference/mfc-classes.md)
