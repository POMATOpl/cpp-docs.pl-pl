---
description: 'Dowiedz się więcej o: Translation: Diagnostics'
title: 'Translacja: Diagnostyka'
ms.date: 11/04/2016
ms.assetid: 3730ca7c-0147-452d-bd4a-6a1e97e9793e
ms.openlocfilehash: 09fc44dea8d51dbb267d402745c8c2a095b969d8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97243058"
---
# <a name="translation-diagnostics"></a>Translacja: Diagnostyka

**2.1.1.3 ANSI** Jak jest identyfikowana Diagnostyka

Microsoft C tworzy komunikaty o błędach w postaci:

> *filename* **(** *numer wiersza* **):** *komunikat* o <em>numerze</em> *diagnostyki* **C**

gdzie *filename* to nazwa pliku źródłowego, w którym wystąpił błąd; *numer wiersza* to numer wiersza, w którym Kompilator wykrył błąd; *Diagnostyka* to "Error" lub "Warning"; *Liczba* jest unikatową cyfrą czterocyfrową (poprzedzoną znakiem **C**, jak pokazano w składni), która identyfikuje błąd lub ostrzeżenie; *komunikat* jest komunikatem wyjaśniającym.

## <a name="see-also"></a>Zobacz też

[Zachowanie zdefiniowane w implementacji](../c-language/implementation-defined-behavior.md)
