---
description: 'Dowiedz się więcej na temat: _com_error:: HelpFile'
title: _com_error::HelpFile
ms.date: 11/04/2016
f1_keywords:
- _com_error::HelpFile
helpviewer_keywords:
- HelpFile method [C++]
ms.assetid: d2d3a0a1-6b62-4d52-a818-3cfae545a4af
ms.openlocfilehash: e45785913a8a5a1909f702bce672727171e0baef
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97295929"
---
# <a name="_com_errorhelpfile"></a>_com_error::HelpFile

**Specyficzne dla firmy Microsoft**

Wywołuje `IErrorInfo::GetHelpFile` funkcję.

## <a name="syntax"></a>Składnia

```
_bstr_t HelpFile() const;
```

## <a name="return-value"></a>Wartość zwracana

Zwraca wynik `IErrorInfo::GetHelpFile` dla `IErrorInfo` obiektu zarejestrowanego w `_com_error` obiekcie. Powstający element BSTR jest hermetyzowany w `_bstr_t` obiekcie. Jeśli nie `IErrorInfo` jest zarejestrowany, zwraca wartość pustą `_bstr_t` .

## <a name="remarks"></a>Uwagi

Wszelkie błędy podczas wywoływania `IErrorInfo::GetHelpFile` metody są ignorowane.

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Klasa _com_error](../cpp/com-error-class.md)
