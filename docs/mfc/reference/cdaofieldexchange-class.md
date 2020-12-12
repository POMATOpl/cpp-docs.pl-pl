---
description: 'Dowiedz się więcej na temat: Klasa CDaoFieldExchange'
title: Klasa CDaoFieldExchange
ms.date: 09/17/2019
f1_keywords:
- CDaoFieldExchange
- AFXDAO/CDaoFieldExchange
- AFXDAO/CDaoFieldExchange::IsValidOperation
- AFXDAO/CDaoFieldExchange::SetFieldType
- AFXDAO/CDaoFieldExchange::m_nOperation
- AFXDAO/CDaoFieldExchange::m_prs
helpviewer_keywords:
- CDaoFieldExchange [MFC], IsValidOperation
- CDaoFieldExchange [MFC], SetFieldType
- CDaoFieldExchange [MFC], m_nOperation
- CDaoFieldExchange [MFC], m_prs
ms.assetid: 350a663e-92ff-44ab-ad53-d94efa2e5823
ms.openlocfilehash: 41389ca9f1f9321abc828f9625f1fef3e745054d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97250910"
---
# <a name="cdaofieldexchange-class"></a>Klasa CDaoFieldExchange

Obsługuje procedury wymiany pól rekordów DAO (DFX) używane przez klasy bazy danych DAO.

Obiekty DAO są obsługiwane przez pakiet Office 2013. Element DAO 3,6 jest wersją ostateczną i jest uznawany za przestarzały.

## <a name="syntax"></a>Składnia

