---
description: 'Dowiedz się więcej na temat: Błąd narzędzi konsolidatora LNK1112'
title: Błąd narzędzi konsolidatora LNK1112
ms.date: 11/04/2016
f1_keywords:
- LNK1112
helpviewer_keywords:
- LNK1112
ms.assetid: 425793d8-37e6-4072-9b6e-c3d4e9c12562
ms.openlocfilehash: ba0a34e07b0806f251c0b1237dc28ab5f8becbf4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97281382"
---
# <a name="linker-tools-error-lnk1112"></a>Błąd narzędzi konsolidatora LNK1112

> Typ maszyny modułu "*Type1*" powoduje konflikt z typem maszyny docelowej "*Type2*"

## <a name="remarks"></a>Uwagi

Pliki obiektów określone jako dane wejściowe zostały skompilowane dla różnych typów komputerów.

Na przykład, jeśli spróbujesz połączyć plik obiektu skompilowany z **/CLR** i plik obiektu skompilowany za pomocą **/CLR: Pure** (typ maszyny CEE), konsolidator generuje błąd LNK1112. **/CLR: Pure** kompilator Option jest przestarzały w programie visual Studio 2015 i nieobsługiwany w programie visual Studio 2017.

Podobnie w przypadku utworzenia jednego modułu z kompilatorem x64 i innego modułu z kompilatorem x86, a następnie nastąpi próba połączenia, konsolidator generuje LNK1112.

Możliwą przyczyną tego błędu jest to, że tworzysz aplikację 64-bitową, ale nie zainstalowano jednego z Visual C++ 64-bitowych kompilatorów. W takim przypadku konfiguracje 64-bitowe nie będą dostępne. Aby rozwiązać ten problem, uruchom Instalatora programu Visual Studio i zainstaluj brakujące składniki języka C++.

Ten błąd może również wystąpić, jeśli zmienisz **konfigurację aktywnego rozwiązania** w **Configuration Manager** a następnie spróbujesz skompilować projekt przed usunięciem pośrednich plików projektu. Aby rozwiązać ten problem, wybierz pozycję **Skompiluj ponownie rozwiązanie** z menu **kompilacja** . Możesz również wybrać opcję **Oczyść rozwiązanie** z menu **kompilacja** , a następnie skompilować rozwiązanie.

## <a name="see-also"></a>Zobacz też

- [Błędy i ostrzeżenia narzędzi konsolidatora](../../error-messages/tool-errors/linker-tools-errors-and-warnings.md)
