---
description: 'Dowiedz się więcej na temat: _bstr_t:: GetBSTR'
title: _bstr_t::GetBSTR
ms.date: 11/04/2016
f1_keywords:
- _bstr_t::GetBSTR
helpviewer_keywords:
- GetBSTR method [C++]
ms.assetid: 0c62ff16-4433-4183-a03c-d5a0a9b731ef
ms.openlocfilehash: ced985bb5123d86ff119279fc49a2b4d181ba8b3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97229304"
---
# <a name="_bstr_tgetbstr"></a>_bstr_t::GetBSTR

**Specyficzne dla firmy Microsoft**

Wskazuje początek `BSTR` opakowany przez `_bstr_t` .

## <a name="syntax"></a>Składnia

```
BSTR& GetBSTR( );
```

## <a name="return-value"></a>Wartość zwracana

Początek `BSTR` opakowany przez `_bstr_t` .

## <a name="remarks"></a>Uwagi

**GetBSTR** ma wpływ na wszystkie `_bstr_t` obiekty, które współużytkują `BSTR` . Więcej niż jeden `_bstr_t` może współdzielić `BSTR` przez użycie konstruktora kopiującego i **operatora =**.

## <a name="example"></a>Przykład

Zobacz [_bstr_t:: Assign](../cpp/bstr-t-assign.md) dla przykładu przy użyciu elementu **GetBSTR**.

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Klasa _bstr_t](../cpp/bstr-t-class.md)
