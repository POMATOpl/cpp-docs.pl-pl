---
description: 'Dowiedz się więcej o: zużywaniu bibliotek i składników'
title: Zużywanie bibliotek i składników w projektach C++
ms.date: 12/18/2020
f1_keywords:
- VC.Project.References
helpviewer_keywords:
- Add References Dialog Box (C++)
- .NET Framework (C++), Add References Dialog Box
ms.assetid: 12b8f571-0f21-40b3-9404-5318a57e9cb5
ms.openlocfilehash: c8e7cb41fad6a974ac677228d884a31e4fa92ce1
ms.sourcegitcommit: 2b2c3fa9244e31db35ea33554dea0efcab490f3c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/18/2020
ms.locfileid: "97682456"
---
# <a name="consuming-libraries-and-components"></a>Zużywanie bibliotek i składników

Projekty języka C++ często muszą wywoływać funkcje lub uzyskiwać dostęp do danych w pliku binarnym, takim jak Biblioteka statyczna (pliki LIB), DLL, składnik środowisko wykonawcze systemu Windows, składnik COM lub zestaw .NET. W takich przypadkach trzeba skonfigurować projekt, aby mógł on znaleźć ten plik binarny w czasie kompilacji. Konkretne kroki zależą od typu projektu, typu pliku binarnego oraz tego, czy plik binarny jest skompilowany w tym samym rozwiązaniu co projekt.

## <a name="consuming-libraries-downloaded-via-vcpkg"></a>Wykorzystywanie bibliotek pobranych za pośrednictwem vcpkg

Aby korzystać z biblioteki pobranej przy użyciu Menedżera pakietów **vcpkg** , można zignorować poniższe instrukcje. Aby uzyskać więcej informacji [, zobacz vcpkg: Menedżer pakietów języka C++ dla systemów Windows, Linux i macOS](vcpkg.md) .

## <a name="consuming-static-libraries"></a>Używanie bibliotek statycznych

Jeśli projekt biblioteki statycznej zostanie skompilowany w tym samym rozwiązaniu:

1. #<a name="include-the-header-files-for-the-static-library-using-quotation-marks-in-a-typical-solution-the-path-starts-with-library-project-name-intellisense-will-help-you-find-it"></a>Uwzględnij pliki nagłówkowe biblioteki statycznej przy użyciu znaków cudzysłowu. W typowym rozwiązaniu ścieżka zaczyna się od `../<library project name>` . Technologia IntelliSense pomoże jej znaleźć.
2. Dodaj odwołanie do projektu biblioteki statycznej. Kliknij prawym przyciskiem myszy pozycję **odwołania** w węźle projektu aplikacji w **Eksplorator rozwiązań** i wybierz polecenie **Dodaj odwołanie**.

Jeśli Biblioteka statyczna nie jest częścią rozwiązania:

1. Kliknij prawym przyciskiem myszy węzeł projektu aplikacji w **Eksplorator rozwiązań** a następnie wybierz polecenie **Właściwości**.
2. Na stronie właściwości **Katalogi VC + +** Dodaj ścieżkę do katalogu, który zawiera plik lib do **ścieżki biblioteki**. Następnie dodaj ścieżkę do plików nagłówkowych biblioteki w celu **uwzględnienia katalogów**.  
3. Na stronie właściwości **dane wejściowe > konsolidatora** Dodaj nazwę pliku lib do **dodatkowych zależności**.

## <a name="dynamic-link-libraries"></a>Biblioteki dołączane dynamicznie

Jeśli biblioteka DLL jest skompilowana jako część tego samego rozwiązania co aplikacja, wykonaj te same czynności co w przypadku biblioteki statycznej.

Jeśli biblioteka DLL nie jest częścią rozwiązania aplikacji, wymagany jest: plik DLL, nagłówki zawierające prototypy dla eksportowanych funkcji i klas oraz plik LIB, który zawiera niezbędne informacje dotyczące łączenia.

