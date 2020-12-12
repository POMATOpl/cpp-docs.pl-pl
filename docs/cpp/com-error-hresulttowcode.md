---
description: 'Dowiedz się więcej na temat: _com_error:: HRESULTToWCode'
title: _com_error::HRESULTToWCode
ms.date: 11/04/2016
f1_keywords:
- _com_error::HRESULTToWCode
helpviewer_keywords:
- HRESULTToWCode method [C++]
ms.assetid: ff3789f5-1047-41a0-b7e3-86dd8f638dba
ms.openlocfilehash: 1bbf62be42d4e34a2ef73493f0449c2ffbaf0646
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97295837"
---
# <a name="_com_errorhresulttowcode"></a>_com_error::HRESULTToWCode

**Specyficzne dla firmy Microsoft**

Maps 32-bit HRESULT do 16-bitowego `wCode` .

## <a name="syntax"></a>Składnia

```
static WORD HRESULTToWCode(
   HRESULT hr
) throw( );
```

#### <a name="parameters"></a>Parametry

*godz.*<br/>
32-bitowy wynik HRESULT ma być mapowany do 16-bitowego `wCode` .

## <a name="return-value"></a>Wartość zwracana

16-bitowe `wCode` zamapowane z 32-BITOWEJ HRESULT.

## <a name="remarks"></a>Uwagi

Aby uzyskać więcej informacji, zobacz [_com_error:: kodostrzeżenia](../cpp/com-error-wcode.md) .

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[_com_error::WCode](../cpp/com-error-wcode.md)<br/>
[_com_error::WCodeToHRESULT](../cpp/com-error-wcodetohresult.md)<br/>
[Klasa _com_error](../cpp/com-error-class.md)
