---
description: 'Dowiedz się więcej na temat: Klasa COleSafeArray'
title: Klasa COleSafeArray
ms.date: 08/29/2019
f1_keywords:
- COleSafeArray
- AFXDISP/COleSafeArray
- AFXDISP/COleSafeArray::COleSafeArray
- AFXDISP/COleSafeArray::AccessData
- AFXDISP/COleSafeArray::AllocData
- AFXDISP/COleSafeArray::AllocDescriptor
- AFXDISP/COleSafeArray::Attach
- AFXDISP/COleSafeArray::Clear
- AFXDISP/COleSafeArray::Copy
- AFXDISP/COleSafeArray::Create
- AFXDISP/COleSafeArray::CreateOneDim
- AFXDISP/COleSafeArray::Destroy
- AFXDISP/COleSafeArray::DestroyData
- AFXDISP/COleSafeArray::DestroyDescriptor
- AFXDISP/COleSafeArray::Detach
- AFXDISP/COleSafeArray::GetByteArray
- AFXDISP/COleSafeArray::GetDim
- AFXDISP/COleSafeArray::GetElement
- AFXDISP/COleSafeArray::GetElemSize
- AFXDISP/COleSafeArray::GetLBound
- AFXDISP/COleSafeArray::GetOneDimSize
- AFXDISP/COleSafeArray::GetUBound
- AFXDISP/COleSafeArray::Lock
- AFXDISP/COleSafeArray::PtrOfIndex
- AFXDISP/COleSafeArray::PutElement
- AFXDISP/COleSafeArray::Redim
- AFXDISP/COleSafeArray::ResizeOneDim
- AFXDISP/COleSafeArray::UnaccessData
- AFXDISP/COleSafeArray::Unlock
helpviewer_keywords:
- COleSafeArray [MFC], COleSafeArray
- COleSafeArray [MFC], AccessData
- COleSafeArray [MFC], AllocData
- COleSafeArray [MFC], AllocDescriptor
- COleSafeArray [MFC], Attach
- COleSafeArray [MFC], Clear
- COleSafeArray [MFC], Copy
- COleSafeArray [MFC], Create
- COleSafeArray [MFC], CreateOneDim
- COleSafeArray [MFC], Destroy
- COleSafeArray [MFC], DestroyData
- COleSafeArray [MFC], DestroyDescriptor
- COleSafeArray [MFC], Detach
- COleSafeArray [MFC], GetByteArray
- COleSafeArray [MFC], GetDim
- COleSafeArray [MFC], GetElement
- COleSafeArray [MFC], GetElemSize
- COleSafeArray [MFC], GetLBound
- COleSafeArray [MFC], GetOneDimSize
- COleSafeArray [MFC], GetUBound
- COleSafeArray [MFC], Lock
- COleSafeArray [MFC], PtrOfIndex
- COleSafeArray [MFC], PutElement
- COleSafeArray [MFC], Redim
- COleSafeArray [MFC], ResizeOneDim
- COleSafeArray [MFC], UnaccessData
- COleSafeArray [MFC], Unlock
ms.assetid: f45a5224-5f48-40ec-9ddd-287ef9740150
ms.openlocfilehash: 6c33f58f71167c492883a25b05fce6bb8fb09916
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97226704"
---
# <a name="colesafearray-class"></a>Klasa COleSafeArray

Klasa do pracy z tablicami dowolnego typu i wymiaru.

## <a name="syntax"></a>Składnia

