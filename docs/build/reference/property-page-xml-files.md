---
title: Pliki reguł XML na stronie właściwości
description: Opis plików i treści reguł XML programu Visual Studio IDE C++.
ms.date: 10/14/2020
helpviewer_keywords:
- property page XML files
ms.openlocfilehash: 96cbf6a32cada2b594874493868ec884823016cb
ms.sourcegitcommit: 6e5429e076e552b32e8bdc49480c51498d7924c1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/15/2020
ms.locfileid: "92099722"
---
# <a name="property-page-xml-rule-files"></a>Pliki reguł XML na stronie właściwości

Strony właściwości projektu w IDE są konfigurowane przy użyciu plików XML w folderze reguły domyślne. Pliki XML opisują nazwy reguł, kategorii i poszczególnych właściwości, ich typ danych, wartości domyślne i sposób ich wyświetlania. Po ustawieniu właściwości w IDE, Nowa wartość jest przechowywana w pliku projektu.

::: moniker range="vs-2015"

Ścieżka do folderu reguł domyślnych zależy od ustawień regionalnych i używanej wersji programu Visual Studio. W wierszu polecenia programu Visual Studio 2015 lub starszej, folder Rules ma wartość *`%ProgramFiles(x86)%\MSBuild\Microsoft.Cpp\v4.0\<version>\<locale>`* . `<version>`Wartość jest *`v140`* w programie Visual Studio 2015. `<locale>`Jest to identyfikator LCID, na przykład `1033` w języku angielskim. Użyjesz innej ścieżki dla każdej wersji programu Visual Studio, która jest zainstalowana, i dla każdego języka. Na przykład domyślna ścieżka folderu dla programu Visual Studio 2015 Community Edition w języku angielskim może być taka sama *`C:\Program Files (x86)\MSBuild\Microsoft.Cpp\v4.0\v140\1033\`* .

::: moniker-end

::: moniker range="vs-2017"

Ścieżka do folderu reguł domyślnych zależy od ustawień regionalnych i używanej wersji programu Visual Studio. W wierszu polecenia programu Visual Studio 2017 Developer znajduje się folder reguły *`%VSINSTALLDIR%Common7\IDE\VC\VCTargets\<locale>\`* . `<locale>`Jest to identyfikator LCID, na przykład `1033` w języku angielskim. W wierszu polecenia programu Visual Studio 2015 lub starszej, folder reguł to *`%ProgramFiles(x86)%\MSBuild\Microsoft.Cpp\v4.0\<version>\<locale>\`* , gdzie `<version>` wartość jest *`v140`* w programie Visual Studio 2015. Użyjesz innej ścieżki dla każdej wersji programu Visual Studio, która jest zainstalowana, i dla każdego języka. Na przykład domyślna ścieżka folderu dla programu Visual Studio 2017 Community Edition w języku angielskim może być taka sama *`C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\VC\VCTargets\1033\`* .

::: moniker-end

::: moniker range=">=vs-2019"

Ścieżka do folderu reguł domyślnych zależy od ustawień regionalnych i używanej wersji programu Visual Studio. W wierszu polecenia programu Visual Studio 2019 lub nowszym folder reguł to *`%VSINSTALLDIR%MSBuild\Microsoft\VC\<version>\<locale>\`* , gdzie `<version>` wartość jest *`v160`* w programie Visual Studio 2019. `<locale>`Jest to identyfikator LCID, na przykład `1033` w języku angielskim. W programie Visual Studio 2017 folder reguł to *`%VSINSTALLDIR%Common7\IDE\VC\VCTargets\<locale>\`* . W wierszu polecenia programu Visual Studio 2015 lub starszej, folder Rules ma wartość *`%ProgramFiles(x86)%\MSBuild\Microsoft.Cpp\v4.0\<version>\<locale>\`* . Użyjesz innej ścieżki dla każdej wersji programu Visual Studio, która jest zainstalowana, i dla każdego języka. Na przykład domyślna ścieżka folderu dla programu Visual Studio 2019 Community Edition w języku angielskim może być taka sama *`C:\Program Files (x86)\Microsoft Visual Studio\2019\Community\MSBuild\Microsoft\VC\v160\1033\`* .

::: moniker-end

Musisz tylko zrozumieć wewnętrzne działania tych plików i środowisko IDE programu Visual Studio w kilku scenariuszach:

- Chcesz utworzyć niestandardową stronę właściwości lub
- Chcesz dostosować właściwości projektu bez używania środowiska IDE programu Visual Studio.

## <a name="contents-of-rule-files"></a>Zawartość plików reguł

Najpierw Otwórz strony właściwości dla projektu. Kliknij prawym przyciskiem myszy węzeł projektu w **Eksplorator rozwiązań** i wybierz polecenie **Właściwości**:

![Pokazuje okno dialogowe właściwości projektu Visual Studio C++](../media/cpp-property-page-2017.png)

Każdy węzeł we **właściwościach konfiguracji** jest nazywany *regułą*. Reguła czasami reprezentuje pojedyncze narzędzie, takie jak kompilator. Ogólnie rzecz biorąc termin odnosi się do elementu, który ma właściwości, które wykonuje i który może generować niektóre dane wyjściowe. Każda reguła jest wypełniana na podstawie pliku XML w folderze reguł domyślnych. Na przykład reguła C/C++, która jest wyświetlana w tym miejscu, jest wypełniana przez *"cl.xml"*.

Każda reguła ma zestaw właściwości, które są pogrupowane w *Kategorie*. Każdy podwęzeł w ramach reguły reprezentuje kategorię. Na przykład węzeł **Optymalizacja** w **C/C++** zawiera wszystkie właściwości związane z optymalizacją narzędzia kompilatora. Właściwości i ich wartości są renderowane w formacie siatki w okienku po prawej stronie.

Możesz otworzyć *`cl.xml`* w Notatniku lub dowolnym edytorze XML. Zobaczysz węzeł główny o nazwie `Rule` . Definiuje tę samą listę właściwości, które są wyświetlane w interfejsie użytkownika wraz z dodatkowymi metadanymi.

```xml
<?xml version="1.0" encoding="utf-8"?>
<!--Copyright, Microsoft Corporation, All rights reserved.-->
<Rule Name="CL" PageTemplate="tool" DisplayName="C/C++" SwitchPrefix="/" Order="10" xmlns="http://schemas.microsoft.com/build/2009/properties" xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml" xmlns:sys="clr-namespace:System;assembly=mscorlib">
  <Rule.Categories>
    <Category Name="General" DisplayName="General" />
    <Category Name="Optimization" DisplayName="Optimization" />
    <Category Name="Preprocessor" DisplayName="Preprocessor" />
    <Category Name="Code Generation" DisplayName="Code Generation" />
    <Category Name="Language" DisplayName="Language" />
    <Category Name="Precompiled Headers" DisplayName="Precompiled Headers" />
    <Category Name="Output Files" DisplayName="Output Files" />
    <Category Name="Browse Information" DisplayName="Browse Information" />
    <Category Name="Advanced" DisplayName="Advanced" />
    <Category Name="All Options" DisplayName="All Options" Subtype="Search" />
    <Category Name="Command Line" DisplayName="Command Line" Subtype="CommandLine" />
  </Rule.Categories>
  <!-- . . . -->
