---
description: 'Dowiedz się więcej na temat: _com_error:: Error'
title: _com_error::Error
ms.date: 11/04/2016
f1_keywords:
- _com_error::Error
- Error
helpviewer_keywords:
- Error method [C++]
ms.assetid: b53a15fd-198e-4276-afcd-13439c4807f7
ms.openlocfilehash: 25dd78caeada9e7606bc26f241126b0d0f510f4c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97318198"
---
# <a name="_com_errorerror"></a>_com_error::Error

**Specyficzne dla firmy Microsoft**

Pobiera wartość HRESULT przekazaną do konstruktora.

## <a name="syntax"></a>Składnia

```
HRESULT Error( ) const throw( );
```

## <a name="return-value"></a>Wartość zwracana

Nieprzetworzony element HRESULT przeszedł do konstruktora.

## <a name="remarks"></a>Uwagi

Pobiera hermetyzowany element HRESULT w `_com_error` obiekcie.

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Klasa _com_error](../cpp/com-error-class.md)
