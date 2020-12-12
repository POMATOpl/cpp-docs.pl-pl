---
description: 'Dowiedz się więcej na temat: _com_error:: Kodostrzeżenia'
title: _com_error::WCode
ms.date: 11/04/2016
f1_keywords:
- _com_error::WCode
helpviewer_keywords:
- WCode method [C++]
ms.assetid: f3b21852-f8ea-4e43-bff1-11c2d35454c4
ms.openlocfilehash: e3a19e5ae6c98cb38445e5eaa822474b2a852135
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97295734"
---
# <a name="_com_errorwcode"></a>_com_error::WCode

**Specyficzne dla firmy Microsoft**

Pobiera 16-bitowy kod błędu mapowany na hermetyzowaną wartość HRESULT.

## <a name="syntax"></a>Składnia

```
WORD WCode ( ) const throw( );
```

## <a name="return-value"></a>Wartość zwracana

Jeśli wynik HRESULT znajduje się w zakresie od 0x80040200 do 0x8004FFFF, `WCode` Metoda zwraca HRESULT minus 0x80040200; w przeciwnym razie zwraca zero.

## <a name="remarks"></a>Uwagi

`WCode`Metoda jest używana do cofania mapowania, które odbywa się w kodzie obsługi com. Otoka dla `dispinterface` właściwości lub metody wywołuje procedurę obsługi, która pakuje argumenty i wywołania `IDispatch::Invoke` . Po powrocie, jeśli zwracana jest niepowodzenie HRESULT of `DISP_E_EXCEPTION` , informacje o błędzie są pobierane ze `EXCEPINFO` struktury przesłanej do `IDispatch::Invoke` . Kod błędu może być 16-bitową wartością przechowywaną w `wCode` składowej `EXCEPINFO` struktury lub pełną 32-bitową wartością w `scode` składowej `EXCEPINFO` struktury. Jeśli zostanie zwrócona wartość 16-bitowa `wCode` , należy najpierw ją zamapować na 32-bitową awarię HRESULT.

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[_com_error::HRESULTToWCode](../cpp/com-error-hresulttowcode.md)<br/>
[_com_error::WCodeToHRESULT](../cpp/com-error-wcodetohresult.md)<br/>
[Klasa _com_error](../cpp/com-error-class.md)
