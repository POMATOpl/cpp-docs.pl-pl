---
description: 'Dowiedz się więcej na temat: raw_dispinterfaces Importowanie atrybutu'
title: raw_dispinterfaces atrybut importowania
ms.date: 08/29/2019
f1_keywords:
- raw_dispinterfaces
helpviewer_keywords:
- raw_dispinterfaces attribute
ms.assetid: f762864d-29bf-445b-825a-ba7b29a95409
ms.openlocfilehash: 447f76bdee16d2719c02ad4a73883f8f176f2584
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97202018"
---
# <a name="raw_dispinterfaces-import-attribute"></a>raw_dispinterfaces atrybut importowania

**Specyficzne dla języka C++**

Instruuje kompilator, aby generował funkcje otoki niskiego poziomu dla metod dispinterface oraz dla właściwości, które wywołują `IDispatch::Invoke` i zwracają kod błędu HRESULT.

## <a name="syntax"></a>Składnia

> **#import** **raw_dispinterfaces** *biblioteki typów*

## <a name="remarks"></a>Uwagi

Jeśli ten atrybut nie jest określony, generowane są tylko otoki wysokiego poziomu, które generują wyjątki C++ w przypadku niepowodzenia.

**ZAKOŃCZENIE specyficzne dla języka C++**

## <a name="see-also"></a>Zobacz też

[Atrybuty #import](../preprocessor/hash-import-attributes-cpp.md)\
[#import — dyrektywa](../preprocessor/hash-import-directive-cpp.md)
