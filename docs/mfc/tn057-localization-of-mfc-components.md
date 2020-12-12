---
description: 'Dowiedz się więcej na temat: TN057: Lokalizacja składników MFC'
title: 'TN057: lokalizacja składników MFC'
ms.date: 06/28/2018
helpviewer_keywords:
- components [MFC], localizing
- TN057
- resources [MFC], localization
- localization [MFC], MFC resources
- localization [MFC], MFC components
- MFC DLLs [MFC], localizing
- DLLs [MFC], localizing MFC
- localization [MFC], resources
ms.assetid: 5376d329-bd45-41bd-97f5-3d895a9a0af5
ms.openlocfilehash: d4a331e74acd2b5b38ae059ea180a0a2148e3a0f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97214809"
---
# <a name="tn057-localization-of-mfc-components"></a>TN057: lokalizacja składników MFC

> [!NOTE]
> Następująca Uwaga techniczna nie została zaktualizowana, ponieważ została najpierw uwzględniona w dokumentacji online. W związku z tym niektóre procedury i tematy mogą być nieaktualne lub nieprawidłowe. Aby uzyskać najnowsze informacje, zalecamy wyszukiwanie tematu zainteresowania w indeksie dokumentacji online.

Ta Uwaga opisuje niektóre projekty i procedury, których można użyć do zlokalizowania składnika, jeśli jest to aplikacja lub kontrolka OLE lub biblioteka DLL, która używa MFC.

## <a name="overview"></a>Omówienie

Istnieją dwie problemy, które należy rozwiązać podczas lokalizowania składnika korzystającego z MFC. Najpierw należy zlokalizować własne zasoby — ciągi, okna dialogowe i inne zasoby, które są specyficzne dla danego składnika. Większość składników utworzonych przy użyciu MFC obejmuje również wiele zasobów, które są zdefiniowane przez MFC. Należy również zapewnić zlokalizowane zasoby MFC. Na szczęście kilka języków jest już dostarczonych przez MFC.

Ponadto składnik powinien być przygotowany do uruchamiania w jego środowisku docelowym (w środowisku z obsługą standardu lub DBCS). W większości przypadków jest to zależne od aplikacji, która wymaga poprawnego skonfigurowania znaków z dużą liczbą bitów i obsługi ciągów zawierających znaki dwubajtowe. MFC jest włączona domyślnie dla obu tych środowisk, w taki sposób, że możliwe jest posiadanie pojedynczego pliku binarnego na całym świecie, który jest używany na wszystkich platformach, które są połączone w czasie instalacji.

## <a name="localizing-your-components-resources"></a>Lokalizowanie zasobów składnika

Lokalizowanie aplikacji lub biblioteki DLL powinno wiązać się z zastępowaniem zasobów, które pasują do języka docelowego. W przypadku własnych zasobów jest to stosunkowo proste: Edytuj zasoby w edytorze zasobów i skompiluj aplikację. Jeśli kod jest prawidłowo zapisany, nie będzie żadnych ciągów ani tekstów, które mają być lokalizowane w kodzie źródłowym języka C++ — wszystkie lokalizacje można wykonać, modyfikując zasoby. W rzeczywistości można zaimplementować składnik, w taki sposób, że wszystkie udostępnienie zlokalizowanej wersji nie obejmuje nawet kompilacji oryginalnego kodu. Jest to bardziej skomplikowane, ale jest dobrze dobrane i jest mechanizmem wybranym dla MFC. Istnieje również możliwość zlokalizowania aplikacji przez załadowanie pliku EXE lub DLL do edytora zasobów i bezpośrednie edytowanie zasobów. Gdy jest to możliwe, wymaga ponownego zastosowania tych zmian przy każdej kompilacji nowej wersji aplikacji.

Jednym ze sposobów, aby uniknąć odnalezienia wszystkich zasobów w oddzielnej bibliotece DLL, nazywanych czasami satelitarną biblioteką DLL. Ta biblioteka DLL jest następnie ładowana dynamicznie w czasie wykonywania, a zasoby są ładowane z tej biblioteki DLL, a nie z modułu głównego ze wszystkimi kodami. MFC bezpośrednio obsługuje to podejście. Rozważmy aplikację o nazwie MYAPP.EXE; wszystkie jego zasoby mogą znajdować się w bibliotece DLL o nazwie MYRES.DLL. W aplikacji `InitInstance` można wykonać następujące czynności w celu załadowania biblioteki DLL i spowodowania załadowania przez MFC zasobów z tej lokalizacji:

```cpp
CMyApp::InitInstance()
{
    // one of the first things in the init code
    HINSTANCE hInst = LoadLibrary("myres.dll");

    if (hInst != NULL)
        AfxSetResourceHandle(hInst);

    // other initialization code would follow
    // ...
}
```

Od tego dnia MFC będzie ładować zasoby z tej biblioteki DLL, a nie z myapp.exe. Wszystkie zasoby, jednak muszą być obecne w tej bibliotece DLL; MFC nie będzie przeszukiwania wystąpienia aplikacji w wyszukiwaniu danego zasobu. Ta technika stosuje się równie dobrze do zwykłych bibliotek DLL MFC, jak i formantów OLE. Program instalacyjny skopiuje odpowiednią wersję MYRES.DLL w zależności od ustawień regionalnych zasobów, które użytkownik chce.

