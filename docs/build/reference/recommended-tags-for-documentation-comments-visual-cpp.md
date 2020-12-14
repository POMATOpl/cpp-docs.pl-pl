---
description: 'Dowiedz się więcej na temat: zalecane Tagi komentarzy do dokumentacji'
title: Zalecane Tagi dla komentarzy do dokumentacji (Komentarze w dokumentacji C++)
ms.date: 11/04/2016
ms.assetid: 6548e798-5235-4a38-9482-bdc7b88f40a9
ms.openlocfilehash: 34bae4043231abed87770aec252303bd99707afe
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97225352"
---
# <a name="recommended-tags-for-documentation-comments"></a>Zalecane tagi przeznaczone do komentarzy dokumentacji

Kompilator MSVC będzie przetwarzać Komentarze do dokumentacji w kodzie i tworzy plik. xdc dla każdego jednostka kompilacji, a xdcmake.exe będzie przetwarzać pliki XDC do pliku. XML. Przetwarzanie pliku. XML w celu utworzenia dokumentacji jest szczegółami, które muszą zostać zaimplementowane w Twojej lokacji.

Tagi są przetwarzane na konstrukcjach, takich jak typy i elementy członkowskie typu.

Tagi muszą występować bezpośrednio przed typami lub elementami członkowskimi.

> [!NOTE]
> Komentarzy do dokumentacji nie można zastosować do przestrzeni nazw lub w definicji poza wierszem dla właściwości i zdarzeń; Komentarze dokumentacji muszą być zgodne z deklaracjami w klasie.

Kompilator będzie przetwarzać dowolny tag, który jest prawidłowym kodem XML. Poniższe Tagi zapewniają powszechnie używane funkcje w dokumentacji użytkownika:

[`<c>`](c-visual-cpp.md)
[`<code>`](code-visual-cpp.md)
[`<example>`](example-visual-cpp.md)
[`<exception>`](exception-visual-cpp.md)<sup></sup> 
 1 [`<include>`](include-visual-cpp.md) <sup></sup> 
 [`<list>`](list-visual-cpp.md) 1 
 [`<para>`](para-visual-cpp.md) 
 [`<param>`](param-visual-cpp.md) <sup></sup> 
 1 [`<paramref>`](paramref-visual-cpp.md) <sup></sup> 
 1 [`<permission>`](permission-visual-cpp.md) <sup></sup> 
 [`<remarks>`](remarks-visual-cpp.md) 1 
 [`<returns>`](returns-visual-cpp.md) 
 [`<see>`](see-visual-cpp.md) <sup></sup> 
 1 [`<seealso>`](seealso-visual-cpp.md) <sup>1</sup>
[`<summary>`](summary-visual-cpp.md)
[`<value>`](value-visual-cpp.md)

1. Kompilator weryfikuje składnię.

W bieżącej wersji kompilator MSVC nie obsługuje `<paramref>` tagu, który jest obsługiwany przez inne kompilatory programu Visual Studio. Visual C++ może obsługiwać `<paramref>` w przyszłych wydaniach.

## <a name="see-also"></a>Zobacz też

[Dokumentacja XML](xml-documentation-visual-cpp.md)
