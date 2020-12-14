---
description: 'Dowiedz się więcej na temat: błąd krytyczny C1002'
title: Błąd krytyczny C1002
ms.date: 11/04/2016
f1_keywords:
- C1002
helpviewer_keywords:
- C1002
ms.assetid: bd6d274a-c7b4-43af-8bf2-23c5e442aa22
ms.openlocfilehash: edd4ffbd6ce4c8a7f70640619d8dc52775dd0195
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97262714"
---
# <a name="fatal-error-c1002"></a>Błąd krytyczny C1002

Kompilator nie ma miejsca na stercie w przebiegu 2

Kompilator wypełnił ilość pamięci dynamicznej podczas jej drugiego przebiegu, prawdopodobnie z powodu programu z zbyt dużą liczbą symboli lub złożonych wyrażeń.

### <a name="to-fix-by-using-the-following-possible-solutions"></a>Aby rozwiązać ten problem, można użyć następujących rozwiązań

1. Podziel plik źródłowy na kilka mniejszych plików.

1. Podział wyrażeń na mniejsze podwyrażenia.

1. Usuń inne programy lub sterowniki zużywające pamięć.
