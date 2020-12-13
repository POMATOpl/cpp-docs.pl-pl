---
description: 'Dowiedz się więcej na temat: Klasa CW2WEX'
title: Klasa CW2WEX
ms.date: 11/04/2016
f1_keywords:
- CW2WEX
- ATLCONV/ATL::CW2WEX
- ATLCONV/ATL::CW2WEX::CW2WEX
- ATLCONV/ATL::CW2WEX::m_psz
- ATLCONV/ATL::CW2WEX::m_szBuffer
helpviewer_keywords:
- CW2WEX class
ms.assetid: 46262e56-e0d2-41fe-855b-0b67ecc8fcd7
ms.openlocfilehash: 87dbcefe37a54270b021ee1446ba5ccba2ef8313
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97140247"
---
# <a name="cw2wex-class"></a>Klasa CW2WEX

Ta klasa jest używana przez makra konwersji ciągów CW2TEX i CT2WEX oraz typedef CW2W.

> [!IMPORTANT]
> Tej klasy i jej elementów członkowskich nie można używać w aplikacjach, które są wykonywane w środowisko wykonawcze systemu Windows.

## <a name="syntax"></a>Składnia

```
template <int t_nBufferLength = 128>
class CW2WEX
```

#### <a name="parameters"></a>Parametry

*t_nBufferLength*<br/>
Rozmiar buforu używany w procesie tłumaczenia. Domyślna długość to 128 bajtów.

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CW2WEX::CW2WEX](#cw2wex)|Konstruktor.|
|[CW2WEX:: ~ CW2WEX](#dtor)|Destruktor.|

### <a name="public-operators"></a>Operatory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CW2WEX:: operator LPWSTR](#operator_lpwstr)|Operator konwersji.|

### <a name="public-data-members"></a>Publiczne elementy członkowskie danych

|Nazwa|Opis|
|----------|-----------------|
|[CW2WEX:: m_psz](#m_psz)|Element członkowski danych przechowujący ciąg źródłowy.|
|[CW2WEX:: m_szBuffer](#m_szbuffer)|Bufor statyczny używany do przechowywania przekonwertowanego ciągu.|

## <a name="remarks"></a>Uwagi

O ile nie jest wymagana dodatkowa funkcjonalność, użyj CW2TEX, CT2WEX lub CW2W w kodzie.

Ta klasa zawiera bufor statyczny o stałym rozmiarze, który jest używany do przechowywania wyniku konwersji. Jeśli wynik jest zbyt duży, aby zmieścił się w buforze statycznym, Klasa przydziela pamięć przy użyciu **malloc**, zwalniając pamięć, gdy obiekt wykracza poza zakres. Dzięki temu, w przeciwieństwie do makr konwersji tekstu dostępnych we wcześniejszych wersjach ATL, ta klasa jest bezpieczna do użycia w pętlach i nie przechodzą stosu.

Jeśli klasa próbuje przydzielić pamięć na stercie i kończy się niepowodzeniem, wywoła `AtlThrow` z argumentem E_OUTOFMEMORY.

Domyślnie klasy konwersji ATL i makra używają strony kodowej ANSI bieżącego wątku dla konwersji.

Następujące makra są oparte na tej klasie:

- CW2TEX

- CT2WEX

Następujący element typedef jest oparty na tej klasie:

- CW2W

Aby zapoznać się z tymi makrami konwersji tekstu, zobacz [makra konwersji ATL i MFC String](string-conversion-macros.md).

## <a name="example"></a>Przykład

Zobacz [makra konwersji ciągów ATL i MFC,](string-conversion-macros.md) aby zapoznać się z przykładem użycia tych makr konwersji ciągów.

## <a name="requirements"></a>Wymagania

**Nagłówek:** atlconv. h

## <a name="cw2wexcw2wex"></a><a name="cw2wex"></a> CW2WEX::CW2WEX

Konstruktor.

```
CW2WEX(LPCWSTR psz, UINT nCodePage) throw(...);
CW2WEX( LPCWSTR  psz) throw(...);
```

### <a name="parameters"></a>Parametry

*psz*<br/>
Ciąg tekstowy do przekonwertowania.

*nCodePage*<br/>
Strona kodowa. Nieużywane w tej klasie.

### <a name="remarks"></a>Uwagi

Tworzy bufor wymagany do tłumaczenia.

## <a name="cw2wexcw2wex"></a><a name="dtor"></a> CW2WEX:: ~ CW2WEX

Destruktor..

```
~CW2WEX() throw();
```

### <a name="remarks"></a>Uwagi

Zwalnia przydzieloną bufor.

## <a name="cw2wexm_psz"></a><a name="m_psz"></a> CW2WEX:: m_psz

Element członkowski danych przechowujący ciąg źródłowy.

```
LPWSTR m_psz;
```

## <a name="cw2wexm_szbuffer"></a><a name="m_szbuffer"></a> CW2WEX:: m_szBuffer

Bufor statyczny używany do przechowywania przekonwertowanego ciągu.

```
wchar_t m_szBuffer[t_nBufferLength];
```

## <a name="cw2wexoperator-lpwstr"></a><a name="operator_lpwstr"></a> CW2WEX:: operator LPWSTR

Operator rzutowania.

```
operator LPWSTR() const throw();
```

### <a name="return-value"></a>Wartość zwracana

Zwraca ciąg tekstowy jako typ LPWSTR.

## <a name="see-also"></a>Zobacz też

[Klasa CA2AEX](../../atl/reference/ca2aex-class.md)<br/>
[Klasa CA2CAEX](../../atl/reference/ca2caex-class.md)<br/>
[Klasa CA2WEX](../../atl/reference/ca2wex-class.md)<br/>
[Klasa CW2AEX](../../atl/reference/cw2aex-class.md)<br/>
[Klasa CW2CWEX](../../atl/reference/cw2cwex-class.md)<br/>
[Przegląd klas](../../atl/atl-class-overview.md)