```
class COleSafeArray : public tagVARIANT
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[COleSafeArray::COleSafeArray](#colesafearray)|Konstruuje `COleSafeArray` obiekt.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[COleSafeArray::AccessData](#accessdata)|Pobiera wskaźnik do danych macierzy.|
|[COleSafeArray::AllocData](#allocdata)|Przydziela pamięć dla tablicy.|
|[COleSafeArray::AllocDescriptor](#allocdescriptor)|Przydziela pamięć dla deskryptora bezpiecznego tablicy.|
|[COleSafeArray:: Attach](#attach)|Daje kontrolę nad istniejącą `VARIANT` tablicą dla `COleSafeArray` obiektu.|
|[COleSafeArray:: Clear](#clear)|Zwalnia wszystkie dane z bazowego `VARIANT` .|
|[COleSafeArray:: Copy](#copy)|Tworzy kopię istniejącej tablicy.|
|[COleSafeArray:: Create](#create)|Tworzy bezpieczną tablicę.|
|[COleSafeArray::CreateOneDim](#createonedim)|Tworzy jednowymiarowy `COleSafeArray` obiekt.|
|[COleSafeArray::D Estroy](#destroy)|Niszczy istniejącą tablicę.|
|[COleSafeArray::D estroyData](#destroydata)|Niszczy dane w bezpiecznej macierzy.|
|[COleSafeArray::D estroyDescriptor](#destroydescriptor)|Niszczy deskryptor bezpiecznej tablicy.|
|[COleSafeArray::D etach](#detach)|Odłącza tablicę wariantów od `COleSafeArray` obiektu (w taki sposób, że dane nie zostaną zwolnione).|
|[COleSafeArray:: getbytearray](#getbytearray)|Kopiuje zawartość bezpiecznej tablicy do [CByteArray](../../mfc/reference/cbytearray-class.md).|
|[COleSafeArray::GetDim](#getdim)|Zwraca liczbę wymiarów w tablicy.|
|[COleSafeArray:: GetElement](#getelement)|Pobiera pojedynczy element bezpiecznej tablicy.|
|[COleSafeArray::GetElemSize](#getelemsize)|Zwraca rozmiar (w bajtach) jednego elementu w bezpiecznej tablicy.|
|[COleSafeArray::GetLBound](#getlbound)|Zwraca dolną granicę dla dowolnego wymiaru bezpiecznej tablicy.|
|[COleSafeArray::GetOneDimSize](#getonedimsize)|Zwraca liczbę elementów w jednowymiarowym `COleSafeArray` obiekcie.|
|[COleSafeArray::GetUBound](#getubound)|Zwraca górną granicę dla dowolnego wymiaru bezpiecznej tablicy.|
|[COleSafeArray:: Lock](#lock)|Zwiększa liczbę blokad tablicy i umieszcza wskaźnik do danych tablicy w deskryptorze tablicy.|
|[COleSafeArray::P trOfIndex](#ptrofindex)|Zwraca wskaźnik do indeksowanego elementu.|
|[COleSafeArray::P utElement](#putelement)|Przypisuje pojedynczy element do tablicy.|
|[COleSafeArray:: ReDim](#redim)|Zmienia najmniejszą znaczącą (po prawej stronie) powiązaną bezpieczną tablicę.|
|[COleSafeArray::ResizeOneDim](#resizeonedim)|Zmienia liczbę elementów w jednowymiarowym `COleSafeArray` obiekcie.|
|[COleSafeArray::UnaccessData](#unaccessdata)|Zmniejsza liczbę blokad tablicy i unieważnia wskaźnik pobrany przez `AccessData` .|
|[COleSafeArray:: Unlock](#unlock)|Zmniejsza liczbę blokad tablicy, aby można ją było zwolnić lub zmienić jej rozmiar.|

### <a name="public-operators"></a>Operatory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[COleSafeArray:: operator LPCVARIANT](#operator_lpcvariant)|Uzyskuje dostęp do bazowej `VARIANT` struktury `COleSafeArray` obiektu.|
|[COleSafeArray:: operator LPVARIANT](#operator_lpvariant)|Uzyskuje dostęp do bazowej `VARIANT` struktury `COleSafeArray` obiektu.|
|[COleSafeArray:: operator =](#operator_eq)|Kopiuje wartości do `COleSafeArray` obiektu ( `SAFEARRAY` ,, `VARIANT` , `COleVariant` lub `COleSafeArray` tablicy).|
|[COleSafeArray:: operator = =](#operator_eq_eq)|Porównuje dwie tablice wariantów ( `SAFEARRAY` , `VARIANT` , `COleVariant` lub `COleSafeArray` tablice).|
|[COleSafeArray:: operator &lt;&lt;](#operator_lt_lt)|Wyprowadza zawartość `COleSafeArray` obiektu do kontekstu zrzutu.|

## <a name="remarks"></a>Uwagi

`COleSafeArray` pochodzi ze struktury OLE `VARIANT` . `SAFEARRAY`Funkcje składowe OLE są dostępne za pośrednictwem `COleSafeArray` , a także zestaw funkcji składowych przeznaczonych specjalnie dla jednowymiarowych tablic bajtów.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`tagVARIANT`

`COleSafeArray`

## <a name="requirements"></a>Wymagania

**Nagłówek:** AFXDISP. h

## <a name="colesafearrayaccessdata"></a><a name="accessdata"></a> COleSafeArray::AccessData

Pobiera wskaźnik do danych macierzy.

```cpp
void AccessData(void** ppvData);
```

### <a name="parameters"></a>Parametry

*ppvData*<br/>
Wskaźnik do wskaźnika do danych macierzy.

### <a name="remarks"></a>Uwagi

W przypadku błędu funkcja zgłasza element [CMemoryException](../../mfc/reference/cmemoryexception-class.md) lub [COleException](../../mfc/reference/coleexception-class.md).

### <a name="example"></a>Przykład

[!code-cpp[NVC_MFCOleContainer#26](../../mfc/codesnippet/cpp/colesafearray-class_1.cpp)]

## <a name="colesafearrayallocdata"></a><a name="allocdata"></a> COleSafeArray::AllocData

Przydziela pamięć dla bezpiecznej tablicy.

```cpp
void AllocData();
```

### <a name="remarks"></a>Uwagi

W przypadku błędu funkcja zgłasza element [CMemoryException](../../mfc/reference/cmemoryexception-class.md) lub [COleException](../../mfc/reference/coleexception-class.md).

## <a name="colesafearrayallocdescriptor"></a><a name="allocdescriptor"></a> COleSafeArray::AllocDescriptor

Przydziela pamięć dla deskryptora bezpiecznej tablicy.

```cpp
void AllocDescriptor(DWORD dwDims);
```

### <a name="parameters"></a>Parametry

*dwDims*<br/>
Liczba wymiarów w bezpiecznej tablicy.

### <a name="remarks"></a>Uwagi

W przypadku błędu funkcja zgłasza element [CMemoryException](../../mfc/reference/cmemoryexception-class.md) lub [COleException](../../mfc/reference/coleexception-class.md).

## <a name="colesafearrayattach"></a><a name="attach"></a> COleSafeArray:: Attach

Zapewnia kontrolę nad danymi w istniejącej `VARIANT` tablicy do `COleSafeArray` obiektu.

```cpp
void Attach(VARIANT& varSrc);
```

### <a name="parameters"></a>Parametry

*varSrc*<br/>
Obiekt `VARIANT`. Parametr *varSrc* musi mieć [VT_ARRAY](/windows/win32/api/wtypes/ne-wtypes-varenum)VARTYPE.

### <a name="remarks"></a>Uwagi

Typ źródła `VARIANT` jest ustawiony na VT_EMPTY. Ta funkcja czyści bieżące dane tablicowe, jeśli istnieją.

### <a name="example"></a>Przykład

  Zobacz przykład dla [COleSafeArray:: AccessData](#accessdata).

## <a name="colesafearrayclear"></a><a name="clear"></a> COleSafeArray:: Clear

Czyści bezpieczną tablicę.

```cpp
void Clear();
```

### <a name="remarks"></a>Uwagi

Funkcja czyści tablicę bezpieczną przez ustawienie `VARTYPE` obiektu do VT_EMPTY. Bieżąca zawartość jest zwalniana, a tablica jest zwalniana.

## <a name="colesafearraycolesafearray"></a><a name="colesafearray"></a> COleSafeArray::COleSafeArray

Konstruuje `COleSafeArray` obiekt.

```
COleSafeArray();

