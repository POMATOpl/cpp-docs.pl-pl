---
description: 'Dowiedz się więcej na temat: _bstr_t:: wchar_t *, _bstr_t:: char*'
title: _bstr_t::wchar_t *, _bstr_t::char*
ms.date: 11/04/2016
f1_keywords:
- _bstr_t::wchar_t*
- _bstr_t::char*
helpviewer_keywords:
- operator wchar_t* [C++]
- operator char* [C++]
ms.assetid: acd9f4a7-b427-42c2-aaae-acae21cab317
ms.openlocfilehash: 278b122bbc208addab8e9a40e61300ce91a530cf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97278821"
---
# <a name="_bstr_twchar_t-_bstr_tchar"></a>_bstr_t::wchar_t\*, _bstr_t::char\*

**Specyficzne dla firmy Microsoft**

Zwraca znaki BSTR jako tablicę o wąskim lub szerokim znaku.

## <a name="syntax"></a>Składnia

```
operator const wchar_t*( ) const throw( );
operator wchar_t*( ) const throw( );
operator const char*( ) const;
operator char*( ) const;
```

## <a name="remarks"></a>Uwagi

Te operatory mogą służyć do wyodrębniania danych znakowych, które są hermetyzowane przez `BSTR` obiekt. Przypisanie nowej wartości do zwracanego wskaźnika nie powoduje modyfikacji oryginalnych danych BSTR.

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Klasa _bstr_t](../cpp/bstr-t-class.md)
