---
description: 'Dowiedz się więcej na temat: _bstr_t:: GetAddress'
title: _bstr_t::GetAddress
ms.date: 11/04/2016
f1_keywords:
- _bstr_t::GetAddress
helpviewer_keywords:
- GetAddress method [C++]
ms.assetid: 09bc9180-867e-4ee5-b22a-8339dc663142
ms.openlocfilehash: afb877a6f1b4cfcfb6fe08b36168af745d733b85
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97229317"
---
# <a name="_bstr_tgetaddress"></a>_bstr_t::GetAddress

**Specyficzne dla firmy Microsoft**

Zwalnia wszystkie istniejące ciągi i zwraca adres nowo przydzielony ciąg.

## <a name="syntax"></a>Składnia

```
BSTR* GetAddress( );
```

## <a name="return-value"></a>Wartość zwracana

Wskaźnik do `BSTR` opakowany przez `_bstr_t` .

## <a name="remarks"></a>Uwagi

**GetAddress** ma wpływ na wszystkie `_bstr_t` obiekty, które współużytkują `BSTR` . Więcej niż jeden `_bstr_t` może współdzielić `BSTR` przez użycie konstruktora kopiującego i **operatora =**.

## <a name="example"></a>Przykład

Zobacz [_bstr_t:: Assign](../cpp/bstr-t-assign.md) dla przykładu przy użyciu **GetAddress**.

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Klasa _bstr_t](../cpp/bstr-t-class.md)