COleSafeArray(
    const SAFEARRAY& saSrc,
    VARTYPE vtSrc);

COleSafeArray(
    LPCSAFEARRAY pSrc,
    VARTYPE vtSrc);

COleSafeArray(const COleSafeArray& saSrc);
COleSafeArray(const VARIANT& varSrc);
COleSafeArray(LPCVARIANT pSrc);
COleSafeArray(const COleVariant& varSrc);
```

### <a name="parameters"></a>Parametry

*saSrc*<br/>
Istniejący `COleSafeArray` obiekt lub `SAFEARRAY` do skopiowania do nowego `COleSafeArray` obiektu.

*vtSrc*<br/>
Typ VARTYPE nowego `COleSafeArray` obiektu.

*psaSrc*<br/>
Wskaźnik do, `SAFEARRAY` który ma zostać skopiowany do nowego `COleSafeArray` obiektu.

*varSrc*<br/>
Istniejący `VARIANT` obiekt lub, `COleVariant` który ma zostać skopiowany do nowego `COleSafeArray` obiektu.

*pSrc*<br/>
Wskaźnik do `VARIANT` obiektu, który ma zostać skopiowany do nowego `COleSafeArray` obiektu.

### <a name="remarks"></a>Uwagi

Wszystkie te konstruktory tworzą nowe `COleSafeArray` obiekty. Jeśli nie ma parametru, `COleSafeArray` zostanie utworzony pusty obiekt (VT_EMPTY). Jeśli `COleSafeArray` jest kopiowana z innej tablicy, której element VARTYPE jest znany niejawnie (a `COleSafeArray` , `COleVariant` lub `VARIANT` ), VARTYPE tablicy źródłowej jest zachowywana i nie musi być określony. Jeśli `COleSafeArray` jest kopiowana z innej tablicy, której VARTYPE nie jest znany ( `SAFEARRAY` ), parametr VARTYPE musi być określony w *vtSrc* parametru.

W przypadku błędu funkcja zgłasza element [CMemoryException](../../mfc/reference/cmemoryexception-class.md) lub [COleException](../../mfc/reference/coleexception-class.md).

## <a name="colesafearraycopy"></a><a name="copy"></a> COleSafeArray:: Copy

Tworzy kopię istniejącej bezpiecznej tablicy.

```cpp
void Copy(LPSAFEARRAY* ppsa);
```

### <a name="parameters"></a>Parametry

*ppsa*<br/>
Wskaźnik do lokalizacji, w której ma zostać zwrócony nowy deskryptor tablicy.

### <a name="remarks"></a>Uwagi

W przypadku błędu funkcja zgłasza element [CMemoryException](../../mfc/reference/cmemoryexception-class.md) lub [COleException](../../mfc/reference/coleexception-class.md).

## <a name="colesafearraycreate"></a><a name="create"></a> COleSafeArray:: Create

Przydziela i inicjuje dane dla tablicy.

```cpp
void Create(
    VARTYPE vtSrc,
    DWORD dwDims,
    DWORD* rgElements);

