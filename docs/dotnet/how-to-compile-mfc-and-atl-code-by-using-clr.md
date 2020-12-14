---
description: 'Dowiedz się więcej o: Instrukcje: kompilowanie kodu MFC i ATL za pomocą/CLR'
title: 'Instrukcje: kompilowanie kodu MFC i ATL za pomocą polecenia-CLR'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- MFC [C++], interoperability
- ATL [C++], interoperability
- mixed assemblies [C++], MFC code
- mixed assemblies [C++], ATL code
- /clr compiler option [C++], compiling ATL and MFC code
- interoperability [C++], /clr compiler option
- regular MFC DLLs [C++], /clr compiler option
- interop [C++], /clr compiler option
- extension DLLs [C++], /clr compiler option
ms.assetid: 12464bec-33a4-482c-880a-c078de7f6ea5
ms.openlocfilehash: 67a861dac3b4c4b454f4fbde4a500c3677ce0e25
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97304496"
---
# <a name="how-to-compile-mfc-and-atl-code-by-using-clr"></a>Porady: kompilowanie kodu MFC i ATL za pomocą opcji /clr

W tym temacie omówiono sposób kompilowania istniejących programów MFC i ATL do celów środowiska uruchomieniowego języka wspólnego.

### <a name="to-compile-an-mfc-executable-or-regular-mfc-dll-by-using-clr"></a>Aby skompilować plik wykonywalny MFC lub zwykła Biblioteka MFC DLL przy użyciu/CLR

1. Kliknij prawym przyciskiem myszy projekt w **Eksplorator rozwiązań** a następnie kliknij polecenie **Właściwości**.

1. W oknie dialogowym **właściwości projektu** rozwiń węzeł obok pozycji **Właściwości konfiguracji** , a następnie wybierz pozycję **Ogólne**. W prawym okienku w obszarze **wartości domyślne projektu** Ustaw **obsługę środowiska uruchomieniowego języka wspólnego** na **obsługę środowiska uruchomieniowego CLR (/CLR)**.

   Upewnij się, że w tym samym okienku należy **używać** MFC, aby **używać MFC w udostępnionej bibliotece DLL**.

1. W obszarze **Właściwości konfiguracji** rozwiń węzeł obok pozycji **C/C++** i wybierz pozycję **Ogólne**. Upewnij się, że **Format informacji o debugowaniu** jest ustawiony na **program/Zi Database** (nie **/Zi**).

1. Wybierz węzeł **generowanie kodu** . Ustaw **opcję Włącz minimalną** ponowną kompilację na wartość **no (/GM-)**. Ustaw również **podstawowe testy środowiska uruchomieniowego** na **domyślne**.

1. W obszarze **Właściwości konfiguracji** wybierz pozycję **C/C++** , a następnie opcję **generowanie kodu**. Upewnij się, że **Biblioteka środowiska uruchomieniowego** jest ustawiona na **wielowątkowa Biblioteka DLL debugowania (/MDD)** lub **wielowątkowa Biblioteka DLL (/MD)**.

1. W stdafx. h Dodaj następujący wiersz.

    ```
    #using <System.Windows.Forms.dll>
    ```

### <a name="to-compile-an-mfc-extension-dll-by-using-clr"></a>Aby skompilować bibliotekę DLL rozszerzenia MFC przy użyciu/CLR

1. Wykonaj kroki opisane w sekcji "aby skompilować plik wykonywalny MFC lub zwykła Biblioteka MFC DLL przy użyciu/CLR".

1. W obszarze **Właściwości konfiguracji** rozwiń węzeł obok pozycji **C/C++** i wybierz opcję **prekompilowane nagłówki**. Ustaw **Utwórz/Użyj prekompilowanego nagłówka** , aby **nie używać prekompilowanych nagłówków**.

   Alternatywnie, w **Eksplorator rozwiązań**, kliknij prawym przyciskiem myszy stdafx. cpp, a następnie kliknij polecenie **Właściwości**. W obszarze **Właściwości konfiguracji** rozwiń węzeł obok pozycji **C/C++** i wybierz pozycję **Ogólne**. Ustaw **kompilację z obsługą środowiska uruchomieniowego języka wspólnego** na **Brak obsługi środowiska uruchomieniowego** CLR.

