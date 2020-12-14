---
description: 'Dowiedz się więcej na temat: błąd ewaluatora wyrażeń CXX0039'
title: Błąd CXX0039 programu Expression Evaluator
ms.date: 11/04/2016
f1_keywords:
- CXX0039
helpviewer_keywords:
- CXX0039
- CAN0039
ms.assetid: 8bf698d2-e015-4595-944f-72b81aa43d22
ms.openlocfilehash: 19d8e01e3eb8f599319988a8aa9fc0bf401701fc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97244735"
---
# <a name="expression-evaluator-error-cxx0039"></a>Błąd CXX0039 programu Expression Evaluator

symbol jest niejednoznaczny

Ewaluatora wyrażeń języka C nie może określić, które wystąpienie symbolu ma być używane w wyrażeniu. Symbol występuje więcej niż jeden raz w drzewie dziedziczenia.

`::`Aby jawnie określić wystąpienie do użycia w wyrażeniu, należy użyć operatora rozpoznawania zakresu ().

Ten błąd jest identyczny z CAN0039.