void Create(
    VARTYPE vtSrc,
    DWORD dwDims,
    SAFEARRAYBOUND* rgsabounds);
```

### <a name="parameters"></a>Parametry

*vtSrc*<br/>
Typ podstawowy tablicy (czyli element VARTYPE dla każdego elementu tablicy). Element VARTYPE jest ograniczony do podzbioru typów wariantów. Nie można ustawić VT_ARRAY ani flagi VT_BYREF. VT_EMPTY i VT_NULL nie są prawidłowymi typami podstawowymi dla tablicy. Wszystkie inne typy są prawne.

*dwDims*<br/>
Liczba wymiarów w tablicy. Można to zmienić po utworzeniu tablicy przy użyciu [ReDim](#redim).

*rgElements*<br/>
Wskaźnik do tablicy o liczbie elementów dla każdego wymiaru w tablicy.

*rgsabounds*<br/>
Wskaźnik do wektora granic (jeden dla każdego wymiaru) do przydzielenia tablicy.

### <a name="remarks"></a>Uwagi

Ta funkcja wyczyści bieżące dane tablicowe w razie potrzeby. W przypadku błędu funkcja zgłasza [CMemoryException](../../mfc/reference/cmemoryexception-class.md).

### <a name="example"></a>Przykład

[!code-cpp[NVC_MFCOleContainer#27](../../mfc/codesnippet/cpp/colesafearray-class_2.cpp)]

## <a name="colesafearraycreateonedim"></a><a name="createonedim"></a> COleSafeArray::CreateOneDim

Tworzy nowy jednowymiarowy `COleSafeArray` obiekt.

```cpp
void CreateOneDim(
    VARTYPE vtSrc,
    DWORD dwElements,
    const void* pvSrcData = NULL,
    long nLBound = 0);
