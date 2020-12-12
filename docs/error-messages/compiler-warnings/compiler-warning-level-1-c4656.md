---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4656'
title: Ostrzeżenie kompilatora (poziom 1) C4656
ms.date: 11/04/2016
f1_keywords:
- C4656
helpviewer_keywords:
- C4656
ms.assetid: b5aaef74-2320-4345-a6ae-b813881a491c
ms.openlocfilehash: d902a7f7629f8bcbadab4ead240c06ebbf1aa33c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97318819"
---
# <a name="compiler-warning-level-1-c4656"></a>Ostrzeżenie kompilatora (poziom 1) C4656

"symbol": typ danych jest nowy lub został zmieniony od czasu ostatniej kompilacji lub został inaczej zdefiniowany w innym miejscu

Dodano lub Zmieniono typ danych, co sprawia, że nowy kod źródłowy od momentu ostatniej pomyślnej kompilacji. Edytuj i Kontynuuj nie obsługuje zmian istniejących typów danych.

To ostrzeżenie będzie zawsze następuje po [błędzie krytycznym C1092](../../error-messages/compiler-errors-1/fatal-error-c1092.md). Aby uzyskać więcej informacji, zobacz [obsługiwane zmiany kodu](/visualstudio/debugger/supported-code-changes-cpp).

### <a name="to-remove-this-warning-without-ending-the-current-debug-session"></a>Aby usunąć to ostrzeżenie bez kończenia bieżącej sesji debugowania

1. Przed błędem Zmień typ danych z powrotem na stan.

1. Z menu **Debuguj** wybierz polecenie **Zastosuj zmiany kodu**.

### <a name="to-remove-this-error-without-changing-your-source-code"></a>Aby usunąć ten błąd bez zmiany kodu źródłowego

1. Z menu **Debuguj** wybierz polecenie **Zatrzymaj debugowanie**.

1. Z menu **kompilacja** wybierz polecenie **Kompiluj**.
