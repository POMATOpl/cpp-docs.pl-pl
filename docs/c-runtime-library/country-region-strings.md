---
description: 'Dowiedz się więcej o: ciągi kraju/regionu'
title: Ciągi Country-Region
ms.date: 11/04/2016
helpviewer_keywords:
- country/region strings
ms.assetid: 5baf0ccf-0d9b-40dc-83bd-323705287930
ms.openlocfilehash: d865c3a6a8f505eea7878df379db30224511d51c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97195700"
---
# <a name="countryregion-strings"></a>Ciągi kraj/region

Ciągi kraju i regionu można łączyć z ciągiem języka, aby utworzyć specyfikację ustawień regionalnych dla `setlocale` funkcji, `_wsetlocale` , `_create_locale` i `_wcreate_locale` . W przypadku list nazw krajów i regionów obsługiwanych przez różne wersje systemu operacyjnego Windows Zapoznaj się z kolumnami **Language**, **Location** i **Language tag** tabeli w [dodatku A: zachowanie produktu](/openspecs/windows_protocols/ms-lcid/a9eac961-e77d-41a6-90a5-ce1a8b0cdb9c) w \[ MS-LCID]: informacje o identyfikatorze kodu języka (LCID) systemu Windows. Przykład kodu, który wylicza dostępne nazwy ustawień regionalnych i powiązane wartości, można znaleźć w temacie [NLS: Omówienie interfejsów API opartych na nazwach](/windows/win32/intl/nls--name-based-apis-sample).

## <a name="additional-supported-country-and-region-strings"></a>Dodatkowe obsługiwane ciągi krajów i regionów

Implementacja biblioteki wykonawczej Microsoft C obsługuje również następujące dodatkowe ciągi kraju/regionu i skróty:

|Ciąg kraju/regionu|Skrót|Równoważna Nazwa ustawień regionalnych|
|----------------------------|------------------|----------------------------|
|USA|USA|en-US|
|Brytanii|GBR|en-GB|
|Chinach|CHN|zh-CN|
|Czeski|CZE|cs-CZ|
|Anglii|GBR|en-GB|
|Wielka Brytania|GBR|en-GB|
|Holland|NLD|nl-NL|
|Hongkong|HKG|zh-HK|
|Nowa Zelandia|NZL|EN-NZ|
|NZ|NZL|EN-NZ|
|Chiny (PR)|CHN|zh-CN|
|PR — Chiny|CHN|zh-CN|
|Portoryko — Portoryko|PRI|ES — PR|
|Słowacki|SVK|sk-SK|
|Republika Południowej Afryki|ZAF|AF — za|
|Korea Południowa|KOR|ko-KR|
|Republika Południowej Afryki|ZAF|AF — za|
|Korea Południowa|KOR|ko-KR|
|Trinidad & Tobago|Aby|pl-TT|
|Południowe Zjednoczone Królestwo|GBR|en-GB|
|Zjednoczone Królestwo|GBR|en-GB|
|Stany Zjednoczone|USA|en-US|
|Prześlij|USA|en-US|

## <a name="see-also"></a>Zobacz też

[Nazwy lokalne, Języki i ciągi kraj/region](../c-runtime-library/locale-names-languages-and-country-region-strings.md)<br/>
[Ciągi języka](../c-runtime-library/language-strings.md)<br/>
[setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)<br/>
[_create_locale, _wcreate_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md)