```

### <a name="parameters"></a>Parametry

*vtSrc*<br/>
Typ podstawowy tablicy (czyli element VARTYPE dla każdego elementu tablicy).

*dwElements*<br/>
Liczba elementów w tablicy. Można to zmienić po utworzeniu tablicy przy użyciu [ResizeOneDim](#resizeonedim).

*pvSrcData*<br/>
Wskaźnik na dane, które mają zostać skopiowane do tablicy.

*nLBound*<br/>
Dolna granica tablicy.

### <a name="remarks"></a>Uwagi

Funkcja przydziela i inicjuje dane dla tablicy, kopiując określone dane, jeśli wskaźnik *pvSrcData* nie ma wartości null.

W przypadku błędu funkcja zgłasza [CMemoryException](../../mfc/reference/cmemoryexception-class.md).

### <a name="example"></a>Przykład

[!code-cpp[NVC_MFCOleContainer#28](../../mfc/codesnippet/cpp/colesafearray-class_3.cpp)]

## <a name="colesafearraydestroy"></a><a name="destroy"></a> COleSafeArray::D Estroy

Niszczy istniejący deskryptor tablicy i wszystkie dane w tablicy.

```cpp
void Destroy();
```

### <a name="remarks"></a>Uwagi

Jeśli obiekty są przechowywane w tablicy, każdy obiekt jest wydawany. W przypadku błędu funkcja zgłasza element [CMemoryException](../../mfc/reference/cmemoryexception-class.md) lub [COleException](../../mfc/reference/coleexception-class.md).

## <a name="colesafearraydestroydata"></a><a name="destroydata"></a> COleSafeArray::D estroyData

Niszczy wszystkie dane w bezpiecznej macierzy.

```cpp
void DestroyData();
```

### <a name="remarks"></a>Uwagi

Jeśli obiekty są przechowywane w tablicy, każdy obiekt jest wydawany. W przypadku błędu funkcja zgłasza element [CMemoryException](../../mfc/reference/cmemoryexception-class.md) lub [COleException](../../mfc/reference/coleexception-class.md).

## <a name="colesafearraydestroydescriptor"></a><a name="destroydescriptor"></a> COleSafeArray::D estroyDescriptor

Niszczy deskryptor bezpiecznej tablicy.

```cpp
void DestroyDescriptor();
```

### <a name="remarks"></a>Uwagi

W przypadku błędu funkcja zgłasza element [CMemoryException](../../mfc/reference/cmemoryexception-class.md) lub [COleException](../../mfc/reference/coleexception-class.md).

## <a name="colesafearraydetach"></a><a name="detach"></a> COleSafeArray::D etach

Odłącza `VARIANT` dane od `COleSafeArray` obiektu.

```
VARIANT Detach();
```

### <a name="return-value"></a>Wartość zwracana

Wartość bazowa `VARIANT` w `COleSafeArray` obiekcie.

### <a name="remarks"></a>Uwagi

Funkcja odłącza dane w bezpiecznej tablicy przez ustawienie VARTYPE obiektu do VT_EMPTY. Jest on odpowiedzialny za zwolnienie tablicy przez wywołanie funkcji systemu Windows [VariantClear](/windows/win32/api/oleauto/nf-oleauto-variantclear).

W przypadku błędu funkcja zgłasza [COleException](../../mfc/reference/coleexception-class.md).

### <a name="example"></a>Przykład

  Zobacz przykład dla [COleSafeArray::P utelement](#putelement).

## <a name="colesafearraygetbytearray"></a><a name="getbytearray"></a> COleSafeArray:: getbytearray

Kopiuje zawartość tablicy bezpiecznej do programu `CByteArray` .

```cpp
void GetByteArray(CByteArray& bytes);
```

### <a name="parameters"></a>Parametry

*szybkość*<br/>
Odwołanie do obiektu [CByteArray](../../mfc/reference/cbytearray-class.md) .

## <a name="colesafearraygetdim"></a><a name="getdim"></a> COleSafeArray::GetDim

Zwraca liczbę wymiarów w `COleSafeArray` obiekcie.

```
DWORD GetDim();
```

### <a name="return-value"></a>Wartość zwracana

Liczba wymiarów w bezpiecznej tablicy.

### <a name="example"></a>Przykład

[!code-cpp[NVC_MFCOleContainer#27](../../mfc/codesnippet/cpp/colesafearray-class_2.cpp)]

## <a name="colesafearraygetelement"></a><a name="getelement"></a> COleSafeArray:: GetElement

Pobiera pojedynczy element bezpiecznej tablicy.

```cpp
void GetElement(
    long* rgIndices,
    void* pvData);
