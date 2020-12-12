---
description: 'Dowiedz się więcej na temat: Klasa CFixedStringT'
title: Klasa CFixedStringT
ms.date: 03/27/2019
f1_keywords:
- CFixedStringT
- CSTRINGT/ATL::CFixedStringT
- CSTRINGT/ATL::CFixedStringT::CFixedStringT
helpviewer_keywords:
- CFixedStringT class
- shared classes, CFixedStringT
ms.assetid: 6d4171ba-3104-493a-a6cc-d515f4ba9a4b
ms.openlocfilehash: a613716364318ced140709d2b33e9d9c4299af0b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97166839"
---
# <a name="cfixedstringt-class"></a>Klasa CFixedStringT

Ta klasa reprezentuje obiekt String z buforem o stałym znaku.

## <a name="syntax"></a>Składnia

```
template<class StringType, int t_nChars>
class CFixedStringT : private CFixedStringMgr, public StringType
```

#### <a name="parameters"></a>Parametry

*StringType*<br/>
Używane jako klasa bazowa dla obiektu stałego ciągu i może być dowolnego `CStringT` typu. Przykłady obejmują `CString` , `CStringA` , i `CStringW` .

*t_nChars*<br/>
Liczba znaków przechowywanych w buforze.

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CFixedStringT:: CFixedStringT](#cfixedstringt)|Konstruktor dla obiektu String.|

### <a name="public-operators"></a>Operatory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CFixedStringT:: operator =](#operator_eq)|Przypisuje nową wartość do `CFixedStringT` obiektu.|

## <a name="remarks"></a>Uwagi

Ta klasa jest przykładem niestandardowej klasy ciągów opartej na `CStringT` . Chociaż podobne, te dwie klasy różnią się w implementacji. Główne różnice między elementami `CFixedStringT` i `CStringT` są:

- Początkowy bufor znaków jest przypisywany jako część obiektu i ma *t_nChars* rozmiaru. Umożliwia to `CFixedString` obiektowi zajmowanie ciągłego fragmentu pamięci w celu zapewnienia wydajności. Jeśli jednak zawartość `CFixedStringT` obiektu rośnie poza *t_nChars*, bufor jest przydzielany dynamicznie.

- Bufor znaków dla `CFixedStringT` obiektu ma zawsze taką samą długość ( *t_nChars*). Nie ma ograniczeń dotyczących rozmiaru buforu dla `CStringT` obiektów.

- Menedżer pamięci dla `CFixedStringT` został dostosowany w taki sposób, że udostępnianie obiektu [CStringData](../../atl-mfc-shared/reference/cstringdata-class.md) między dwoma lub więcej `CFixedStringT` obiektami jest niedozwolone. `CStringT` w obiektach nie ma tego ograniczenia.

Aby uzyskać więcej informacji na temat dostosowywania `CFixedStringT` i zarządzania pamięcią dla obiektów String, zobacz [Zarządzanie pamięcią i CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`IAtlStringMgr`

`StringType`

`CFixedStringMgr`

`CFixedStringT`

## <a name="requirements"></a>Wymagania

**Nagłówek:** CStringT. h

## <a name="cfixedstringtcfixedstringt"></a><a name="cfixedstringt"></a> CFixedStringT:: CFixedStringT

Konstruuje `CFixedStringT` obiekt.

```
CFixedStringT() throw();
explicit CFixedStringT(IAtlStringMgr* pStringMgr) throw();
CFixedStringT(const CFixedStringT<StringType, t_nChars>& strSrc);
CFixedStringT(const StringType& strSrc);
CFixedStringT(const StringType::XCHAR* pszSrc);
explicit CFixedStringT(const StringType::YCHAR* pszSrc);
explicit CFixedStringT(const unsigned char* pszSrc);
```

### <a name="parameters"></a>Parametry

*pszSrc*<br/>
Ciąg zakończony znakiem null, który ma zostać skopiowany do tego `CFixedStringT` obiektu.

*strSrc*<br/>
Istniejący `CFixedStringT` obiekt do skopiowania do tego `CFixedStringT` obiektu.

*pStringMgr*<br/>
Wskaźnik do Menedżera pamięci `CFixedStringT` obiektu. Aby uzyskać więcej informacji na temat `IAtlStringMgr` zarządzania pamięcią dla programu `CFixedStringT` , zobacz [Zarządzanie pamięcią i CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).

### <a name="remarks"></a>Uwagi

Ponieważ konstruktory kopiuje dane wejściowe do nowego przydzielonego magazynu, należy pamiętać, że mogą wynikać wyjątki pamięci. Niektóre z tych konstruktorów działają jako funkcje konwersji.

## <a name="cfixedstringtoperator-"></a><a name="operator_eq"></a> CFixedStringT:: operator =

Ponownie inicjuje istniejący `CFixedStringT` obiekt z nowymi danymi.

```
CFixedStringT<StringType, t_nChars>& operator=(
    const CFixedStringT<StringType, t_nChars>& strSrc);
CFixedStringT<StringType, t_nChars>& operator=(const char* pszSrc);
CFixedStringT<StringType, t_nChars>& operator=(const wchar_t* pszSrc);
CFixedStringT<StringType, t_nChars>& operator=(const unsigned char* pszSrc);
CFixedStringT<StringType, t_nChars>& operator=(const StringType& strSrc);
```

### <a name="parameters"></a>Parametry

*pszSrc*<br/>
Ciąg zakończony znakiem null, który ma zostać skopiowany do tego `CFixedStringT` obiektu.

*strSrc*<br/>
Istniejący `CFixedStringT` do skopiowania do tego `CFixedStringT` obiektu.

### <a name="remarks"></a>Uwagi

Należy pamiętać, że wyjątki pamięci mogą wystąpić za każdym razem, gdy używasz operatora przypisania, ponieważ nowy magazyn jest często przydzielony do przechowywania wyniku `CFixedStringT` obiektu.

## <a name="see-also"></a>Zobacz też

[Klasa CStringT](../../atl-mfc-shared/reference/cstringt-class.md)<br/>
[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasy udostępnione ATL/MFC](../../atl-mfc-shared/atl-mfc-shared-classes.md)
