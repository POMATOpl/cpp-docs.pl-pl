---
description: 'Dowiedz się więcej na temat: _com_error:: atrybut HelpContext'
title: _com_error::HelpContext
ms.date: 11/04/2016
f1_keywords:
- _com_error::HelpContext
helpviewer_keywords:
- HelpContext method [C++]
ms.assetid: 160d6443-9b68-4cf5-a540-50da951a5b2b
ms.openlocfilehash: 757fb572d9e41486af419712eb7f70cd7cfa7b14
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97295942"
---
# <a name="_com_errorhelpcontext"></a>_com_error::HelpContext

**Specyficzne dla firmy Microsoft**

Wywołuje `IErrorInfo::GetHelpContext` funkcję.

## <a name="syntax"></a>Składnia

```
DWORD HelpContext( ) const throw( );
```

## <a name="return-value"></a>Wartość zwracana

Zwraca wynik `IErrorInfo::GetHelpContext` dla `IErrorInfo` obiektu zarejestrowanego w `_com_error` obiekcie. Jeśli żaden `IErrorInfo` obiekt nie jest zarejestrowany, zwraca zero.

## <a name="remarks"></a>Uwagi

Wszelkie błędy podczas wywoływania `IErrorInfo::GetHelpContext` metody są ignorowane.

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Klasa _com_error](../cpp/com-error-class.md)
