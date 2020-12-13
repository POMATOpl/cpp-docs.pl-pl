---
description: 'Dowiedz się więcej o: tekst i ciągi w Visual C++'
title: Tekst i ciągi w programie Visual C++
ms.date: 11/04/2016
helpviewer_keywords:
- globalization [C++], character sets
- programming [C++], international
- multiple language support [C++]
- Unicode [C++]
- international applications [C++], about international applications
- portability [C++]
- translation [C++], character sets
- non-European characters [C++]
- character sets [C++]
- globalization [C++]
- Japanese characters [C++]
- Kanji character support [C++]
- local character sets [C++]
- ASCII characters [C++]
- character sets [C++], about character sets
- localization [C++], character sets
- translating code [C++]
- localization [C++]
- character sets [C++], non-European
- portability [C++], character sets
- MBCS [C++], international programming
ms.assetid: a1bb27ac-abe5-4c6b-867d-f761d4b93205
ms.openlocfilehash: 3b77df006e095871d11fb3bfbc3d83b081d6052f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335731"
---
# <a name="text-and-strings-in-visual-c"></a>Tekst i ciągi w programie Visual C++

Ważnym aspektem opracowywania aplikacji na rynkach międzynarodowych jest odpowiednia reprezentacja lokalnych zestawów znaków. Zestaw znaków ASCII definiuje znaki w zakresie od 0x00 do 0x7F. Istnieją inne zestawy znaków, głównie europejskie, które definiują znaki w zakresie od 0x00 do 0x7F identycznie z zestawem znaków ASCII, a także definiują rozszerzony zestaw znaków z 0x80 na 0xFF. W ten sposób 8-bitowy zestaw znaków jednobajtowych (SBCS) jest wystarczający do reprezentowania zestawu znaków ASCII, a także zestawów znaków dla wielu języków europejskich. Jednak niektóre nieeuropejskie zestawy znaków, takie jak japoński Kanji, zawierają wiele więcej znaków niż schemat kodowania jednobajtowego może reprezentować i dlatego wymagać kodowania zestawu znaków wielobajtowych (MBCS).

## <a name="in-this-section"></a>W tej sekcji

[Unicode i MBCS](../text/unicode-and-mbcs.md)<br/>
Omawia Visual C++ obsługę programowania Unicode i MBCS.

[Obsługa formatu Unicode](../text/support-for-unicode.md)<br/>
Opisuje Unicode, specyfikację do obsługi wszystkich zestawów znaków, w tym zestawów znaków, które nie mogą być reprezentowane w pojedynczym bajcie.

[Obsługa zestawów znaków wielobajtowych (MBCS)](../text/support-for-multibyte-character-sets-mbcss.md)<br/>
Omawia MBCS, alternatywę dla Unicode dla pomocniczych zestawów znaków, takich jak japoński i chiński, które nie mogą być reprezentowane w pojedynczym bajcie.

[Mapowania tekstu ogólnego w używanie TCHAR. h](../text/generic-text-mappings-in-tchar-h.md)<br/>
Zapewnia mapowanie tekstu ogólnego specyficznego dla firmy Microsoft dla wielu typów danych, procedur i innych obiektów.

[Instrukcje: konwertowanie różnych typów ciągów](../text/how-to-convert-between-various-string-types.md)<br/>
Pokazuje, w jaki sposób konwertować różne Visual C++ typy ciągów na inne ciągi.

## <a name="related-sections"></a>Sekcje pokrewne

[Internacjonalizacja](../c-runtime-library/internationalization.md)<br/>
W tym artykule omówiono obsługę międzynarodową w bibliotece wykonawczej C.

[Przykłady międzynarodowe](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/International)<br/>
Zawiera łącza do przykładów demonstrujących informacje o zastosowaniach wielojęzycznych w Visual C++.

[Ciągi języka i kraju/regionu](../c-runtime-library/locale-names-languages-and-country-region-strings.md)<br/>
Zawiera ciągi języka i kraju/regionu w bibliotece wykonawczej C.
