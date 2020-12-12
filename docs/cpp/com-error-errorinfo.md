---
description: 'Dowiedz się więcej na temat: _com_error:: ErrorInfo'
title: _com_error::ErrorInfo
ms.date: 11/04/2016
f1_keywords:
- _com_error::ErrorInfo
helpviewer_keywords:
- ErrorInfo method [C++]
ms.assetid: 071b446c-4395-4fb8-bd3d-300a8b25f5cd
ms.openlocfilehash: 36092ae9287352d421bf502ad24c054cf3b7a907
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97296046"
---
# <a name="_com_errorerrorinfo"></a>_com_error::ErrorInfo

**Specyficzne dla firmy Microsoft**

Pobiera `IErrorInfo` obiekt przesłany do konstruktora.

## <a name="syntax"></a>Składnia

```
IErrorInfo * ErrorInfo( ) const throw( );
```

## <a name="return-value"></a>Wartość zwracana

Nieprzetworzony `IErrorInfo` element przeszedł do konstruktora.

## <a name="remarks"></a>Uwagi

Pobiera hermetyzowany `IErrorInfo` element w `_com_error` obiekcie lub wartość null, jeśli żaden `IErrorInfo` element nie jest zarejestrowany. Obiekt wywołujący musi wywołać `Release` dla zwróconego obiektu po jego zakończeniu.

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Klasa _com_error](../cpp/com-error-class.md)