```

### <a name="parameters"></a>Parametry

*rgIndices*<br/>
Wskaźnik do tablicy indeksów dla każdego wymiaru tablicy.

*pvData*<br/>
Wskaźnik do lokalizacji, w której ma zostać umieszczony element tablicy.

### <a name="remarks"></a>Uwagi

Ta funkcja automatycznie wywołuje funkcje systemu Windows `SafeArrayLock` i `SafeArrayUnlock` przed pobraniem elementu i po nim. Jeśli element danych jest ciągiem, obiektem lub wariantem, funkcja kopiuje element w prawidłowy sposób. Parametr *pvData* powinien wskazywać na wystarczająco duży bufor, aby zawierał element.

W przypadku błędu funkcja zgłasza element [CMemoryException](../../mfc/reference/cmemoryexception-class.md) lub [COleException](../../mfc/reference/coleexception-class.md).

### <a name="example"></a>Przykład

[!code-cpp[NVC_MFCOleContainer#29](../../mfc/codesnippet/cpp/colesafearray-class_4.cpp)]

## <a name="colesafearraygetelemsize"></a><a name="getelemsize"></a> COleSafeArray::GetElemSize

Pobiera rozmiar elementu w `COleSafeArray` obiekcie.

```
DWORD GetElemSize();
```

### <a name="return-value"></a>Wartość zwracana

Rozmiar, w bajtach, elementów tablicy bezpiecznej.

## <a name="colesafearraygetlbound"></a><a name="getlbound"></a> COleSafeArray::GetLBound

Zwraca dolną granicę dla dowolnego wymiaru `COleSafeArray` obiektu.

```cpp
void GetLBound(
    DWORD dwDim,
    long* pLBound);
```

### <a name="parameters"></a>Parametry

*dwDim*<br/>
Wymiar tablicy, dla którego należy uzyskać dolną granicę.

*pLBound*<br/>
Wskaźnik do lokalizacji, w której ma zostać zwrócona Dolna granica.

### <a name="remarks"></a>Uwagi

W przypadku błędu funkcja zgłasza [COleException](../../mfc/reference/coleexception-class.md).

### <a name="example"></a>Przykład

[!code-cpp[NVC_MFCOleContainer#30](../../mfc/codesnippet/cpp/colesafearray-class_5.cpp)]

## <a name="colesafearraygetonedimsize"></a><a name="getonedimsize"></a> COleSafeArray::GetOneDimSize

Zwraca liczbę elementów w jednowymiarowym `COleSafeArray` obiekcie.

```
DWORD GetOneDimSize();
```

### <a name="return-value"></a>Wartość zwracana

Liczba elementów w tablicy jednowymiarowej.

### <a name="example"></a>Przykład

  Zobacz przykład dla [COleSafeArray:: CreateOneDim](#createonedim).

## <a name="colesafearraygetubound"></a><a name="getubound"></a> COleSafeArray::GetUBound

Zwraca górną granicę dla dowolnego wymiaru bezpiecznej tablicy.

```cpp
void GetUBound(
    DWORD dwDim,
    long* pUBound);
