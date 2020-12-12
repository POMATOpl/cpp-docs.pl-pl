---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4651'
title: Ostrzeżenie kompilatora (poziom 1) C4651
ms.date: 11/04/2016
f1_keywords:
- C4651
helpviewer_keywords:
- C4651
ms.assetid: f1ea82aa-4dc1-4972-b55a-57fdb962f0dd
ms.openlocfilehash: 319d08799ed9494a5ef1d4d7b663fb8ec7b303e2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97318861"
---
# <a name="compiler-warning-level-1-c4651"></a>Ostrzeżenie kompilatora (poziom 1) C4651

określono element "Definition" dla prekompilowanego nagłówka, ale nie dla bieżącego kompilowania

Definicja została określona podczas generowania prekompilowanego nagłówka, ale nie w tej kompilacji.

Definicja będzie obowiązywać w prekompilowanym nagłówku, ale nie w pozostałej części kodu.

W przypadku skompilowania prekompilowanego nagłówka z/DSYMBOL, kompilator generuje to ostrzeżenie, jeśli kompilacja/Yu nie ma/DSYMBOL.  Dodanie/DSYMBOL do wiersza polecenia/Yu rozwiązuje to ostrzeżenie.
