---
description: 'Dowiedz się więcej na temat: błąd krytyczny C1092'
title: Błąd krytyczny C1092
ms.date: 11/04/2016
f1_keywords:
- C1092
helpviewer_keywords:
- C1092
ms.assetid: bcaa87f0-fbfc-4a33-844b-3b9f5d67f279
ms.openlocfilehash: b2a16991784b901202e5d51c0d256ad48305f55f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97145135"
---
# <a name="fatal-error-c1092"></a>Błąd krytyczny C1092

Edytuj i Kontynuuj nie obsługuje zmiany typów danych; wymagana kompilacja

Typ danych został zmieniony lub dodany od czasu ostatniej pomyślnej kompilacji.

- Polecenie Edytuj i Kontynuuj nie obsługuje zmian istniejących typów danych, w tym definicji klas, struktur lub wyliczeniowych. Musisz zatrzymać debugowanie i skompilować aplikację.

- Funkcja Edytuj i Kontynuuj nie obsługuje dodawania nowych typów danych, jeśli plik bazy danych programu, taki jak VC *x* 0. pdb (gdzie *x* jest wersją główną Visual C++ w użyciu), jest tylko do odczytu. Aby dodać typy danych, kompilator musi otworzyć plik. pdb w trybie zapisu.

### <a name="to-remove-this-error-without-ending-the-current-debug-session"></a>Aby usunąć ten błąd bez kończenia bieżącej sesji debugowania

1. Przed błędem Zmień typ danych z powrotem na stan.

1. Z menu **Debuguj** wybierz polecenie **Zastosuj zmiany kodu**.

### <a name="to-remove-this-error-without-changing-your-source-code"></a>Aby usunąć ten błąd bez zmiany kodu źródłowego

1. Z menu **Debuguj** wybierz polecenie **Zatrzymaj debugowanie**.

1. Z menu **kompilacja** wybierz polecenie **Kompiluj**.

Aby uzyskać więcej informacji, zobacz [obsługiwane zmiany kodu](/visualstudio/debugger/supported-code-changes-cpp).