1. W przypadku pliku, który zawiera DllMain i wszystkie jego wywołania, w **Eksplorator rozwiązań** kliknij prawym przyciskiem myszy plik, a następnie kliknij polecenie **Właściwości**. W obszarze **Właściwości konfiguracji** rozwiń węzeł obok pozycji **C/C++** i wybierz pozycję **Ogólne**. W prawym okienku w obszarze **wartości domyślne projektu** ustaw opcję **Kompiluj z obsługą środowiska uruchomieniowego** CLR, aby **nie obsługiwać środowiska uruchomieniowego** CLR.

### <a name="to-compile-an-atl-executable-by-using-clr"></a>Aby skompilować plik wykonywalny ATL przy użyciu/CLR

1. W **Eksplorator rozwiązań** kliknij prawym przyciskiem myszy projekt, a następnie kliknij polecenie **Właściwości**.

1. W oknie dialogowym **właściwości projektu** rozwiń węzeł obok pozycji **Właściwości konfiguracji** , a następnie wybierz pozycję **Ogólne**. W prawym okienku w obszarze **wartości domyślne projektu** Ustaw **obsługę środowiska uruchomieniowego języka wspólnego** na **obsługę środowiska uruchomieniowego CLR (/CLR)**.

1. W obszarze **Właściwości konfiguracji** rozwiń węzeł obok pozycji **C/C++** i wybierz pozycję **Ogólne**. Upewnij się, że **Format informacji o debugowaniu** jest ustawiony na **program/Zi Database** (nie **/Zi**).

1. Wybierz węzeł **generowanie kodu** . Ustaw **opcję Włącz minimalną** ponowną kompilację na wartość **no (/GM-)**. Ustaw również **podstawowe testy środowiska uruchomieniowego** na **domyślne**.

1. W obszarze **Właściwości konfiguracji** wybierz pozycję **C/C++** , a następnie opcję **generowanie kodu**. Upewnij się, że **Biblioteka środowiska uruchomieniowego** jest ustawiona na **wielowątkowa Biblioteka DLL debugowania (/MDD)** lub **wielowątkowa Biblioteka DLL (/MD)**.

1. Dla każdego pliku wygenerowanego przez MIDL (pliki C) kliknij prawym przyciskiem myszy plik w **Eksplorator rozwiązań** a następnie kliknij polecenie **Właściwości**. W obszarze **Właściwości konfiguracji** rozwiń węzeł obok pozycji **C/C++** i wybierz pozycję **Ogólne**. Ustaw **kompilację z obsługą środowiska uruchomieniowego języka wspólnego** na **Brak obsługi środowiska uruchomieniowego** CLR.

### <a name="to-compile-an-atl-dll-by-using-clr"></a>Aby skompilować bibliotekę DLL ATL przy użyciu/CLR

1. Wykonaj kroki opisane w sekcji "aby skompilować plik wykonywalny ATL przy użyciu/CLR".

1. W obszarze **Właściwości konfiguracji** rozwiń węzeł obok pozycji **C/C++** i wybierz opcję **prekompilowane nagłówki**. Ustaw **Utwórz/Użyj prekompilowanego nagłówka** , aby **nie używać prekompilowanych nagłówków**.

   Alternatywnie, w **Eksplorator rozwiązań**, kliknij prawym przyciskiem myszy stdafx. cpp, a następnie kliknij polecenie **Właściwości**. W obszarze **Właściwości konfiguracji** rozwiń węzeł obok pozycji **C/C++** i wybierz pozycję **Ogólne**. Ustaw **kompilację z obsługą środowiska uruchomieniowego języka wspólnego** na **Brak obsługi środowiska uruchomieniowego** CLR.

1. W przypadku pliku, który zawiera DllMain i wszystkie jego wywołania, w **Eksplorator rozwiązań** kliknij prawym przyciskiem myszy plik, a następnie kliknij polecenie **Właściwości**. W obszarze **Właściwości konfiguracji** rozwiń węzeł obok pozycji **C/C++** i wybierz pozycję **Ogólne**. W prawym okienku w obszarze **wartości domyślne projektu** ustaw opcję **Kompiluj z obsługą środowiska uruchomieniowego** CLR, aby **nie obsługiwać środowiska uruchomieniowego** CLR.

## <a name="see-also"></a>Zobacz też

[Zestawy mieszane (natywne i zarządzane)](../dotnet/mixed-native-and-managed-assemblies.md)
