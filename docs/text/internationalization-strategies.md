---
description: 'Dowiedz się więcej o: strategiach wielojęzycznych'
title: Strategie internacjonalizacji
ms.date: 11/04/2016
helpviewer_keywords:
- globalization [C++], character sets
- language-portable code [C++]
- MBCS [C++], internationalization strategies
- Windows API [C++], international programming strategies
- Win32 [C++], international programming strategies
- Unicode [C++], globalizing applications
- character sets [C++], international programming strategies
- localization [C++], character sets
ms.assetid: b09d9854-0709-4b9a-a00c-b0b8bc4199b1
ms.openlocfilehash: 51570a3e340a8af0a9f16f8212aa11f6bf3119b5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331180"
---
# <a name="internationalization-strategies"></a>Strategie internacjonalizacji

W zależności od docelowych systemów operacyjnych i rynków masz kilka różnorodnych strategii:

- Aplikacja używa kodowania Unicode.

   Używasz funkcji specyficznych dla standardu Unicode i wszystkie znaki są 16-bitowym (chociaż można używać znaków ANSI w niektórych częściach programu do specjalnych celów). Biblioteka wykonawcza języka C udostępnia funkcje, makra i typy danych dla programowania tylko w formacie Unicode. MFC jest w pełni włączone w formacie Unicode.

- Aplikacja używa programu MBCS i może być uruchamiana na dowolnej platformie Win32.

   Używasz funkcji specyficznych dla MBCS. Ciągi mogą zawierać znaki jednobajtowe, znaki dwubajtowe lub oba. Biblioteka wykonawcza C udostępnia funkcje, makra i typy danych dla programowania MBCS. MFC jest w pełni MBCS.

- Kod źródłowy aplikacji jest zastosowany do całkowitego przenoszenia — przez ponowną kompilację z symbolem `_UNICODE` lub `_MBCS` zdefiniowanym symbolem, można utworzyć wersje, które używają jednego z nich. Aby uzyskać więcej informacji, zobacz [Mapowanie tekstu ogólnego w używanie TCHAR. h](../text/generic-text-mappings-in-tchar-h.md).

   Używane są w pełni przenośne funkcje, makra i typy danych w czasie wykonywania w języku C. Elastyczność MFC obsługuje dowolne z tych strategii.

Pozostała część tych tematów koncentruje się na tworzeniu całkowicie przenośnego kodu, który można skompilować jako Unicode lub jako MBCS.

## <a name="see-also"></a>Zobacz też

[Unicode i MBCS](../text/unicode-and-mbcs.md)<br/>
[Ustawienia regionalne i strony kodowe](../text/locales-and-code-pages.md)
