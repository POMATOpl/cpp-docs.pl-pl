---
description: 'Dowiedz się więcej na temat: błąd kompilacji projektu PRJ0009'
title: Błąd PRJ0009 kompilacji projektu
ms.date: 11/04/2016
f1_keywords:
- PRJ0009
helpviewer_keywords:
- PRJ0009
ms.assetid: 89291778-cda4-495d-983f-ddcc06dfc98b
ms.openlocfilehash: 28a7a9ce1a4fa5f1b5b95ba208739b7172f0ac6d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97343889"
---
# <a name="project-build-error-prj0009"></a>Błąd PRJ0009 kompilacji projektu

Nie można otworzyć dziennika kompilacji do zapisu.

**Upewnij się, że plik nie jest otwarty przez inny proces i nie jest chroniony przed zapisem.**

Po ustawieniu właściwości **Rejestrowanie kompilacji** na **wartość tak** i wykonaniu kompilacji lub odbudowy, Visual C++ nie mógł otworzyć dziennika kompilacji w trybie wyłączności.

Sprawdź ustawienia **rejestrowania kompilacji** , otwierając okno dialogowe **Opcje** (w menu **Narzędzia** kliknij polecenie **Opcje** ), a następnie wybierz opcję **kompilacja VC + +** w folderze **projekty** . Plik kompilacji jest nazywany BuildLog.htm i jest zapisywana w katalogu pośrednim $ (IntDir).

Możliwe przyczyny tego błędu:

- Są uruchamiane dwa procesy Visual C++ i podjęto próbę skompilowania tej samej konfiguracji tego samego projektu jednocześnie.

- Plik dziennika kompilacji jest otwierany w procesie, który blokuje plik.

- Użytkownik nie ma uprawnienia do tworzenia pliku.

- Bieżący użytkownik nie ma dostępu do zapisu do pliku BuildLog.htm.