1. Skopiuj plik DLL do folderu wyjściowego projektu lub do innego folderu w standardowej ścieżce wyszukiwania systemu Windows dla bibliotek DLL. Zobacz [kolejność wyszukiwania biblioteki dołączanej dynamicznie](/windows/win32/dlls/dynamic-link-library-search-order).
2. Wykonaj kroki 1-3 dla bibliotek statycznych, aby zapewnić ścieżki do plików nagłówkowych i LIB.

## <a name="com-objects"></a>obiekty COM

Jeśli Natywna aplikacja C++ wymaga użycia obiektu COM, a ten obiekt jest *zarejestrowany*, wszystko, co trzeba zrobić, wywołuje funkcję CoCreateInstance i przekazuje identyfikator CLSID obiektu. System znajdzie go w rejestrze systemu Windows i załaduje go. Projekt C++/CLI może zużywać obiekt COM w ten sam sposób. Lub można go wykorzystać, dodając odwołanie do niego z listy **Dodaj odwołania > com** i zużywać ją za pośrednictwem otoki umożliwiającej wywoływanie [środowiska uruchomieniowego](/dotnet/framework/interop/runtime-callable-wrapper).

## <a name="net-assemblies-and-windows-runtime-components"></a>Zestawy .NET i składniki środowisko wykonawcze systemu Windows

W projektach platformy UWP lub C++/CLI, zestawy .NET lub składniki środowisko wykonawcze systemu Windows są zużywane przez dodanie *odwołania* do zestawu lub składnika. W węźle **odwołania** w projekcie platformy UWP lub C++/CLI widoczne są odwołania do często używanych składników. Kliknij prawym przyciskiem myszy węzeł **odwołania** w **Eksplorator rozwiązań** , aby wyświetlić **Menedżera odwołań** i przeszukać składniki dostępne w systemie. Wybierz przycisk **Przeglądaj** , aby przejść do dowolnego folderu, który zawiera niestandardowy składnik. Ponieważ zestawy .NET i składniki środowisko wykonawcze systemu Windows zawierają wbudowane informacje o typie, można wyświetlić ich metody i klasy, klikając prawym przyciskiem myszy i wybierając pozycję **Widok w Przeglądarka obiektów**.

## <a name="reference-properties"></a>Właściwości odwołania

Każdy rodzaj odwołania ma właściwości. Aby wyświetlić właściwości, wybierz odwołanie w Eksplorator rozwiązań i naciśnij **klawisze ALT + ENTER** lub kliknij prawym przyciskiem myszy i wybierz polecenie **Właściwości**. Niektóre właściwości są tylko do odczytu, a niektóre z nich można modyfikować. Jednak zazwyczaj nie trzeba ręcznie modyfikować tych właściwości.

### <a name="activex-reference-properties"></a>Właściwości odwołania ActiveX

Właściwości odwołania ActiveX są dostępne tylko w odniesieniu do składników modelu COM. Te właściwości są wyświetlane tylko po wybraniu składnika modelu COM w okienku **odwołania** . Właściwości nie są modyfikowane.

- **Pełna ścieżka kontrolki**

   Wyświetla ścieżkę katalogu przywoływanej kontrolki.

- **Identyfikator GUID kontrolki**

   Wyświetla identyfikator GUID dla kontrolki ActiveX.

- **Wersja kontrolki**

   Wyświetla wersję kontrolki ActiveX, do której istnieje odwołanie.

- **Nazwa biblioteki typów**

   Wyświetla nazwę biblioteki typów, do której istnieje odwołanie.

- **Narzędzie otoki**

   Wyświetla narzędzie używane do kompilowania zestawu międzyoperacyjnego na podstawie przywoływanej biblioteki COM lub kontrolki ActiveX.

### <a name="assembly-reference-properties-ccli"></a>Właściwości odwołania do zestawu (C++/CLI)

Właściwości odwołania do zestawu są dostępne tylko w odniesieniu do zestawów .NET Framework w projektach C++/CLI. Te właściwości są wyświetlane tylko po wybraniu zestawu .NET Framework w okienku **odwołania** . Właściwości nie są modyfikowane.

