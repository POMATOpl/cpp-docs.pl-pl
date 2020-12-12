---
description: 'Dowiedz się więcej na temat: _com_error:: Source'
title: _com_error::Source
ms.date: 11/04/2016
f1_keywords:
- _com_error::Source
helpviewer_keywords:
- Source method [C++]
ms.assetid: 55353741-fabc-4b0c-9787-b5a69bb189f2
ms.openlocfilehash: 3b6cf35420454e8285d3d8b4deee3df8fe8771e4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97295773"
---
# <a name="_com_errorsource"></a>_com_error::Source

**Specyficzne dla firmy Microsoft**

Wywołuje `IErrorInfo::GetSource` funkcję.

## <a name="syntax"></a>Składnia

```
_bstr_t Source() const;
```

## <a name="return-value"></a>Wartość zwracana

Zwraca wynik `IErrorInfo::GetSource` dla `IErrorInfo` obiektu zarejestrowanego w `_com_error` obiekcie. Wyniki `BSTR` są hermetyzowane w `_bstr_t` obiekcie. Jeśli nie `IErrorInfo` jest zarejestrowany, zwraca wartość pustą `_bstr_t` .

## <a name="remarks"></a>Uwagi

Wszelkie błędy podczas wywoływania `IErrorInfo::GetSource` metody są ignorowane.

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Klasa _com_error](../cpp/com-error-class.md)
