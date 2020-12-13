---
description: 'Dowiedz się więcej na temat: no_dual_interfaces Importowanie atrybutu'
title: no_dual_interfaces atrybut importowania
ms.date: 08/29/2019
f1_keywords:
- no_dual_interfaces
helpviewer_keywords:
- no_dual_interfaces attribute
ms.assetid: 9acd5d9d-4a49-4cdc-9470-73a2c23cf512
ms.openlocfilehash: 1c3010b252ac71e38312fa193520938fbb4d681a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333341"
---
# <a name="no_dual_interfaces-import-attribute"></a>no_dual_interfaces atrybut importowania

**Specyficzne dla języka C++**

Zmienia sposób, w jaki kompilator generuje funkcje otoki dla dwóch metod interfejsu.

## <a name="syntax"></a>Składnia

> **#import** **no_dual_interfaces** *biblioteki typów*

## <a name="remarks"></a>Uwagi

Zwykle otoka wywołuje metodę za pomocą tabeli funkcji wirtualnych dla interfejsu. W przypadku **no_dual_interfaces**, otoka wywołuje wywołanie `IDispatch::Invoke` metody.

**ZAKOŃCZENIE specyficzne dla języka C++**

## <a name="see-also"></a>Zobacz też

[Atrybuty #import](../preprocessor/hash-import-attributes-cpp.md)\
[#import — dyrektywa](../preprocessor/hash-import-directive-cpp.md)
