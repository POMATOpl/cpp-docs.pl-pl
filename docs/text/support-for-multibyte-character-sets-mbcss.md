---
description: 'Dowiedz się więcej o: Obsługa zestawów znaków wielobajtowych (zestawy MBCS)'
title: Obsługa zestawów znaków wielobajtowych (zestawy MBCS)
ms.date: 11/04/2016
helpviewer_keywords:
- MBCS [C++], about MBCS
- character sets [C++], multibyte
- multibyte characters [C++]
- MBCS [C++]
ms.assetid: b498733c-a1e1-45e3-8f26-d6da3cb5f2dd
ms.openlocfilehash: 8ab6af7aa77942b39785faf68ea6a530867abff8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335767"
---
# <a name="support-for-multibyte-character-sets-mbcss"></a>Obsługa zestawów znaków wielobajtowych (zestawy MBCS)

Zestawy znaków wielobajtowych (zestawy MBCS) to starsze podejście do obsługi zestawów znaków, takich jak japoński i chiński, które nie mogą być reprezentowane w pojedynczym bajcie. W przypadku tworzenia nowych aplikacji należy używać standardu Unicode dla wszystkich ciągów tekstowych, z wyjątkiem takich ciągów systemu, które nie są widoczne dla użytkowników końcowych. MBCS jest starszą technologią i nie jest zalecana w przypadku nowych rozwiązań programistycznych.

Najbardziej powszechną implementacją MBCS są zestawy znaków dwubajtowych (DBCS). Ogólnie Visual C++, a MFC w szczególności jest w pełni włączone dla DBCS.

Aby zapoznać się z przykładami, zobacz pliki kodu źródłowego MFC.

W przypadku platform używanych na rynkach, których Języki używają dużych zestawów znaków, Najlepsza alternatywą dla standardu Unicode jest MBCS. MFC obsługuje MBCS przy użyciu typów danych internationalizable i funkcji czasu wykonywania języka C. Należy to zrobić w kodzie.

W obszarze MBCS znaki są kodowane w 1 lub 2 bajtach. W przypadku znaków 2-bajtowych pierwszy lub potencjalny bajt wiodący sygnalizuje, że oba te i następujące bajty mają być interpretowane jako jeden znak. Pierwszy bajt pochodzi z zakresu kodów zastrzeżonego do użycia jako bajty potencjalnego klienta. Które zakresy bajtów mogą być potencjalnymi bajtami, zależy od używanej strony kodowej. Na przykład strona kodowa Japońska 932 używa zakresu 0x81 za pośrednictwem 0x9F jako bajtów potencjalnych, ale Koreańska strona kodowa 949 używa innego zakresu.

Rozważ wszystkie następujące kwestie w programowaniu MBCS.

Znaki MBCS w środowisku MBCS znaki mogą pojawić się w ciągach, takich jak nazwy plików i katalogów.

### <a name="editing-operations"></a>Edytowanie operacji

Operacje edycji w aplikacjach MBCS powinny działać na znakach, a nie w bajtach. Karetka nie powinna dzielić znaku, klawisz **Strzałka w prawo** powinna przenieść jeden znak w prawo itd. **Usuń** należy usunąć znak; Operacja **Cofnij** powinna ponownie wstawić.

### <a name="string-handling"></a>Obsługa ciągów

W aplikacji, która używa MBCS, obsługa ciągów stanowi specjalne problemy. Znaki obu szerokości są mieszane w pojedynczym ciągu; w związku z tym należy pamiętać o sprawdzeniu potencjalnych bajtów.

### <a name="run-time-library-support"></a>Obsługa bibliotek w czasie wykonywania

Biblioteka wykonawcza C i MFC obsługują programowanie jednobajtowe, MBCS i Unicode. Ciągi jednobajtowe są przetwarzane z `str` rodziną funkcji czasu wykonywania, ciągi MBCS są przetwarzane przy użyciu odpowiednich `_mbs` funkcji, a ciągi Unicode są przetwarzane przy użyciu odpowiednich `wcs` funkcji. Implementacje funkcji składowych klasy MFC używają przenośnych funkcji czasu wykonywania, które mapują w odpowiednich przypadkach do normalnej `str` rodziny funkcji, funkcji MBCS lub funkcji Unicode, zgodnie z opisem w "przenośność MBCS/Unicode".

### <a name="mbcsunicode-portability"></a>Przenośność MBCS/Unicode

Korzystając z pliku nagłówkowego używanie TCHAR. h, można tworzyć aplikacje z jednym bajtem, MBCS i Unicode z tych samych źródeł. Używanie TCHAR. h definiuje makra poprzedzone *_tcs* , które mapują do `str` , `_mbs` lub, w `wcs` zależności od potrzeb. Aby skompilować MBCS, zdefiniuj symbol `_MBCS` . Aby skompilować kod Unicode, zdefiniuj symbol `_UNICODE` . Domyślnie program `_UNICODE` jest zdefiniowany dla aplikacji MFC. Aby uzyskać więcej informacji, zobacz [Mapowanie tekstu ogólnego w używanie TCHAR. h](../text/generic-text-mappings-in-tchar-h.md).

> [!NOTE]
> Zachowanie jest niezdefiniowane, jeśli zdefiniujesz jednocześnie `_UNICODE` i `_MBCS` .

Pliki nagłówkowe Mbctype. h i mbstring. h definiują funkcje i makra specyficzne dla MBCS, które mogą być potrzebne w niektórych przypadkach. Na przykład `_ismbblead` informuje, czy określony bajt w ciągu jest bajtem wiodącym.

W przypadku portów międzynarodowych należy zakodować program za pomocą zestawów znaków [Unicode](../text/support-for-unicode.md) lub wielobajtowych (zestawy MBCS).

## <a name="what-do-you-want-to-do"></a>Co chcesz zrobić?

- [Włącz MBCS w moim programie](../text/international-enabling.md)

- [Włącz zarówno kod Unicode, jak i MBCS w moim programie](../text/internationalization-strategies.md)

- [Korzystanie z MBCS do tworzenia międzynarodowego programu](../text/mbcs-programming-tips.md)

- [Zobacz Podsumowanie programowania MBCS](../text/mbcs-programming-tips.md)

- [Dowiedz się więcej o mapowaniu tekstu ogólnego dla przenośności szerokości bajtów](../text/generic-text-mappings-in-tchar-h.md)

## <a name="see-also"></a>Zobacz też

[Tekst i ciągi](../text/text-and-strings-in-visual-cpp.md)<br/>
[Obsługa MBCS w programie Visual C++](../text/mbcs-support-in-visual-cpp.md)
