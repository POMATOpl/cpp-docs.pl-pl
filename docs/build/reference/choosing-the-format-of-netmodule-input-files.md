---
description: 'Dowiedz się więcej o programie: Wybieranie formatu plików wejściowych modułu.'
title: Wybieranie formatu plików wejściowych .netmodule
ms.date: 11/04/2016
ms.assetid: 4653d1bd-300f-4083-86f5-d1a06f44e61c
ms.openlocfilehash: ed7e448879e983ace7d96cdc7585bf0303378114
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97179209"
---
# <a name="choosing-the-format-of-netmodule-input-files"></a>Wybieranie formatu plików wejściowych .netmodule

Plik MSIL. obj (skompilowany za pomocą [/CLR](clr-common-language-runtime-compilation.md)) może być również używany jako plik modułu.  pliki. obj zawierają metadane i symbole natywne.  . moduły zawierają tylko metadane.

Plik MSIL. obj można przekazać do dowolnego innego kompilatora programu Visual Studio za pomocą opcji kompilatora/addmodule (ale należy pamiętać, że plik. obj stanie się częścią zestawu, i musi być dostarczany z zestawem).  Na przykład Visual C# i Visual Basic mają opcję kompilatora/addmodule.

> [!NOTE]
> W większości przypadków należy przekazać do konsolidatora plik. obj z kompilacji, która utworzyła moduł .NET.  Przekazanie pliku modułu MSIL. dll lub. module do konsolidatora może spowodować LNK1107.

pliki. obj, wraz ze skojarzonymi z nimi plikami. h, do których odwołuje się #include w źródle, umożliwiają aplikacjom C++ korzystanie z natywnych typów w module, a w pliku module.  Jeśli próbujesz przekazać plik. obj do #using, informacje o typach natywnych nie będą dostępne; Zamiast tego #include plik. obj pliku. h.

Inne kompilatory programu Visual Studio mogą korzystać tylko z zarządzanych typów z modułu.

Użyj poniższego elementu, aby określić, czy do konsolidatora MSVC należy użyć pliku.

- Jeśli tworzysz przy użyciu kompilatora programu Visual Studio innego niż Visual C++, program tworzy moduł. webmodule i użyjemy modułu jako dane wejściowe do konsolidatora.

- Jeśli używasz kompilatora MSVC do tworzenia modułów i jeśli moduły zostaną użyte do kompilowania czegoś innego niż biblioteka, Użyj plików obj utworzonych przez kompilator jako dane wejściowe modułu dla konsolidatora; nie należy używać pliku. module jako danych wejściowych.

- Jeśli moduły zostaną użyte do skompilowania natywnej biblioteki (nie zarządzanej), Użyj plików. obj jako danych wejściowych modułu dla konsolidatora i wygeneruj plik biblioteki lib.

- Jeśli moduły zostaną użyte do skompilowania biblioteki zarządzanej, a wszystkie dane wejściowe modułu dla konsolidatora zostaną zweryfikowane (utworzone za pomocą/CLR: safe), Użyj plików. obj jako danych wejściowych modułu dla konsolidatora i wygeneruj plik biblioteki. dll (zestawu) lub. module (modułu).

- Jeśli moduły zostaną użyte do skompilowania biblioteki zarządzanej, a dane wejściowe jednego lub większej liczby modułów do konsolidatora zostaną wygenerowane z zaledwie/CLR, Użyj plików. obj jako danych wejściowych modułu dla konsolidatora i wygeneruj plik. dll (zestaw).  Jeśli chcesz uwidocznić zarządzane typy z biblioteki, a jeśli chcesz, aby aplikacje C++ korzystały z natywnych typów w bibliotece, biblioteka będzie składać się z plików. obj dla modułów składnika biblioteki (należy również dostarczyć pliki. h dla każdego modułu, aby można było odwoływać się do #include z kodu źródłowego).

## <a name="see-also"></a>Zobacz też

[Pliki. module — Wejście konsolidatora](netmodule-files-as-linker-input.md)
