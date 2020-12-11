---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4049'
title: Ostrzeżenie kompilatora (poziom 1) C4049
ms.date: 11/04/2016
f1_keywords:
- C4049
helpviewer_keywords:
- C4049
ms.assetid: d11c1870-bcfc-4d71-8945-b87ec6ec3514
ms.openlocfilehash: b6de6fd816be8925dab553ff4dc5a062300b42e5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97160574"
---
# <a name="compiler-warning-level-1-c4049"></a>Ostrzeżenie kompilatora (poziom 1) C4049

ograniczenie kompilatora: Trwa kończenie emisji numeru wiersza

Plik zawiera więcej niż 16 777 215<sup>(2)</sup>wierszy źródłowych. Kompilator przerywa numerowanie o 16 777 215.

Dla kodu po wierszu 16 777 215:

- Obraz nie będzie zawierał żadnych informacji debugowania dla numerów wierszy.

- Niektóre funkcje diagnostyczne mogą być zgłaszane z nieprawidłowymi numerami wierszy.

- listy. asm (/FAs) mogą mieć niepoprawne numery wierszy.
