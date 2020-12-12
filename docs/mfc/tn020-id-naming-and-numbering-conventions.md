---
description: 'Dowiedz się więcej na temat: TN020: Konwencje nazewnictwa i numerowania identyfikatorów'
title: 'TN020: konwencje nazewnictwa i numerowania identyfikatorów'
ms.date: 11/04/2016
f1_keywords:
- vc.id
helpviewer_keywords:
- TN020
- resource identifiers, naming and numbering
- resource identifiers
ms.assetid: aecbd2cf-68b3-47f6-ae21-b1f507917245
ms.openlocfilehash: 85f59e45ec9d4ce748515cf638f4fb4cf33c7d38
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97215875"
---
# <a name="tn020-id-naming-and-numbering-conventions"></a>TN020: konwencje nazewnictwa i numerowania identyfikatorów

Ta Uwaga opisuje konwencje nazewnictwa i numerowania identyfikatorów, które są używane przez MFC 2,0 dla zasobów, poleceń, ciągów, kontrolek i okien podrzędnych.

Konwencje nazewnictwa i numeracji MFC mają spełniać następujące wymagania:

- Podaj spójny Standard nazewnictwa identyfikatorów używany w bibliotece MFC i aplikacjach MFC, które są obsługiwane przez Edytor zasobów Visual C++. Ułatwia to programistom interpretowanie typu i pochodzenia zasobu na podstawie jego identyfikatora.

- Wyróżnij silną relację od 1 do 1 między określonymi typami identyfikatorów.

- Zgodność z powszechnie używanymi standardami nazewnictwa identyfikatorów w systemie Windows.

- Podziel na partycje obszar numerowania identyfikatorów. Numery IDENTYFIKACYJNe mogą być przypisywane przez programistę, MFC, Windows i edytowane Visual C++ zasoby. Odpowiednie partycjonowanie pomoże uniknąć duplikowania numerów IDENTYFIKACYJNych.

## <a name="the-id-prefix-naming-convention"></a>Konwencja nazewnictwa prefiksów identyfikatorów

W aplikacji może wystąpić kilka typów identyfikatorów. Konwencja nazewnictwa identyfikatorów MFC definiuje różne prefiksy dla różnych typów zasobów.

MFC używa prefiksu "IDR_", aby wskazać identyfikator zasobu dotyczący wielu typów zasobów. Na przykład dla danego okna ramki MFC używa tego samego prefiksu "IDR_", aby wskazać menu, akcelerator, ciąg i zasób ikony. W poniższej tabeli przedstawiono różne prefiksy i ich użycie:

|Prefiks|Zastosowanie|
|------------|---------|
|IDR_|Dla wielu typów zasobów (używanych głównie dla menu, akceleratorów i wstążek).|
|IDD_|Dla zasobów szablonu okna dialogowego (na przykład IDD_DIALOG1).|
|IDC_|Dla zasobów kursora.|
|IDI_|Dla zasobów ikon.|
|IDB_|Dla zasobów bitmapowych.|
|IDS_|Dla zasobów ciągu.|

W ramach zasobu okna dialogowego MFC stosuje się do następujących konwencji:

|Prefiks lub etykieta|Zastosowanie|
|---------------------|---------|
|IDOK, IDCANCEL|Dla standardowych identyfikatorów przycisków wypychania.|
|IDC_|Inne kontrolki okna dialogowego.|

Prefiks "IDC_" jest również używany w przypadku kursorów. Ten konflikt nazewnictwa nie jest zazwyczaj problemem, ponieważ typowa aplikacja będzie zawierać kilka kursorów i wiele kontrolek dialogowych.

W ramach zasobu menu MFC stosuje się do następujących konwencji:

|Prefiks|Zastosowanie|
|------------|---------|
|IDM_|Dla elementów menu, które nie używają architektury poleceń MFC.|
|ID_|Dla poleceń menu, które używają architektury poleceń MFC.|

