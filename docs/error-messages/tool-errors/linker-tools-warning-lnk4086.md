---
description: 'Dowiedz się więcej o: LNK4086 narzędzi KONSOLIDATORA ostrzeżenia narzędzi konsolidatora'
title: Ostrzeżenie LNK4086 narzędzi konsolidatora
ms.date: 11/04/2016
f1_keywords:
- LNK4086
helpviewer_keywords:
- LNK4086
ms.assetid: ea1eecbb-ba2c-41bb-9a4f-fa0808a4b92d
ms.openlocfilehash: f19138d895706579cff13bd1d43b9a64ccaa5044
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97210117"
---
# <a name="linker-tools-warning-lnk4086"></a>Ostrzeżenie LNK4086 narzędzi konsolidatora

punkt wejścia "Function" nie jest __stdcall z "liczbą" bajtów argumentów; nie można uruchomić obrazu

Punkt wejścia dla biblioteki DLL musi być **`__stdcall`** . Należy ponownie skompilować funkcję przy użyciu opcji [/GZ](../../build/reference/gd-gr-gv-gz-calling-convention.md) lub określić **`__stdcall`** lub WINAPI podczas definiowania funkcji.
