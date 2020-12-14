---
description: 'Dowiedz się więcej na temat: ciągi języka'
title: Ciągi języka
ms.date: 11/04/2016
helpviewer_keywords:
- language strings
ms.assetid: bbee63b1-af0b-4e44-9eaf-dd3e265c05fd
ms.openlocfilehash: 077a440981c9e39e87356310c40ae9b249d4662e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97246581"
---
# <a name="language-strings"></a>Ciągi języka

Funkcje [setlocale](../c-runtime-library/reference/setlocale-wsetlocale.md) i [_create_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md) mogą korzystać z obsługiwanych języków NLS API systemu Windows w systemach operacyjnych, które nie korzystają ze strony kodowej Unicode. Aby uzyskać listę obsługiwanych języków według wersji systemu operacyjnego, zobacz [dodatek a: zachowanie produktu](/openspecs/windows_protocols/ms-lcid/a9eac961-e77d-41a6-90a5-ce1a8b0cdb9c) w \[ MS-LCID]: dokumentacja identyfikatora kodu języka (LCID) systemu Windows. Ciąg języka może być dowolną wartością w kolumnach **Język** i **Język** listy obsługiwanych języków. Przykład kodu, który wylicza dostępne nazwy ustawień regionalnych i powiązane wartości, można znaleźć w temacie [NLS: Omówienie interfejsów API opartych na nazwach](/windows/win32/intl/nls--name-based-apis-sample).

## <a name="additional-supported-language-strings"></a>Dodatkowe obsługiwane ciągi języka

Implementacja biblioteki wykonawczej Microsoft C obsługuje również następujące ciągi języka:

|Ciąg języka|Równoważna Nazwa ustawień regionalnych|
|---------------------|----------------------------|
|Samoa|en-US|
|angielski (amerykański)|en-US|
|amerykański (angielski)|en-US|
|służb|en-AU|
|Belgii|NL-to|
|Ustawa|EN-CA|
|chh|zh-HK|
|rozkład Chi|zh-SG|
|Chiński|zh|
|Chiński — Hongkong|zh-HK|
|Chiński (uproszczony)|zh-CN|
|Chiński (Singapur)|zh-SG|
|Chiński (tradycyjny)|zh-TW|
|holenderski — belgijski|NL-to|
|angielski (amerykański)|en-US|
|angielski (Australia)|en-AU|
|angielski — Belize|pl-BZ|
|angielski — może|EN-CA|
|angielski — Karaiby|pl-029|
|angielski — wygasnąć|EN-IE|
|Angielski — Jamajka|pl-JM|
|angielski — NZ|EN-NZ|
|angielski (Republika Południowej Afryki)|pl-za|
|angielski — Trynidad y Tobago|pl-TT|
|angielski — Zjednoczone Królestwo|en-GB|
|angielski — Stany Zjednoczone|en-US|
|angielski (USA)|en-US|
|francuski — belgijski|fr — należy|
|francuski — Kanada|fr — CA|
|Francuski — Luksemburg|fr — LU|
|francuski — szwajcarski|fr-CH|
|niemiecki — austriacki|de-AT|
|niemiecki — Lichtenstein|de-LI|
|niemiecki — Luksemburg|de-LU|
|niemiecki (Szwajcaria)|Usuń CH|
|Irlandzki — angielski|EN-IE|
|włoski (szwajcarski)|IT-CH|
|Norweski|nie|
|norweski (Bokmal)|nb-NO|
|norweski — nynorsk|NN-NO|
|portugalski (Brazylia)|pt-BR|
|hiszpański (Argentyna)|ES-AR|
|Hiszpański — Boliwia|ES — BO|
|hiszpański — Chile|ES — CL|
|hiszpański — Kolumbia|ES — CO|
|hiszpański — Kostaryka|ES — CR|
|hiszpański — Dominikana|ES-DO|
|hiszpański (Ekwador)|ES — we|
|hiszpański — Salwador|ES — SV|
|Hiszpański — Gwatemala|ES-GT|
|hiszpański — Honduras|ES — HN|
|hiszpański (Meksyk)|es — MX|
|hiszpański — nowoczesny|es-ES|
|hiszpański — Nikaragua|ES — NI|
|hiszpański — Panama|ES — PA|
|Hiszpański — Paragwaj|ES — PR|
|Hiszpański — Peru|ES — PE|
|hiszpański — Portoryko|ES — PR|
|hiszpański — Urugwaj|ES — UY|
|hiszpański — Wenezuela|ES — VE|
|szwedzki — Finlandia|OHR-FI|
|przewoźnik|Usuń CH|
|Południowe Zjednoczone Królestwo|en-GB|
|Prześlij|en-US|
|poniżej|en-US|

## <a name="see-also"></a>Zobacz też

[Nazwy lokalne, Języki i ciągi kraj/region](../c-runtime-library/locale-names-languages-and-country-region-strings.md)<br/>
[Ciągi kraju/regionu](../c-runtime-library/country-region-strings.md)<br/>
[setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)<br/>
[_create_locale, _wcreate_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md)
