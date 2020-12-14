---
description: 'Dowiedz się więcej na temat: testowanie błędów wyodrębniania'
title: Testing for Extraction Errors
ms.date: 11/04/2016
helpviewer_keywords:
- extraction errors
ms.assetid: 6a681028-adba-4557-8f7b-f137932905f8
ms.openlocfilehash: c4a9b5c1ffe4f78718563b33e39012272cfb8042
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97259360"
---
# <a name="testing-for-extraction-errors"></a>Testing for Extraction Errors

Funkcje przetwarzania błędów wyjścia, omówione w [funkcjach przetwarzania błędów](../standard-library/output-file-stream-member-functions.md), mają zastosowanie do strumieni wejściowych. Testowanie błędów podczas wyodrębniania jest ważne. Należy wziąć pod uwagę następujące instrukcje:

```cpp
cin>> n;
```

Jeśli `n` jest to liczba całkowita ze znakiem, wartość większa niż 32 767 (maksymalna dopuszczalna wartość lub MAX_INT) ustawia `fail` bit strumienia, a `cin` obiekt stanie się bezużyteczny. Wszystkie kolejne operacje wyodrębniania powodują natychmiastowe zwrócenie bez żadnej wartości.

## <a name="see-also"></a>Zobacz też

[Strumienie wejściowe](../standard-library/input-streams.md)
