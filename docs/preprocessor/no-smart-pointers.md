---
description: 'Dowiedz się więcej na temat: no_smart_pointers Importowanie atrybutu'
title: no_smart_pointers atrybut importowania
ms.date: 08/29/2019
f1_keywords:
- no_smart_pointers
helpviewer_keywords:
- no_smart_pointers attribute
ms.assetid: d69dd71e-08a8-4446-a3d0-a062dc29cb17
ms.openlocfilehash: cf2299668a2e1b24cdf45069766466f448ee9d66
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333277"
---
# <a name="no_smart_pointers-import-attribute"></a>no_smart_pointers atrybut importowania

**Specyficzne dla języka C++**

Pomija Tworzenie inteligentnych wskaźników dla wszystkich interfejsów w bibliotece typów.

## <a name="syntax"></a>Składnia

> **#import** **no_smart_pointers** *biblioteki typów*

## <a name="remarks"></a>Uwagi

Domyślnie, gdy używasz `#import` , uzyskujesz deklarację inteligentnego wskaźnika dla wszystkich interfejsów w bibliotece typów. Te inteligentne wskaźniki są typu [_com_ptr_t](../cpp/com-ptr-t-class.md).

**ZAKOŃCZENIE specyficzne dla języka C++**

## <a name="see-also"></a>Zobacz też

[Atrybuty #import](../preprocessor/hash-import-attributes-cpp.md)\
[#import — dyrektywa](../preprocessor/hash-import-directive-cpp.md)