Polecenia, które są zgodne z architekturą poleceń MFC, muszą mieć procedurę obsługi poleceń ON_COMMAND i mogą mieć procedurę obsługi ON_UPDATE_COMMAND_UI. Jeśli te programy obsługi poleceń stosują się do architektury poleceń MFC, będą działać prawidłowo, niezależnie od tego, czy są powiązane z poleceniem menu, przyciskiem paska narzędzi lub przyciskiem paska dialogowego. Ten sam prefiks "ID_" jest również używany dla ciągu wiersza polecenia menu, który jest wyświetlany na pasku komunikatów programu. Większość elementów menu w aplikacji powinna być zgodna z konwencjami poleceń MFC. Wszystkie standardowe identyfikatory poleceń (na przykład ID_FILE_NEW) są zgodne z tą konwencją.

MFC używa również "IDP_" jako wyspecjalizowanej postaci ciągów (zamiast "IDS_"). Ciągi z prefiksem "IDP_" są monitami, czyli ciągami używanymi w oknach komunikatów. Ciągi "IDP_" mogą zawierać "%1" i "%2" jako symbole zastępcze ciągów określonych przez program. Ciągi "IDP_" zazwyczaj zawierają tematy pomocy z nimi skojarzone i ciągi "IDS_" nie. Ciągi "IDP_" są zawsze zlokalizowane, a ciągi "IDS_" mogą nie być lokalizowane.

Biblioteka MFC używa również prefiksu "IDW_" jako wyspecjalizowanej formy identyfikatorów sterowania (zamiast "IDC_"). Te identyfikatory są przypisywane do okien podrzędnych, takich jak widoki i rozdzielacze, według klas struktury. Identyfikatory implementacji MFC są poprzedzone prefiksem "AFX_".

## <a name="the-id-numbering-convention"></a>Konwencja ID-Numbering

Poniższa tabela zawiera listę prawidłowych zakresów dla identyfikatorów określonych typów. Niektóre limity są limitami implementacji technicznej, a inne są konwencjami, które są przeznaczone do zapobiegania kolizji identyfikatorów z wstępnie zdefiniowanymi identyfikatorami systemu Windows lub implementacją domyślną MFC.

Zdecydowanie zalecamy zdefiniowanie wszystkich identyfikatorów wewnątrz zalecanych zakresów. Dolny limit tych zakresów wynosi 1, ponieważ 0 nie jest używany. Zalecamy użycie wspólnej Konwencji i użycie 100 lub 101 jako pierwszego identyfikatora.

|Prefiks|Typ zasobu|Prawidłowy zakres|
|------------|-------------------|-----------------|
|IDR_|wielokrotność|od 1 do 0x6FFF|
|IDD_|szablony okna dialogowego|od 1 do 0x6FFF|
|IDC_, IDI_, IDB_|kursory, ikony, mapy bitowe|od 1 do 0x6FFF|
|IDS_, IDP_|ciągi ogólne|od 1 do 0x7FFF|
|ID_|polecenia|0x8000 do 0xDFFF|
|IDC_|funkcje sterowania|od 8 do 0xDFFF|

Przyczyny dotyczące tych limitów zakresu:

- Zgodnie z Konwencją wartość identyfikatora 0 nie jest używana.

- Ograniczenia implementacji systemu Windows ograniczają rzeczywiste identyfikatory zasobów do 0x7FFF.

- Wewnętrzna platforma MFC rezerwuje następujące zakresy:

  - 0x7000 do 0x7FFF (zobacz plik AFXRES. h)

  - 0xE000 do 0xEFFF (zobacz plik AFXRES. h)

  - 16000 do 18000 (patrz afxribbonres. h)

  Te zakresy mogą ulec zmianie w przyszłych implementacjach MFC.

- Kilka poleceń systemu Windows używa zakresu od 0xF000 do 0xFFFF.

- Identyfikatory sterujące od 1 do 7 są zarezerwowane dla kontrolek standardowych, takich jak IDOK i IDCANCEL.

- Zakres 0x8000 za pomocą wartości 0xFFFF dla ciągów jest zastrzeżony dla poleceń menu polecenia.

## <a name="see-also"></a>Zobacz też

[Uwagi techniczne według numeru](../mfc/technical-notes-by-number.md)<br/>
[Uwagi techniczne według kategorii](../mfc/technical-notes-by-category.md)