</Rule>
```

Istnieje jeden plik XML dla każdego węzła w obszarze **Właściwości konfiguracji** w interfejsie użytkownika stron właściwości. Możesz dodawać lub usuwać reguły w interfejsie użytkownika: są one wykonywane przez dołączenie lub usunięcie lokalizacji do odpowiednich plików XML w projekcie. Na przykład jest to sposób *`Microsoft.CppBuild.targets`* (znaleziono jeden poziom wyższy niż folder 1033) obejmuje *`cl.xml`* :

```xml
<PropertyPageSchema Condition="'$(ConfigurationType)' != 'Utility'" Include="$(VCTargetsPath)$(LangID)\cl.xml"/>
```

W przypadku *`cl.xml`* wszystkich danych masz podstawową strukturę:

```xml
<?xml version="1.0" encoding="utf-8"?>
<Rule>
  <Rule.DataSource />
  <Rule.Categories>
    <Category />
    <!-- . . . -->
  </Rule.Categories>
  <BoolProperty />
  <EnumProperty />
  <IntProperty />
  <StringProperty />
  <StringListProperty />
</Rule>
```

W następnej sekcji opisano każdy element główny i niektóre z metadanych, które można dołączyć.

### <a name="rule-attributes"></a>Atrybuty reguły

**`<Rule>`** Element jest węzłem głównym w pliku XML. Może mieć wiele atrybutów:

```xml
<Rule Name="CL" PageTemplate="tool" SwitchPrefix="/" Order="10"
          xmlns="http://schemas.microsoft.com/build/2009/properties"
          xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
          xmlns:sys="clr-namespace:System;assembly=mscorlib">
  <Rule.DisplayName>
    <sys:String>C/C++</sys:String>
  </Rule.DisplayName>