- **Ścieżka względna**

   Wyświetla ścieżkę względną z katalogu projektu do zestawu, do którego się odwołuje.

### <a name="build-properties"></a>Właściwości kompilacji

W przypadku różnych rodzajów odwołań dostępne są następujące właściwości. Umożliwiają one określenie sposobu kompilowania z odwołaniami.

- **Kopiuj lokalne**

   Określa, czy przywoływany zestaw ma być automatycznie kopiowany do lokalizacji docelowej podczas kompilacji.

- **Kopiuj lokalne zestawy satelickie (C++/CLI)**

   Określa, czy zestawy satelickie przywoływanego zestawu mają być automatycznie kopiowane do lokalizacji docelowej podczas kompilacji. Używany tylko w przypadku **kopiowania lokalnego** **`true`** .

- **Wyjście zestawu odwołania**

   Określa, że ten zestaw jest używany w procesie kompilacji. Jeśli **`true`** , zestaw jest używany w wierszu poleceń kompilatora podczas kompilacji.

### <a name="project-to-project-reference-properties"></a>Właściwości odwołania projektu do projektu

Następujące właściwości definiują *odwołanie projekt-projekt* z projektu wybranego w okienku **odwołania** do innego projektu w tym samym rozwiązaniu. Aby uzyskać więcej informacji, zobacz [Zarządzanie odwołaniami w projekcie](/visualstudio/ide/managing-references-in-a-project).

- **Połącz zależności biblioteki**

   Gdy ta właściwość ma **wartość true**, system projektu łączy pliki lib, które projekt niezależny generuje w projekcie zależnym. Zazwyczaj należy określić **wartość true**.

- **Identyfikator projektu**

   Jednoznacznie identyfikuje projekt niezależny. Wartość właściwości jest wewnętrznym identyfikatorem GUID systemu, który nie jest modyfikowany.

- **Użyj danych wejściowych zależności biblioteki**

   Gdy ta właściwość ma **wartość false**, system projektu nie będzie łączyć plików obj dla biblioteki, która nie produkuje niezależnego projektu do projektu zależnego. Dlatego ta wartość wyłącza łączenie przyrostowe. Zazwyczaj należy określić **wartość FAŁSZ** , ponieważ Kompilowanie aplikacji może zająć dużo czasu, jeśli istnieje wiele niezależnych projektów.

### <a name="read-only-reference-properties-com--net"></a>Właściwości odwołania tylko do odczytu (COM & .NET)

W odwołaniach do zestawów COM i .NET istnieją następujące właściwości i nie można ich modyfikować.

- **Nazwa zestawu**

   Wyświetla nazwę zestawu dla przywoływanego zestawu.

- **Kultura**

   Wyświetla kulturę wybranego odwołania.

- **Opis**

   Wyświetla opis wybranego odwołania.

- **Pełna ścieżka**

   Wyświetla ścieżkę katalogu przywoływanego zestawu.

- **Tożsamość**

   W przypadku zestawów .NET Framework wyświetla pełną ścieżkę. W przypadku składników COM program wyświetla identyfikator GUID.

- **Etykieta**

   Wyświetla etykietę odwołania.

- **Nazwa**

   Wyświetla nazwę odwołania.

- **Token klucza publicznego**

   Wyświetla token klucza publicznego używany do identyfikowania przywoływanego zestawu.

- **Silna nazwa**

   **`true`** Jeśli przywoływany zestaw ma silną nazwę. Zestaw o silnej nazwie ma unikatową wersję.

- **Wersja**

   Wyświetla wersję przywoływanego zestawu.

## <a name="see-also"></a>Zobacz także

[Odwołanie do strony właściwości projektu C++](reference/property-pages-visual-cpp.md)<br>
[Ustawianie właściwości kompilacji i kompilatora języka C++ w programie Visual Studio](working-with-project-properties.md)
