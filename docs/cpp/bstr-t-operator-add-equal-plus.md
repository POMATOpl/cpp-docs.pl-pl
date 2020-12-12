---
description: 'Dowiedz się więcej na temat: _bstr_t:: operator + =, +'
title: _bstr_t::operator +=, +
ms.date: 11/04/2016
f1_keywords:
- _bstr_t::operator+
- _bstr_t::operator+=
helpviewer_keywords:
- += operator [C++], appending strings
- + operator [C++], _bstr_t objects
ms.assetid: d28316ce-c2c8-4a38-bdb3-44fa4e582c44
ms.openlocfilehash: e3ae71a3a43e189251ac0ddaf77572656a031aaf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97308812"
---
# <a name="_bstr_toperator--"></a>_bstr_t::operator +=, +

**Specyficzne dla firmy Microsoft**

Dołącza znaki do końca `_bstr_t` obiektu lub łączy dwa ciągi.

## <a name="syntax"></a>Składnia

```
_bstr_t& operator+=( const _bstr_t& s1 );
_bstr_t operator+( const _bstr_t& s1 );
friend _bstr_t operator+( const char* s2, const _bstr_t& s1);
friend _bstr_t operator+( const wchar_t* s3, const _bstr_t& s1);
```

#### <a name="parameters"></a>Parametry

*S2*<br/>
Obiekt `_bstr_t`.

*S2*<br/>
Ciąg wielobajtowy.

*S3*<br/>
Ciąg Unicode.

## <a name="remarks"></a>Uwagi

Te operatory wykonują łączenie ciągów:

- **operator + = (**  *S1*  **)** Dołącza znaki z hermetyzowania `BSTR` *S1* do końca tego obiektu `BSTR` .

- **operator + (**  *S1*  **)** Zwraca nowy `_bstr_t` , który jest tworzony przez złączenie tego obiektu z tym obiektem z warstwy `BSTR` *S1*.

- **operator + (***S2* **&#124;** *S1***)** Zwraca nowy `_bstr_t` , który jest tworzony przez złączenie ciągu wielobajtowego *S2*, konwertowane na Unicode, z `BSTR` hermetyzacją w *S1*.        

- **operator + (**  *S3* **,**  *S1*  **)** Zwraca nowy `_bstr_t` , który jest tworzony przez złączenie ciągu Unicode *S3* z `BSTR` hermetyzacją w *S1*.

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Klasa _bstr_t](../cpp/bstr-t-class.md)
