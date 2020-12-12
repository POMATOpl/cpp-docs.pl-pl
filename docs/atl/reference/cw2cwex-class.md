---
description: 'Dowiedz się więcej na temat: Klasa CW2CWEX'
title: Klasa CW2CWEX
ms.date: 11/04/2016
f1_keywords:
- CW2CWEX
- ATLCONV/ATL::CW2CWEX
- ATLCONV/ATL::CW2CWEX::CW2CWEX
- ATLCONV/ATL::CW2CWEX::m_psz
helpviewer_keywords:
- CW2CWEX class
ms.assetid: d654b22b-05a6-410f-a0ec-9a2cbbb4cca7
ms.openlocfilehash: 769dcedf1a9dc15129b09e3305330de33242562e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97140234"
---
# <a name="cw2cwex-class"></a>Klasa CW2CWEX

Ta klasa jest używana przez makra konwersji ciągów CW2CTEX i CT2CWEX oraz typedef CW2W.

> [!IMPORTANT]
> Tej klasy i jej elementów członkowskich nie można używać w aplikacjach, które są wykonywane w środowisko wykonawcze systemu Windows.

## <a name="syntax"></a>Składnia

```
template<int t_nBufferLength = 128>
class CW2CWEX
```

#### <a name="parameters"></a>Parametry

*t_nBufferLength*<br/>
Rozmiar buforu używany w procesie tłumaczenia. Domyślna długość to 128 bajtów.

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CW2CWEX::CW2CWEX](#cw2cwex)|Konstruktor.|
|[CW2CWEX:: ~ CW2CWEX](#dtor)|Destruktor.|

### <a name="public-operators"></a>Operatory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CW2CWEX:: operator LPCWSTR](#operator_lpcwstr)|Operator konwersji.|

### <a name="public-data-members"></a>Publiczne elementy członkowskie danych

|Nazwa|Opis|
|----------|-----------------|
|[CW2CWEX:: m_psz](#m_psz)|Element członkowski danych przechowujący ciąg źródłowy.|

## <a name="remarks"></a>Uwagi

O ile nie jest wymagana dodatkowa funkcjonalność, użyj CW2CTEX, CT2CWEX lub CW2W w kodzie.

Ta klasa jest bezpieczna do użycia w pętlach i nie przechodzą na stos. Domyślnie klasy konwersji ATL i makra używają strony kodowej ANSI bieżącego wątku dla konwersji.

Następujące makra są oparte na tej klasie:

- CW2CTEX

- CT2CWEX

Następujący element typedef jest oparty na tej klasie:

- CW2W

Aby zapoznać się z tymi makrami konwersji tekstu, zobacz [makra konwersji ATL i MFC String](string-conversion-macros.md).

## <a name="example"></a>Przykład

Zobacz [makra konwersji ciągów ATL i MFC,](string-conversion-macros.md) aby zapoznać się z przykładem użycia tych makr konwersji ciągów.

## <a name="requirements"></a>Wymagania

**Nagłówek:** atlconv. h

## <a name="cw2cwexcw2cwex"></a><a name="cw2cwex"></a> CW2CWEX::CW2CWEX

Konstruktor.

```
CW2CWEX(LPCWSTR psz, UINT nCodePage) throw(...);
CW2CWEX(LPCWSTR psz) throw(...);
```

### <a name="parameters"></a>Parametry

*psz*<br/>
Ciąg tekstowy do przekonwertowania.

*nCodePage*<br/>
Strona kodowa. Nieużywane w tej klasie.

### <a name="remarks"></a>Uwagi

Przypisuje bufor używany w procesie tłumaczenia.

## <a name="cw2cwexcw2cwex"></a><a name="dtor"></a> CW2CWEX:: ~ CW2CWEX

Destruktor.

```
~CW2CWEX() throw();
```

### <a name="remarks"></a>Uwagi

Zwalnia przydzieloną bufor.

## <a name="cw2cwexm_psz"></a><a name="m_psz"></a> CW2CWEX:: m_psz

Element członkowski danych przechowujący ciąg źródłowy.

```
LPCWSTR m_psz;
```

## <a name="cw2cwexoperator-lpcwstr"></a><a name="operator_lpcwstr"></a> CW2CWEX:: operator LPCWSTR

Operator konwersji.

```
operator LPCWSTR() const throw();
```

### <a name="return-value"></a>Wartość zwracana

Zwraca ciąg tekstowy jako typ LPCWSTR.

## <a name="see-also"></a>Zobacz też

[Klasa CA2AEX](../../atl/reference/ca2aex-class.md)<br/>
[Klasa CA2CAEX](../../atl/reference/ca2caex-class.md)<br/>
[Klasa CA2WEX](../../atl/reference/ca2wex-class.md)<br/>
[Klasa CW2AEX](../../atl/reference/cw2aex-class.md)<br/>
[Klasa CW2WEX](../../atl/reference/cw2wex-class.md)<br/>
[Przegląd klas](../../atl/atl-class-overview.md)