```

### <a name="parameters"></a>Parametry

*dwDim*<br/>
Wymiar tablicy, dla którego należy uzyskać górną granicę.

*pUBound*<br/>
Wskaźnik do lokalizacji, aby przywrócić górną granicę.

### <a name="remarks"></a>Uwagi

W przypadku błędu funkcja zgłasza [COleException](../../mfc/reference/coleexception-class.md).

### <a name="example"></a>Przykład

[!code-cpp[NVC_MFCOleContainer#31](../../mfc/codesnippet/cpp/colesafearray-class_6.cpp)]

## <a name="colesafearraylock"></a><a name="lock"></a> COleSafeArray:: Lock

Zwiększa liczbę blokad tablicy i umieszcza wskaźnik do danych tablicy w deskryptorze tablicy.

```cpp
void Lock();
```

### <a name="remarks"></a>Uwagi

W przypadku błędu zgłasza [COleException](../../mfc/reference/coleexception-class.md).

Wskaźnik w deskryptorze tablicy jest prawidłowy do momentu `Unlock` wywołania. Wywołania `Lock` można zagnieżdżać; wymagana jest równa Liczba wywołań `Unlock` .

Nie można usunąć tablicy, gdy jest ona zablokowana.

## <a name="colesafearrayoperator-lpcvariant"></a><a name="operator_lpcvariant"></a> COleSafeArray:: operator LPCVARIANT

Wywołaj ten operator rzutowania, aby uzyskać dostęp do źródłowej `VARIANT` struktury tego `COleSafeArray` obiektu.

```
operator LPCVARIANT() const;
```

## <a name="colesafearrayoperator-lpvariant"></a><a name="operator_lpvariant"></a> COleSafeArray:: operator LPVARIANT

Wywołaj ten operator rzutowania, aby uzyskać dostęp do źródłowej `VARIANT` struktury tego `COleSafeArray` obiektu.

```
operator LPVARIANT();
```

### <a name="remarks"></a>Uwagi

Należy zauważyć, że zmiana wartości w `VARIANT` strukturze, do której uzyskuje dostęp wskaźnik zwracany przez tę funkcję, spowoduje zmianę wartości tego `COleSafeArray` obiektu.

## <a name="colesafearrayoperator-"></a><a name="operator_eq"></a> COleSafeArray:: operator =

Te przeciążone operatory przypisania kopiują wartość źródłową do tego `COleSafeArray` obiektu.

```
COleSafeArray& operator=(const COleSafeArray& saSrc);
COleSafeArray& operator=(const VARIANT& varSrc);
COleSafeArray& operator=(LPCVARIANT pSrc);
COleSafeArray& operator=(const COleVariant& varSrc);
```

### <a name="remarks"></a>Uwagi

Poniżej znajduje się krótki opis każdego z następujących operatorów:

- **operator = (** *saSrc* **)** Kopiuje istniejący `COleSafeArray` obiekt do tego obiektu.

- **operator = (** *varSrc* **)** Kopiuje istniejący `VARIANT` lub `COleVariant` tablicę do tego obiektu.

- **operator = (** *pSrc* **)** Kopiuje `VARIANT` obiekt Array, do którego uzyskuje dostęp *pSrc* do tego obiektu.

## <a name="colesafearrayoperator-"></a><a name="operator_eq_eq"></a> COleSafeArray:: operator = =

Ten operator porównuje dwie tablice ( `SAFEARRAY` , `VARIANT` ,, `COleVariant` lub `COleSafeArray` tablice) i zwraca wartość różną od zera, jeśli są równe; w przeciwnym razie 0.

```
BOOL operator==(const SAFEARRAY& saSrc) const;  BOOL operator==(LPCSAFEARRAY pSrc) const;

BOOL operator==(const COleSafeArray& saSrc) const;  BOOL operator==(const VARIANT& varSrc) const;

BOOL operator==(LPCVARIANT pSrc) const;  BOOL operator==(const COleVariant& varSrc) const;
```

### <a name="remarks"></a>Uwagi

Dwie tablice są równe, jeśli mają taką samą liczbę wymiarów, równy rozmiar w każdym wymiarze i równe wartości elementów.

## <a name="colesafearrayoperator-ltlt"></a><a name="operator_lt_lt"></a> COleSafeArray:: operator &lt;&lt;

`COleSafeArray`Operator wstawiania (<<) obsługuje zrzucanie diagnostyczne i przechowywanie `COleSafeArray` obiektu w archiwum.

```
CDumpContext& AFXAPI operator<<(
    CDumpContext& dc,
    COleSafeArray& saSrc);
```

## <a name="colesafearrayptrofindex"></a><a name="ptrofindex"></a> COleSafeArray::P trOfIndex

Zwraca wskaźnik do elementu określonego przez wartości indeksu.

```cpp
void PtrOfIndex(
    long* rgIndices,
    void** ppvData);
```

### <a name="parameters"></a>Parametry

*rgIndices*<br/>
Tablica wartości indeksu, które identyfikują element tablicy. Należy określić wszystkie indeksy dla elementu.

*ppvData*<br/>
Zwraca wskaźnik do elementu identyfikowanego przez wartości w *rgIndices*.

## <a name="colesafearrayputelement"></a><a name="putelement"></a> COleSafeArray::P utElement

Przypisuje pojedynczy element do tablicy.

```cpp
void PutElement(
    long* rgIndices,
    void* pvData);
