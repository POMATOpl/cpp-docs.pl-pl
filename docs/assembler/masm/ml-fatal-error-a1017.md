---
description: 'Dowiedz się więcej o: błąd krytyczny ML A1017'
title: Błąd krytyczny ML A1017
ms.date: 12/17/2019
ms.custom: error-reference
f1_keywords:
- A1017
helpviewer_keywords:
- A1017
ms.assetid: bef0b312-5431-4e5a-b637-c19919acf01b
ms.openlocfilehash: f15896e18721ef149cabd178bca433844a6edef5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97129444"
---
# <a name="ml-fatal-error-a1017"></a>Błąd krytyczny ML A1017

**Brakująca nazwa pliku źródłowego**

Nie można znaleźć pliku do nałączenia lub przekazania do konsolidatora.

Ten błąd jest generowany, gdy jest przyznawana opcjami wiersza polecenia ML bez określenia nazwy pliku, na którym ma działać. Aby złożyć pliki, które nie mają rozszerzenia ASM, użyj opcji wiersza polecenia **/Ta** .

Ten błąd może być również wygenerowany przez wywołanie ML bez parametrów, jeśli zmienna środowiskowa ML zawiera opcje wiersza polecenia.

## <a name="see-also"></a>Zobacz też

[Komunikaty o błędach ML](ml-error-messages.md)