```

- **`Name`**: Atrybut name jest IDENTYFIKATORem `Rule` . Musi być unikatowa wśród wszystkich plików XML strony właściwości projektu.

- **`PageTemplate`**: Wartość tego atrybutu jest używana przez interfejs użytkownika do wybierania z kolekcji szablonów interfejsu użytkownika. Szablon "Narzędzie" renderuje właściwości w standardowym formacie siatki. Inne wbudowane wartości tego atrybutu to "Debugger" i "Generic". Zobacz odpowiednio węzeł Debugowanie i węzeł ogólny, aby zobaczyć format interfejsu użytkownika wynikający z określenia tych wartości. Interfejs użytkownika dla szablonu strony "debuger" używa pola rozwijanego do przełączania między właściwościami różnych debugerów. Szablon "ogólny" wyświetla różne kategorie właściwości na jednej stronie, w przeciwieństwie do wielu węzłów podrzędnych kategorii w `Rule` węźle. Ten atrybut jest tylko sugestią interfejsu użytkownika. Plik XML został zaprojektowany jako niezależny od interfejsu użytkownika. Inny interfejs użytkownika może używać tego atrybutu do różnych celów.

- **`SwitchPrefix`**: Prefiks używany w wierszu polecenia dla przełączników. Wartość `"/"` spowodowałaby, że przełączniki wyglądają jak **`/ZI`** , **`/nologo`** , **`/W3`** , i tak dalej.

- **`Order`**: Sugestia klienta potencjalnego interfejsu użytkownika w względnej lokalizacji w `Rule` porównaniu do wszystkich innych reguł w systemie.

- **`xmlns`**: Standardowy element XML. Widoczne są trzy obszary nazw. Te atrybuty odpowiadają przestrzeniom nazw dla klas deserializacji XML, schematu XML i przestrzeni nazw System.

- **`DisplayName`**: Nazwa, która jest wyświetlana w interfejsie użytkownika strony właściwości dla `Rule` węzła. Ta wartość jest zlokalizowana. Utworzyliśmy `DisplayName` jako element podrzędny, `Rule` a nie jako atrybut (na przykład `Name` lub `SwitchPrefix` ) ze względu na wymagania narzędzia lokalizacji wewnętrznej. Z perspektywy XML obydwa są równoważne. Dzięki temu można po prostu wprowadzić atrybut, aby zmniejszyć jego czytelność lub pozostawić go w taki sam sposób.

- **`DataSource`**: Ta ważna Właściwość Nakazuje systemowi projektu odczytanie i zapisanie wartości właściwości oraz grupowanie (wyjaśnione później). W przypadku *`cl.xml`* wartości są następujące:

    ```xml
    <DataSource Persistence="ProjectFile" ItemType="ClCompile" Label="" HasConfigurationCondition="true" />
    ```

  - `Persistence="ProjectFile"` informuje system projektu, że wszystkie właściwości w `Rule` pliku projektu lub pliku arkusza właściwości (w zależności od tego, który węzeł został użyty do duplikowania stron właściwości). Druga możliwa wartość to `"UserFile"` , co spowoduje zapisanie wartości w *`.user`* pliku.

  - `ItemType="ClCompile"` wskazuje, że właściwości będą przechowywane jako metadane ItemDefinition lub metadane elementu (tylko wtedy, gdy strony właściwości zostały zduplikowane z węzła pliku w Eksploratorze rozwiązań) tego typu elementu. Jeśli to pole nie jest ustawione, właściwość jest zapisywana jako wspólna właściwość w liście właściwości.

  - `Label=""` wskazuje, że gdy właściwości są zapisywane jako `ItemDefinition` metadane, etykieta nadrzędnego ItemDefinitionGroup będzie pusta (każdy element MSBuild może mieć etykietę). Program Visual Studio 2017 lub nowszy używa grup oznaczonych jako do nawigowania w pliku projektu. vcxproj. Grupy zawierające większość `Rule` właściwości mają pusty ciąg jako etykietę.

  - `HasConfigurationCondition="true"` informuje system projektu, aby dołączył warunek konfiguracji do wartości tak, aby obowiązywał tylko dla bieżącej konfiguracji projektu (warunek może być dołączany do grupy nadrzędnej lub sama sama wartość). Na przykład Otwórz strony właściwości poza węzłem projektu i ustaw wartość właściwości **Traktuj ostrzeżenia jako błąd** w obszarze **Właściwości konfiguracji > C/C++ ogólne** do "tak". Następująca wartość jest zapisywana w pliku projektu. Zwróć uwagę na warunek konfiguracji dołączony do elementu nadrzędnego ItemDefinitionGroup.

    ```xml
    <ItemDefinitionGroup Condition="'$(Configuration)|$(Platform)'=='Debug|Win32'">
      <ClCompile>
        <TreatWarningAsError>true</TreatWarningAsError>
      </ClCompile>
    </ItemDefinitionGroup>
    ```

     Jeśli ta wartość jest ustawiona na stronie właściwości dla określonego pliku, na przykład *`stdafx.cpp`* , wówczas wartość właściwości powinna być zapisywana w ramach `stdafx.cpp` elementu w pliku projektu, jak pokazano poniżej. Zwróć uwagę, jak warunek konfiguracji jest bezpośrednio dołączony do samego metadanych:

    ```xml
    <ItemGroup>
      <ClCompile Include="stdafx.cpp">
        <TreatWarningAsError Condition="'$(Configuration)|$(Platform)'=='Debug|Win32'">true</TreatWarningAsError>
      </ClCompile>
    </ItemGroup>
    ```

  Innym atrybutem `DataSource` niewymienionym tutaj jest `PersistedName` . Ten atrybut służy do reprezentowania właściwości w pliku projektu przy użyciu innej nazwy. Domyślnie ten atrybut jest ustawiony na Właściwość `Name` .

  Właściwość pojedynczej może przesłonić `DataSource` element nadrzędny `Rule` . W takim przypadku lokalizacja tej właściwości będzie różna od innych właściwości w `Rule` .

- Istnieją inne atrybuty elementu, w `Rule` tym `Description` i `SupportsFileBatching` , które nie są wyświetlane w tym miejscu. Pełny zestaw atrybutów, które mają zastosowanie do `Rule` lub z dowolnego innego elementu, można uzyskać, przeglądając dokumentację dla tych typów. Alternatywnie można przeanalizować właściwości publiczne dla typów w `Microsoft.Build.Framework.XamlTypes` przestrzeni nazw `Microsoft.Build.Framework.dll` zestawu.

- **`DisplayName`**, **`PageTemplate`** , i **`Order`** są właściwościami związanymi z INTERFEJSem użytkownika, które znajdują się w tym samym modelu danych niezależnym od interfejsu użytkownika. Te właściwości są prawie określone do użycia przez każdy interfejs użytkownika, który jest używany do wyświetlania stron właściwości. `DisplayName` i `Description` są dwie właściwości, które są obecne w prawie wszystkich elementach w pliku XML. Te dwie właściwości są jedynymi, które są zlokalizowane.

### <a name="category-elements"></a>Elementy kategorii

`Rule`Może mieć wiele `Category` elementów. Kolejność, w której kategorie są wymienione w pliku XML jest sugestią interfejsu użytkownika do wyświetlania kategorii w tej samej kolejności. Na przykład kolejność kategorii w węźle **C/C++** widocznym w interfejsie użytkownika jest taka sama jak kolejność w *`cl.xml`* . Przykładowa Kategoria wygląda następująco:

```xml
<Category Name="Optimization">
  <Category.DisplayName>
    <sys:String>Optimization</sys:String>
  </Category.DisplayName>
