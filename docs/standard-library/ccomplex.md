---
description: 'Dowiedz się więcej na temat: &lt; ccomplex&gt;'
title: '&lt;ccomplex&gt;'
ms.date: 07/11/2019
f1_keywords:
- <ccomplex>
- ccomplex
helpviewer_keywords:
- ccomplex header
ms.assetid: a9fcb5f0-88e3-464b-a5fd-d1afb8cd7e6f
ms.openlocfilehash: d657d7b0b2a203bcbad93ff1c78f6b78eb4d7707
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97325318"
---
# <a name="ltccomplexgt"></a>&lt;ccomplex&gt;

Zawiera nagłówek standardowej biblioteki języka C++ [\<complex>](complex.md) .

> [!NOTE]
> Nagłówek standardowej biblioteki C \<complex.h> nie jest zawarty w \<ccomplex> , ponieważ jest efektywnie zastępowany przez przeciążenia C++ w \<complex> i \<cmath> . Powoduje to, że \<ccomplex> nagłówek jest nadmiarowy. \<complex.h>Nagłówek jest przestarzały w języku C++. \<ccomplex>Nagłówek jest przestarzały w języku c++ 17 i został usunięty z wersji Standard c++ 20.

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<ccomplex>

**Przestrzeń nazw:** std

## <a name="remarks"></a>Uwagi

Nazwa `clog` , która jest zadeklarowana w \<complex.h> , nie jest zdefiniowana w `std` przestrzeni nazw ze względu na potencjalne konflikty z `clog` zadeklarowaną w elemencie [\<iostream>](iostream.md) .

## <a name="see-also"></a>Zobacz też

[\<complex>](complex.md)\
[\<cmath>](cmath.md)\
[Dokumentacja plików nagłówkowych](cpp-standard-library-header-files.md)\
[Omówienie standardowej biblioteki języka C++](cpp-standard-library-overview.md)\
[Bezpieczeństwo wątku w standardowej bibliotece języka C++](thread-safety-in-the-cpp-standard-library.md)
