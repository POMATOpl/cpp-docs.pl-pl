---
description: 'Dowiedz się więcej na temat: współprocesora zmiennoprzecinkowe i konwencje wywoływania'
title: Koprocesor zmiennoprzecinkowy i konwencje wywoływania
ms.date: 11/04/2016
helpviewer_keywords:
- floating-point numbers [C++]
- floating-point coprocessor
ms.assetid: 3cc6615a-b308-4cf7-9570-83e192a832b3
ms.openlocfilehash: 2f68671783b8a556e787aa6637b9b5c2e5799485
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97242551"
---
# <a name="floating-point-coprocessor-and-calling-conventions"></a>Koprocesor zmiennoprzecinkowy i konwencje wywoływania

Jeśli piszesz procedury asemblera dla współprocesora zmiennoprzecinkowego, musisz zachować słowo kontrolne zmiennoprzecinkowe i wyczyścić stos współprocesora, chyba że zwracasz **`float`** lub **`double`** wartość (którą funkcja powinna zwrócić w St (0)).

## <a name="see-also"></a>Zobacz też

[Konwencje wywoływania](../cpp/calling-conventions.md)