</Category>
```

W tym fragmencie kodu `Name` przedstawiono `DisplayName` atrybuty i, które zostały opisane wcześniej. Po ponownym uruchomieniu istnieją inne atrybuty, `Category` które mogą nie być wyświetlane w przykładzie. Aby dowiedzieć się więcej, Przeczytaj dokumentację lub Zbadaj zestawy przy użyciu programu *`ildasm.exe`* .

### <a name="property-elements"></a>Elementy właściwości

Większość pliku reguł składa się z `Property` elementów. Zawierają listę wszystkich właściwości w `Rule` . Każda właściwość może być jednym z pięciu możliwych typów przedstawionych w podstawowej strukturze:,,, `BoolProperty` `EnumProperty` `IntProperty` `StringProperty` i `StringListProperty` . W pliku mogą znajdować się tylko niektóre z tych typów. Właściwość ma wiele atrybutów, które można szczegółowo opisać. `StringProperty`Opisano to tutaj. Pozostałe są podobne.

```xml
<StringProperty Subtype="file" Name="ObjectFileName" Category="Output Files" Switch="Fo">
  <StringProperty.DisplayName>
    <sys:String>Object File Name</sys:String>
  </StringProperty.DisplayName>
  <StringProperty.Description>
    <sys:String>Specifies a name to override the default object file name; can be file or directory name.(/Fo[name])</sys:String>
  </StringProperty.Description>