Tworzenie bibliotek DLL dotyczących tylko zasobów jest stosunkowo proste. Tworzysz projekt DLL, Dodaj. RC i Dodaj wymagane zasoby. Jeśli masz istniejący projekt, który nie korzysta z tej techniki, możesz skopiować zasoby z tego projektu. Po dodaniu pliku zasobów do projektu prawie gotowe do skompilowania projektu. Jedyną czynnością, którą należy wykonać, jest ustawienie opcji konsolidatora do uwzględnienia **/NOENTRY**. Nakazuje konsolidatorowi, że biblioteka DLL nie ma punktu wejścia — ponieważ nie ma kodu, nie ma punktu wejścia.

> [!NOTE]
> Edytor zasobów w Visual C++ 4,0 i nowszych obsługuje wiele języków na. Plik RC. Może to ułatwić zarządzanie lokalizacją w pojedynczym projekcie. Zasoby dla każdego języka są kontrolowane przez dyrektywy preprocesora wygenerowane przez Edytor zasobów.

## <a name="using-the-provided-mfc-localized-resources"></a>Korzystanie z dostarczonych zlokalizowanych zasobów MFC

Każda aplikacja MFC, która kompiluje się ponownie używa dwóch rzeczy z MFC: Code i Resources. Oznacza to, że MFC zawiera różne komunikaty o błędach, wbudowane okna dialogowe i inne zasoby, które są używane przez klasy MFC. Aby można było całkowicie zlokalizować aplikację, należy zlokalizować nie tylko zasoby aplikacji, ale również zasoby, które pochodzą bezpośrednio z MFC. MFC udostępnia wiele różnych plików zasobów językowych automatycznie, dzięki czemu w przypadku, gdy językiem docelowym jest jeden z obsługiwanych języków MFC, wystarczy upewnić się, że są używane te zlokalizowane zasoby.

Zgodnie z tym pisaniem MFC obsługuje język chiński, niemiecki, hiszpański, francuski, włoski, japoński i koreański. Pliki zawierające te zlokalizowane wersje znajdują się w MFC\INCLUDE\L. * ("L" oznacza katalogi zlokalizowane). Pliki w języku niemieckim są na przykład MFC\INCLUDE\L.DEU. Aby spowodować, że aplikacja będzie używać tych plików z wersji RC zamiast plików znajdujących się w MFC\INCLUDE, Dodaj `/IC:\PROGRAM FILES\MICROSOFT VISUAL STUDIO .NET 2003\VC7\MFC\INCLUDE\L.DEU` do wiersza polecenia RC (to jest tylko przykład: należy zastąpić wybrane ustawienia regionalne, a także katalog, w którym zainstalowano Visual C++).

Powyższe instrukcje będą działały, jeśli aplikacja jest statycznie łączona z MFC. Większość łączy z większością aplikacji (ponieważ jest to AppWizard domyślna). W tym scenariuszu nie tylko kod jest połączony dynamicznie — jest to zasoby. W związku z tym można zlokalizować zasoby w aplikacji, ale zasoby implementacji MFC nadal będą ładowane z MFC7x.DLL (lub nowszej wersji) lub z MFC7xLOC.DLL, jeśli istnieje. Można to podejścia z dwóch różnych kątów.

Bardziej skomplikowane podejście polega na dostarczeniu jednego z zlokalizowanych MFC7xLOC.DLLs (takich jak MFC7xDEU, na potrzeby języka niemieckiego, MFC7xESP.DLL dla języka hiszpańskiego itp.) lub w nowszej wersji, a następnie zainstalowanie odpowiedniej MFC7xLOC.DLL w katalogu systemowym, gdy użytkownik zainstaluje aplikację. Może to być bardzo skomplikowany zarówno dla dewelopera, jak i dla użytkownika końcowego, ponieważ nie jest to zalecane. Aby uzyskać więcej informacji na temat tej techniki i jej zamiarów, zobacz [Uwagi techniczne 56](../mfc/tn056-installation-of-localized-mfc-components.md) .

Najprostszym i najbezpieczniejszym podejściem jest dołączenie zlokalizowanych zasobów MFC do samej aplikacji lub biblioteki DLL (lub jej satelickiej biblioteki DLL, jeśli są używane). Pozwala to uniknąć problemów z instalacją MFC7xLOC.DLL prawidłowo. W tym celu należy postępować zgodnie z takimi samymi instrukcjami, jak w przypadku przypadku statycznego podanego powyżej (odpowiednio ustawiając wiersz polecenia RC, aby wskazywał zlokalizowane zasoby), z tą różnicą, że należy również usunąć `/D_AFXDLL` definicję, która została dodana przez AppWizard. Gdy `/D_AFXDLL` jest zdefiniowany, plik AFXRES. H (i inne pliki MFC RC) nie definiują żadnych zasobów (ponieważ zostaną pobrane z bibliotek MFC DLL).

## <a name="see-also"></a>Zobacz też

[Uwagi techniczne według numeru](../mfc/technical-notes-by-number.md)<br/>
[Uwagi techniczne według kategorii](../mfc/technical-notes-by-category.md)
