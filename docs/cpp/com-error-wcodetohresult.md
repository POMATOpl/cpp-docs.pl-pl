---
description: 'Dowiedz się więcej na temat: _com_error:: WCodeToHRESULT'
title: _com_error::WCodeToHRESULT
ms.date: 11/04/2016
f1_keywords:
- _com_error::WCodeToHRESULT
helpviewer_keywords:
- WCodeToHRESULT method [C++]
ms.assetid: 0ec43a4b-ca91-42d5-b270-3fde9c8412ea
ms.openlocfilehash: 9925c34f14f0685cb563e37a8cae0970911f009c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97295721"
---
# <a name="_com_errorwcodetohresult"></a>_com_error::WCodeToHRESULT

**Specyficzne dla firmy Microsoft**

Maps 16-bitowy *kodostrzeżenia* do 32-bitowy wynik HRESULT.

## <a name="syntax"></a>Składnia

```
static HRESULT WCodeToHRESULT(
   WORD wCode
) throw( );
```

#### <a name="parameters"></a>Parametry

*Kodostrzeżenia*<br/>
16-bitowa *kodostrzeżenia* do zmapowania na 32-bitowy wynik HRESULT.

## <a name="return-value"></a>Wartość zwracana

32-bitowe HRESULT zamapowane z 16-bitowej *kodostrzeżenia*.

## <a name="remarks"></a>Uwagi

Zobacz funkcję członkowską [kodostrzeżenia](../cpp/com-error-wcode.md) .

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[_com_error::WCode](../cpp/com-error-wcode.md)<br/>
[_com_error::HRESULTToWCode](../cpp/com-error-hresulttowcode.md)<br/>
[Klasa _com_error](../cpp/com-error-class.md)