```
class CDaoFieldExchange
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CDaoFieldExchange::IsValidOperation](#isvalidoperation)|Zwraca wartość różną od zera, jeśli bieżąca operacja jest odpowiednia dla typu aktualizowanego pola.|
|[CDaoFieldExchange:: SetFieldType](#setfieldtype)|Określa typ składowej danych zestawu rekordów — kolumny lub parametru — reprezentowane przez wszystkie kolejne wywołania funkcji DFX do momentu następnego wywołania metody `SetFieldType` .|

### <a name="public-data-members"></a>Publiczne elementy członkowskie danych

|Nazwa|Opis|
|----------|-----------------|
|[CDaoFieldExchange:: m_nOperation](#m_noperation)|Operacja DFX wykonywana przez bieżące wywołanie `DoFieldExchange` funkcji składowej zestawu rekordów.|
|[CDaoFieldExchange:: m_prs](#m_prs)|Wskaźnik do zestawu rekordów, na którym są wykonywane operacje DFX.|

## <a name="remarks"></a>Uwagi

`CDaoFieldExchange` nie ma klasy bazowej.

Użyj tej klasy, jeśli piszesz procedury wymiany danych dla niestandardowych typów danych; w przeciwnym razie nie będziesz bezpośrednio używać tej klasy. DFX wymienia dane między elementami członkowskimi danych pola obiektu [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) i odpowiednimi polami bieżącego rekordu w źródle danych. DFX zarządza wymianą w obu kierunkach ze źródła danych i źródła danych. Aby uzyskać informacje o tworzeniu niestandardowych procedur DFX, zobacz [Uwagi techniczne 53](../../mfc/tn053-custom-dfx-routines-for-dao-database-classes.md) .

> [!NOTE]
> Klasy bazy danych DAO różnią się od klas baz danych MFC opartych na Open Database Connectivity (ODBC). Wszystkie nazwy klas baz danych DAO mają prefiks "CDao". Nadal można uzyskać dostęp do źródeł danych ODBC przy użyciu klas DAO. Ogólnie rzecz biorąc, klasy MFC oparte na obiektach DAO są bardziej możliwością niż klasy MFC oparte na ODBC. Klasy oparte na DAO mogą uzyskiwać dostęp do danych, w tym za pośrednictwem sterowników ODBC, za pośrednictwem własnego aparatu bazy danych. Obsługują one również operacje języka definicji danych (DDL), takie jak Dodawanie tabel za pośrednictwem klas zamiast konieczności samodzielnego wywoływania obiektów DAO.

> [!NOTE]
> Wymiana pól rekordów DAO (DFX) jest bardzo podobna do wymiany pól rekordów (RFX) w klasach baz danych MFC opartych na ODBC ( `CDatabase` , `CRecordset` ). Jeśli rozumiesz RFX, będziesz w łatwy sposób korzystać z DFX.

`CDaoFieldExchange`Obiekt zawiera informacje kontekstu, które są konieczne do wymiany pól rekordów DAO. `CDaoFieldExchange` obiekty obsługują wiele operacji, w tym parametry powiązania i elementy członkowskie danych pól oraz ustawienia różnych flag dla pól bieżącego rekordu. Operacje DFX są wykonywane na elementach członkowskich danych klasy zestawu rekordów typów zdefiniowanych przez wartość **`enum`** **FieldType** w `CDaoFieldExchange` . Możliwe wartości **FieldType** to:

- `CDaoFieldExchange::outputColumn` dla elementów członkowskich danych pola.

- `CDaoFieldExchange::param` dla elementów członkowskich danych parametru.

Funkcja członkowska [IsValidOperation](#isvalidoperation) jest udostępniana do pisania własnych niestandardowych procedur DFX. Funkcja [SetFieldType](#setfieldtype) jest często używana w funkcjach [CDaoRecordset::D ofieldexchange](../../mfc/reference/cdaorecordset-class.md#dofieldexchange) . Szczegółowe informacje o funkcjach globalnych DFX można znaleźć w temacie [Record Field Exchange Functions](../../mfc/reference/record-field-exchange-functions.md). Aby uzyskać informacje o tworzeniu niestandardowych procedur DFX dla własnych typów danych, zobacz [Uwagi techniczne 53](../../mfc/tn053-custom-dfx-routines-for-dao-database-classes.md).

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`CDaoFieldExchange`

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxdao. h

## <a name="cdaofieldexchangeisvalidoperation"></a><a name="isvalidoperation"></a> CDaoFieldExchange::IsValidOperation

Jeśli piszesz własną funkcję DFX, wywołaj `IsValidOperation` na początku funkcji, aby określić, czy bieżącą operację można wykonać na konkretnym typie elementu członkowskiego danych pola (a `CDaoFieldExchange::outputColumn` lub a `CDaoFieldExchange::param` ).

```
BOOL IsValidOperation();
```

### <a name="return-value"></a>Wartość zwracana

Różne od zera, jeśli bieżąca operacja jest odpowiednia dla typu aktualizowanego pola.

### <a name="remarks"></a>Uwagi

Niektóre operacje wykonywane przez mechanizm DFX mają zastosowanie tylko do jednego z możliwych typów pól. Postępuj zgodnie z modelem istniejących funkcji DFX.

Aby uzyskać dodatkowe informacje na temat pisania niestandardowych procedur DFX, zobacz [Uwagi techniczne 53](../../mfc/tn053-custom-dfx-routines-for-dao-database-classes.md).

## <a name="cdaofieldexchangem_noperation"></a><a name="m_noperation"></a> CDaoFieldExchange:: m_nOperation

Identyfikuje operację wykonywaną na obiekcie [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) skojarzonym z obiektem wymiany pól.

### <a name="remarks"></a>Uwagi

`CDaoFieldExchange`Obiekt udostępnia kontekst dla wielu różnych operacji DFX na zestawie rekordów.

> [!NOTE]
> Wartość PSEUDONULL opisana w poniższych operacjach MarkForAddNew i SetFieldNull to wartość użyta do oznaczenia pól o wartości null. Mechanizm wymiany pola rekordu DAO (DFX) używa tej wartości do określenia, które pola zostały jawnie oznaczone jako puste. PSEUDONULL nie jest wymagana dla pól [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) i [COleCurrency](../../mfc/reference/colecurrency-class.md) .

Możliwe wartości `m_nOperation` :

|Operacja|Opis|
|---------------|-----------------|
|`AddToParameterList`|Kompiluje klauzulę **Parameters** instrukcji SQL.|
|`AddToSelectList`|Kompiluje klauzulę **SELECT** instrukcji SQL.|
|`BindField`|Tworzy powiązanie pola w bazie danych z lokalizacją w pamięci aplikacji.|
|`BindParam`|Ustawia wartości parametrów dla zapytania zestawu rekordów.|
|`Fixup`|Ustawia stan null dla pola.|
|`AllocCache`|Przypisuje pamięć podręczną służącą do sprawdzania "zanieczyszczonych" pól w zestawie rekordów.|
|`StoreField`|Zapisuje bieżący rekord w pamięci podręcznej.|
|`LoadField`|Przywraca zmienne elementu członkowskiego danych w pamięci podręcznej.|
|`FreeCache`|Zwalnia pamięć podręczną służącą do sprawdzania "zanieczyszczonych" pól w zestawie rekordów.|
|`SetFieldNull`|Ustawia stan pola na wartość null i wartość na PSEUDONULL.|
|`MarkForAddNew`|Oznacza pola "zanieczyszczony", jeśli nie PSEUDONULL.|
|`MarkForEdit`|Oznacza pola jako zanieczyszczone, jeśli są niezgodne z pamięcią podręczną.|
|`SetDirtyField`|Ustawia wartości pól oznaczone jako "zanieczyszczone".|
|`DumpField`|Zrzuca zawartość pola (tylko debugowanie).|
|`MaxDFXOperation`|Używany do sprawdzania danych wejściowych.|

## <a name="cdaofieldexchangem_prs"></a><a name="m_prs"></a> CDaoFieldExchange:: m_prs

Zawiera wskaźnik do obiektu [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) skojarzonego z `CDaoFieldExchange` obiektem.

### <a name="remarks"></a>Uwagi

## <a name="cdaofieldexchangesetfieldtype"></a><a name="setfieldtype"></a> CDaoFieldExchange:: SetFieldType

Wywołanie `SetFieldType` w `CDaoRecordset` `DoFieldExchange` przesłonięciu klasy.

```cpp
void SetFieldType(UINT nFieldType);
```

### <a name="parameters"></a>Parametry

*nFieldType*<br/>
Wartość **pola EnumType** zadeklarowana w `CDaoFieldExchange` , która może mieć jedną z następujących wartości:

- `CDaoFieldExchange::outputColumn`

- `CDaoFieldExchange::param`

### <a name="remarks"></a>Uwagi

Zwykle ClassWizard to wywołanie. Jeśli piszesz własną funkcję i używasz Kreatora do pisania `DoFieldExchange` funkcji, Dodaj wywołania do własnej funkcji poza mapą pól. Jeśli Kreator nie zostanie użyty, nie będzie mapy pól. Wywołanie poprzedza wywołania funkcji DFX, po jednym dla każdego elementu członkowskiego danych w klasie i identyfikuje typ pola jako `CDaoFieldExchange::outputColumn` .

W przypadku Sparametryzuj klasy zestawu rekordów należy dodać wywołania DFX dla wszystkich elementów członkowskich danych parametrów (poza mapą pola) i poprzedzić te wywołania wywołaniem metody `SetFieldType` . Przekaż wartość `CDaoFieldExchange::param` . (Zamiast tego można użyć [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md) i ustawić jego wartości parametrów).

Ogólnie rzecz biorąc każda grupa wywołań funkcji DFX skojarzonych z elementami członkowskimi danych pól lub składowymi danych parametrów musi być poprzedzona wywołaniem metody `SetFieldType` . Parametr *nFieldType* każdego `SetFieldType` wywołania identyfikuje typ elementów członkowskich danych reprezentowanych przez wywołania funkcji DFX, które są zgodne z `SetFieldType` wywołaniem.

## <a name="see-also"></a>Zobacz też

[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasa CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)
