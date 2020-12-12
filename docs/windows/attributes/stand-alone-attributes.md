---
description: Dowiedz się więcej o Stand-Alone atrybutach
title: Atrybuty Stand-Alone (C++ COM)
ms.date: 10/02/2018
helpviewer_keywords:
- standalone attributes
- attributes [C++/CLI], standalone
ms.assetid: 0d72e84e-236c-43b3-ac9a-d9b91fcd6794
ms.openlocfilehash: 39b7356243f9b6ba7c42e907ca0733f59b85961e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97329593"
---
# <a name="stand-alone-attributes"></a>Oddzielne atrybuty

Atrybut autonomiczny nie działa na słowie kluczowym języka C++, ale jest bardziej podobny do wiersza kodu. Autonomiczne instrukcje atrybutów wymagają średnika na końcu wiersza.

## <a name="stand-alone-attribute-list"></a>Lista atrybutów autonomicznych

|Atrybut|Opis|
|---------------|-----------------|
|[cpp_quote](cpp-quote.md)|Emituje określony ciąg bez znaków cudzysłowu do wygenerowanego pliku nagłówkowego.|
|[celnej](custom-cpp.md)|Umożliwia zdefiniowanie własnego atrybutu.|
|[db_command](db-command.md)|Tworzy polecenie OLE DB.|
|[emitidl](emitidl.md)|Określa, czy wszystkie kolejne atrybuty IDL będą przetwarzane i umieszczane w wygenerowanym pliku IDL.|
|[idl_module](idl-module.md)|Określa punkt wejścia w bibliotece DLL.|
|[idl_quote](idl-quote.md)|Umożliwia korzystanie z konstrukcji IDL, które nie są obsługiwane w bieżącej wersji Visual C++ i umożliwiają przekazywanie ich do wygenerowanego pliku IDL.|
|[zaimportować](import.md)|Określa inny plik IDL,. ODL lub. h zawierający definicje, które chcesz odwołać z głównego pliku. idl.|
|[importidl](importidl.md)|Wstawia określony plik IDL do wygenerowanego pliku IDL|
|[importlib](importlib.md)|Sprawia, że typy, które zostały już skompilowane w innej bibliotece typów dostępne dla tworzonej biblioteki typów.|
|[być](include-cpp.md)|Określa co najmniej jeden plik nagłówka do uwzględnienia w wygenerowanym pliku IDL.|
|[includelib —](includelib-cpp.md)|Powoduje, że plik IDL lub h zostanie uwzględniony w wygenerowanym pliku IDL.|
|[library_block](library-block.md)|Umieszcza konstrukcję w bloku biblioteki pliku IDL.|
|[elementu](module-cpp.md)|Definiuje blok biblioteki w pliku IDL.|
|[no_injected_text](no-injected-text.md)|Uniemożliwia kompilatorowi wstrzyknięcie kodu w wyniku użycia atrybutów.|
|[pragma](pragma.md)|Emituje określony ciąg bez znaków cudzysłowu do wygenerowanego pliku IDL.|

## <a name="see-also"></a>Zobacz też

[Atrybuty według użycia](attributes-by-usage.md)
