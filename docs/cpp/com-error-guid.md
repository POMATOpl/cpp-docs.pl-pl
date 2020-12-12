---
description: 'Dowiedz się więcej na temat: _com_error:: GUID'
title: _com_error::GUID
ms.date: 11/04/2016
f1_keywords:
- _com_error::GUID
helpviewer_keywords:
- GUID method [C++]
ms.assetid: e84c2c23-d02e-48f8-b776-9bd6937296d2
ms.openlocfilehash: 32f88728d5c0f93094413aaeae8fb3c116b415c3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97295968"
---
# <a name="_com_errorguid"></a>_com_error::GUID

**Specyficzne dla firmy Microsoft**

Wywołuje `IErrorInfo::GetGUID` funkcję.

## <a name="syntax"></a>Składnia

```
GUID GUID( ) const throw( );
```

## <a name="return-value"></a>Wartość zwracana

Zwraca wynik `IErrorInfo::GetGUID` dla `IErrorInfo` obiektu zarejestrowanego w `_com_error` obiekcie. Jeśli żaden `IErrorInfo` obiekt nie jest zarejestrowany, zwraca `GUID_NULL` .

## <a name="remarks"></a>Uwagi

Wszelkie błędy podczas wywoływania `IErrorInfo::GetGUID` metody są ignorowane.

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Klasa _com_error](../cpp/com-error-class.md)
