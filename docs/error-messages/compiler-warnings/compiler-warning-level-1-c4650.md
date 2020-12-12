---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4650'
title: Ostrzeżenie kompilatora (poziom 1) C4650
ms.date: 11/04/2016
f1_keywords:
- C4650
helpviewer_keywords:
- C4650
ms.assetid: 3190b3e3-dcd6-4846-939b-f900ab652b2a
ms.openlocfilehash: 8af31cb6eaacc8b090103a2a5f622eb7aff275a4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97318887"
---
# <a name="compiler-warning-level-1-c4650"></a>Ostrzeżenie kompilatora (poziom 1) C4650

informacje debugowania nie są w prekompilowanym nagłówku; dostępne są tylko symbole globalne z nagłówka

Prekompilowany plik nagłówkowy nie został skompilowany przy użyciu symbolicznych informacji debugowania firmy Microsoft.

W przypadku połączenia utworzony plik wykonywalny lub biblioteka dołączany dynamicznie nie będzie zawierał informacji o debugowaniu dla symboli lokalnych zawartych w prekompilowanym nagłówku.

To ostrzeżenie można uniknąć przez ponowne skompilowanie prekompilowanego pliku nagłówkowego za pomocą opcji wiersza polecenia [/Zi](../../build/reference/z7-zi-zi-debug-information-format.md) .
