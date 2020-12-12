---
description: 'Dowiedz się więcej na temat: Tworzenie projektu (samouczek ATL, część 1)'
title: Tworzenie projektu (ALT — Samouczek, część 1)
ms.custom: get-started-article
ms.date: 08/19/2019
ms.assetid: f6b727d1-390a-4b27-b82f-daadcd9fc059
ms.openlocfilehash: f594294b5d97222791a3f3f43c147fae9514889b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97148089"
---
# <a name="creating-the-project-atl-tutorial-part-1"></a>Tworzenie projektu (ALT — Samouczek, część 1)

Ten samouczek przeprowadzi Cię krok po kroku przez Projekt ATL nienależący do atrybutu, który tworzy obiekt ActiveX, który wyświetla wielokąt. Obiekt zawiera opcje umożliwiające użytkownikowi zmianę liczby stron, które tworzą Wielokąt, i kodu, aby odświeżyć ekran.

> [!NOTE]
> W tym samouczku jest tworzony ten sam kod źródłowy, który jest przykładem wielokąta. Jeśli chcesz, aby nie wprowadzać kodu źródłowego ręcznie, możesz pobrać go z [przykładowej abstrakcyjnej próbki wielokąta](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/Controls/Polygon). Następnie można odwoływać się do kodu źródłowego Wielokąt podczas pracy w samouczku lub użyć go do sprawdzenia błędów w projekcie.
> Aby skompilować, Otwórz plik *PCH. h* (*stdafx. h* w programie Visual Studio 2017 i starsze) i Zastąp:
>
> ```
> #ifndef WINVER
> #define WINVER 0x0400
> #endif
> ```
>
> with
>
> ```
> #ifndef WINVER
> #define WINVER 0x0500
> #define _WIN32_WINNT 0x0500
> #endif
> ```
>
> Kompilator nadal będzie `regsvr32` pokazywać nieprawidłową pracę, ale nadal powinien być utworzony i dostępny dla biblioteki DLL.

### <a name="to-create-the-initial-atl-project-using-the-atl-project-wizard"></a>Aby utworzyć początkowy Projekt ATL przy użyciu Kreatora projektu ATL

1. W programie Visual Studio 2017 i starszych: **plik**  >  **Nowy**  >  **projekt**. Otwórz kartę **Visual C++** i wybierz pozycję **MFC/ATL**. Wybierz **Projekt ATL**.

   W programie Visual Studio 2019: wybierz pozycję **plik**  >  **Nowy**  >  **projekt**, wpisz "ATL" w polu wyszukiwania, a następnie wybierz pozycję **Projekt ATL**.

1. Umożliwia wpisanie *wielokąta* jako nazwy projektu.

    Lokalizacja dla kodu źródłowego zwykle będzie domyślnie \Users \\ \<username> \source\repos, a nowy folder zostanie utworzony automatycznie.

1. W programie Visual Studio 2019 zaakceptuj wartości domyślne i kliknij przycisk **OK**.
   W programie Visual Studio 2017 kliknij przycisk **OK** , aby otworzyć kreatora **Projekt ATL** . Kliknij pozycję **Ustawienia aplikacji** , aby wyświetlić dostępne opcje. Ponieważ ten projekt tworzy formant i formant musi być serwerem działającym w procesie, pozostaw **Typ aplikacji** jako bibliotekę DLL. Kliknij przycisk **OK**.

Program Visual Studio utworzy projekt, generując kilka plików. Można wyświetlić te pliki w **Eksplorator rozwiązań** przez powiększanie `Polygon` obiektu. Poniżej znajdują się pliki.

::: moniker range="<=msvc-150"

|Plik|Opis|
|----------|-----------------|
|Wielokąt. cpp|Zawiera implementację `DllMain` , `DllCanUnloadNow` ,, `DllGetClassObject` `DllRegisterServer` i `DllUnregisterServer` . Zawiera również mapę obiektów, która jest listą obiektów ATL w projekcie. Jest to początkowo puste.|
|Wielokąt. def|Ten plik definicji modułu zawiera konsolidator z informacjami o eksportach wymaganych przez bibliotekę DLL.|
|Wielokąt. idl|Plik języka definicji interfejsu, który opisuje interfejsy specyficzne dla obiektów.|
|Wielokąt. RGS|Ten skrypt rejestru zawiera informacje dotyczące rejestrowania biblioteki DLL programu.|
|Wielokąt. RC|Plik zasobu, który początkowo zawiera informacje o wersji i ciąg zawierający nazwę projektu.|
|Resource.h|Plik nagłówkowy pliku zasobów.|
|Polygonps. def|Ten plik definicji modułu udostępnia konsolidator z informacjami o eksportach wymaganych przez serwer proxy i Kod zastępczy obsługujący wywołania w apartamentach.|
|stdafx.cpp|Plik, który będzie `#include` *stdafx. h*.|
|stdafx.h|Plik, który będzie `#include` i prekompilował pliki nagłówkowe ATL.|

::: moniker-end

::: moniker range=">=msvc-160"

|Plik|Opis|
|----------|-----------------|
|Wielokąt. cpp|Zawiera implementację `DllMain` , `DllCanUnloadNow` ,, `DllGetClassObject` `DllRegisterServer` i `DllUnregisterServer` . Zawiera również mapę obiektów, która jest listą obiektów ATL w projekcie. Jest to początkowo puste.|
|Wielokąt. def|Ten plik definicji modułu zawiera konsolidator z informacjami o eksportach wymaganych przez bibliotekę DLL.|
|Wielokąt. idl|Plik języka definicji interfejsu, który opisuje interfejsy specyficzne dla obiektów.|
|Wielokąt. RGS|Ten skrypt rejestru zawiera informacje dotyczące rejestrowania biblioteki DLL programu.|
|Wielokąt. RC|Plik zasobu, który początkowo zawiera informacje o wersji i ciąg zawierający nazwę projektu.|
|Resource.h|Plik nagłówkowy pliku zasobów.|
|Polygonps. def|Ten plik definicji modułu udostępnia konsolidator z informacjami o eksportach wymaganych przez serwer proxy i Kod zastępczy obsługujący wywołania w apartamentach.|
|PCH. cpp|Plik, który będzie `#include` *PCH. h*.|
|PCH. h|Plik, który będzie `#include` i prekompilował pliki nagłówkowe ATL.|

::: moniker-end

1. W **Eksplorator rozwiązań** kliknij prawym przyciskiem myszy `Polygon` projekt.

1. W menu skrótów kliknij polecenie **Właściwości**.

1. Kliknij **konsolidator**. Zmień opcję **na-UserRedirection** na **wartość tak**.

1. Kliknij przycisk **OK**.

W następnym kroku dodasz kontrolkę do projektu.

[Do kroku 2](../atl/adding-a-control-atl-tutorial-part-2.md)

## <a name="see-also"></a>Zobacz też

[Samouczek](../atl/active-template-library-atl-tutorial.md)