```

### <a name="parameters"></a>Parametry

*rgIndices*<br/>
Wskaźnik do tablicy indeksów dla każdego wymiaru tablicy.

*pvData*<br/>
Wskaźnik na dane, które mają zostać przypisane do tablicy. VT_DISPATCH, VT_UNKNOWN i VT_BSTR typy wariantów są wskaźnikami i nie wymagają innego poziomu pośredniego.

### <a name="remarks"></a>Uwagi

Ta funkcja automatycznie wywołuje funkcje systemu Windows [SafeArrayLock](/windows/win32/api/oleauto/nf-oleauto-safearraylock) i [SafeArrayUnlock](/windows/win32/api/oleauto/nf-oleauto-safearrayunlock) przed przypisaniem elementu i po nim. Jeśli element danych jest ciągiem, obiektem lub wariantem, funkcja kopiuje ją poprawnie, a jeśli istniejący element jest ciągiem, obiektem lub wariantem, zostanie wyczyszczony poprawnie.

Należy pamiętać, że można mieć wiele blokad w tablicy, aby można było umieścić elementy w tablicy, gdy tablica jest zablokowana przez inne operacje.

W przypadku błędu funkcja zgłasza element [CMemoryException](../../mfc/reference/cmemoryexception-class.md) lub [COleException](../../mfc/reference/coleexception-class.md).

### <a name="example"></a>Przykład

[!code-cpp[NVC_MFCOleContainer#32](../../mfc/codesnippet/cpp/colesafearray-class_7.cpp)]

## <a name="colesafearrayredim"></a><a name="redim"></a> COleSafeArray:: ReDim

Zmienia najmniejszą znaczącą (po prawej stronie) powiązaną bezpieczną tablicę.

```cpp
void Redim(SAFEARRAYBOUND* psaboundNew);
```

### <a name="parameters"></a>Parametry

*psaboundNew*<br/>
Wskaźnik do nowej struktury powiązanej z bezpieczną tablicą zawierającą nową powiązaną tablicę. Można zmienić tylko najmniej znaczący wymiar tablicy.

### <a name="remarks"></a>Uwagi

W przypadku błędu funkcja zgłasza [COleException](../../mfc/reference/coleexception-class.md).

## <a name="colesafearrayresizeonedim"></a><a name="resizeonedim"></a> COleSafeArray::ResizeOneDim

Zmienia liczbę elementów w jednowymiarowym `COleSafeArray` obiekcie.

```cpp
void ResizeOneDim(DWORD dwElements);
```

### <a name="parameters"></a>Parametry

*dwElements*<br/>
Liczba elementów w tablicy jednowymiarowej bezpiecznej.

### <a name="remarks"></a>Uwagi

W przypadku błędu funkcja zgłasza [COleException](../../mfc/reference/coleexception-class.md).

### <a name="example"></a>Przykład

  Zobacz przykład dla [COleSafeArray:: CreateOneDim](#createonedim).

## <a name="colesafearrayunaccessdata"></a><a name="unaccessdata"></a> COleSafeArray::UnaccessData

Zmniejsza liczbę blokad tablicy i unieważnia wskaźnik pobrany przez `AccessData` .

```cpp
void UnaccessData();
```

### <a name="remarks"></a>Uwagi

W przypadku błędu funkcja zgłasza [COleException](../../mfc/reference/coleexception-class.md).

### <a name="example"></a>Przykład

  Zobacz przykład dla [COleSafeArray:: AccessData](#accessdata).

## <a name="colesafearrayunlock"></a><a name="unlock"></a> COleSafeArray:: Unlock

Zmniejsza liczbę blokad tablicy, aby można ją było zwolnić lub zmienić jej rozmiar.

```cpp
void Unlock();
```

### <a name="remarks"></a>Uwagi

Ta funkcja jest wywoływana po zakończeniu dostępu do danych w tablicy. W przypadku błędu zgłasza [COleException](../../mfc/reference/coleexception-class.md).

## <a name="see-also"></a>Zobacz też

[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasa COleVariant](../../mfc/reference/colevariant-class.md)<br/>
[Klasa CRecordset](../../mfc/reference/crecordset-class.md)<br/>
[Klasa CDatabase](../../mfc/reference/cdatabase-class.md)<br/>
