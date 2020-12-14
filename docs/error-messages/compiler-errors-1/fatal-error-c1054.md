---
description: 'Dowiedz się więcej na temat: błąd krytyczny C1054'
title: Błąd krytyczny C1054
ms.date: 11/04/2016
f1_keywords:
- C1054
helpviewer_keywords:
- C1054
ms.assetid: 9cfb7307-b22a-4418-b7c0-2621b0ab5b1b
ms.openlocfilehash: 1bfe8718fcb0d3edb172f0f5a89bb2f479e56137
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97251664"
---
# <a name="fatal-error-c1054"></a>Błąd krytyczny C1054

ograniczenie kompilatora: inicjatory są zagnieżdżone zbyt głęboko

Kod przekracza limit zagnieżdżenia dla inicjatorów (10-15 poziomów, w zależności od kombinacji typów, które są inicjowane).

### <a name="to-fix-by-using-the-following-possible-solutions"></a>Aby rozwiązać ten problem, można użyć następujących rozwiązań

1. Uprość typy danych, które są inicjowane w celu zmniejszenia zagnieżdżenia.

1. Inicjuj zmienne w oddzielnych instrukcjach po deklaracji.
