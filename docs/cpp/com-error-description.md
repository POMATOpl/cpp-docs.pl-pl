---
description: 'Dowiedz się więcej na temat: _com_error::D opis'
title: _com_error::Description
ms.date: 11/04/2016
f1_keywords:
- _com_error::Description
helpviewer_keywords:
- Description method [C++]
ms.assetid: 88191e24-4ee8-44a6-8c4c-3758e22e0548
ms.openlocfilehash: 6404d16361abe81d9e234a6b63039a7476d91ef1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97332550"
---
# <a name="_com_errordescription"></a>_com_error::Description

**Specyficzne dla firmy Microsoft**

Wywołuje `IErrorInfo::GetDescription` funkcję.

## <a name="syntax"></a>Składnia

```
_bstr_t Description( ) const;
```

## <a name="return-value"></a>Wartość zwracana

Zwraca wynik `IErrorInfo::GetDescription` dla `IErrorInfo` obiektu zarejestrowanego w `_com_error` obiekcie. Wyniki `BSTR` są hermetyzowane w `_bstr_t` obiekcie. Jeśli nie `IErrorInfo` jest zarejestrowany, zwraca wartość pustą `_bstr_t` .

## <a name="remarks"></a>Uwagi

Wywołuje `IErrorInfo::GetDescription` funkcję i pobiera `IErrorInfo` zarejestrowane w `_com_error` obiekcie. Wszelkie błędy podczas wywoływania `IErrorInfo::GetDescription` metody są ignorowane.

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Klasa _com_error](../cpp/com-error-class.md)