</StringProperty>
```

Większość atrybutów w fragmencie kodu została opisana przed. Nowe są `Subtype` , `Category` i `Switch` .

- **`Subtype`** jest atrybutem dostępnym tylko `StringProperty` dla `StringListProperty` elementów i. Zapewnia informacje kontekstowe. Na przykład wartość `file` wskazuje, że właściwość reprezentuje ścieżkę pliku. Program Visual Studio używa takich informacji kontekstowych, aby usprawnić proces edycji. Na przykład może udostępnić okno Eksploratora Windows, które umożliwia użytkownikowi wybranie pliku wizualnie jako edytora właściwości.

- **`Category`**: Kategoria, pod którą znajduje się ta właściwość. Spróbuj znaleźć tę właściwość w kategorii **pliki wyjściowe** w interfejsie użytkownika.

- **`Switch`**: Gdy reguła reprezentuje narzędzie, takie jak narzędzie kompilatora, większość właściwości jest `Rule` przenoszona jako przełączniki do pliku wykonywalnego narzędzia w czasie kompilacji. Wartość tego atrybutu wskazuje, który literał przełączania ma być używany. W `<StringProperty>` przykładzie określono, że przełącznik powinien być **`Fo`** . W połączeniu z `SwitchPrefix` atrybutem w obiekcie nadrzędnym `Rule` Ta właściwość jest przenoszona do pliku wykonywalnego jako  **`/Fo"Debug\"`** . Jest on widoczny w wierszu polecenia dla C/C++ w interfejsie użytkownika strony właściwości.

   Inne atrybuty właściwości obejmują:

- **`Visible`**: Jeśli nie chcesz, aby właściwość była wyświetlana na stronach właściwości, ale chcesz ją udostępnić w czasie kompilacji, ustaw ten atrybut na `false` .

- **`ReadOnly`**: Jeśli chcesz udostępnić widok tylko do odczytu wartości tej właściwości na stronach właściwości, ustaw ten atrybut na `true` .

- **`IncludeInCommandLine`**: W czasie kompilacji narzędzie może nie potrzebować niektórych jego właściwości. Ustaw ten atrybut na `false` , aby uniemożliwić przekazywanie określonej właściwości.
