---
description: 'Dowiedz się więcej na temat: błąd krytyczny kompilatora zasobów kompilatora zasobów RC1052'
title: Błąd krytyczny kompilatora zasobów RC1052
ms.date: 11/04/2016
f1_keywords:
- RC1052
helpviewer_keywords:
- RC1052
ms.assetid: 59803673-492b-44fa-80fa-df93b8aaf9fb
ms.openlocfilehash: 41ef30cfde7d463337b1747b3f6141866e39e3be
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97255083"
---
# <a name="resource-compiler-fatal-error-rc1052"></a>Błąd krytyczny kompilatora zasobów RC1052

ograniczenie kompilatora: bloki #if lub #ifdef zagnieżdżone zbyt głęboko

Program przekroczył maksymalną dozwoloną liczbę poziomów zagnieżdżenia dla `#if` `#ifdef` dyrektyw i.

Przyczyną tego błędu może być dołączenie plików, które używają tych dyrektyw preprocesora.

Aby rozwiązać ten problem, zmniejsz liczbę zagnieżdżonych `#if` i `#ifdef` dyrektyw w pliku zasobów. Jeśli problem jest spowodowany przez pliki nagłówkowe, które są zawarte w pliku zasobów, zmniejsz liczbę zagnieżdżonych `#if` i `#ifdef` dyrektyw w plikach nagłówkowych. Jeśli nie jest to możliwe, rozważ utworzenie i uwzględnienie nowego pliku nagłówkowego w pliku zasobów, uruchamiając preprocesor w istniejących plikach nagłówkowych. Aby uzyskać więcej informacji, zobacz opcja kompilatora [/p (preprocess to File)](../../build/reference/p-preprocess-to-a-file.md) .
