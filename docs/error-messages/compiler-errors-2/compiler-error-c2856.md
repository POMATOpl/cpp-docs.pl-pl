---
description: 'Dowiedz się więcej o: błąd kompilatora C2856'
title: Błąd kompilatora C2856
ms.date: 11/04/2016
f1_keywords:
- C2856
helpviewer_keywords:
- C2856
ms.assetid: fe616c51-124e-49e3-9dd8-883ec1660680
ms.openlocfilehash: 8594bc5902e13967084aa3695131d616a4cf04da
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337553"
---
# <a name="compiler-error-c2856"></a>Błąd kompilatora C2856

\#pragma hdrstop nie może znajdować się wewnątrz bloku #if

`hdrstop`Dyrektywy pragma nie można umieścić wewnątrz treści bloku kompilacji warunkowej.

Przenieś `#pragma hdrstop` instrukcję do obszaru, który nie znajduje się w `#if/#endif` bloku.
