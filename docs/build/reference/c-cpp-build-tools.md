---
description: 'Dowiedz się więcej na temat: dodatkowe narzędzia do kompilacji MSVC'
title: Dodatkowe narzędzia do kompilacji MSVC
ms.date: 08/28/2019
f1_keywords:
- c.build
helpviewer_keywords:
- builds [C++], C/C++ tools
- tools [C++], build
ms.assetid: 48d9daf4-6bbf-473a-8ce2-bf2923b69f80
ms.openlocfilehash: 41395edcbc2f375b4173f2cff25cbcac581ee5d1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97182648"
---
# <a name="additional-msvc-build-tools"></a>Dodatkowe narzędzia do kompilacji MSVC

Program Visual Studio udostępnia następujące narzędzia wiersza polecenia umożliwiające wyświetlanie danych wyjściowych kompilacji i manipulowanie nimi:

- [LIB.EXE](lib-reference.md) służy do tworzenia biblioteki plików obiektów Common File Format (COFF) i zarządzania nią. Może również służyć do tworzenia plików eksportu i importowania bibliotek w celu odwoływania się do wyeksportowanych definicji.

- [EDITBIN.EXE](editbin-reference.md) służy do modyfikowania plików binarnych COFF.

- [DUMPBIN.EXE](dumpbin-reference.md) wyświetla informacje (takie jak tabela symboli) dotyczące plików binarnych COFF.

- [NMAKE](nmake-reference.md) odczytuje i wykonuje pliki reguł programu make.

- [ERRLOOK](value-edit-control.md), narzędzie do wyszukiwania błędów, pobiera komunikat o błędzie systemu lub komunikatu o błędzie modułu na podstawie wprowadzonej wartości.

- [Xdcmake](xdcmake-reference.md). Narzędzie do przetwarzania plików kodu źródłowego, które zawierają komentarze dokumentacji oznaczone tagami XML.

- [BSCMAKE.EXE](bscmake-reference.md) (dostarczane tylko w celu zapewnienia zgodności z poprzednimi wersjami) kompilują plik informacji o przeglądaniu (BSC), który zawiera informacje o symbolach (klasy, funkcje, dane, makra i typy) w programie. Te informacje są wyświetlane w oknach przeglądania w środowisku deweloperskim. (Plik. bsc można także skompilować w środowisku programistycznym).

Windows SDK ma także kilka narzędzi do kompilacji, w tym [RC.EXE](/windows/win32/menurc/resource-compiler), które kompilator języka C++ wywołuje do kompilowania natywnych zasobów systemu Windows, takich jak okna dialogowe, strony właściwości, mapy bitowe, tabele ciągów i tak dalej.

## <a name="see-also"></a>Zobacz też

[Odwołanie kompilacji C/C++](c-cpp-building-reference.md)<br/>
[Nazwy dekoracyjne](decorated-names.md)<br/>
[Opcje kompilatora MSVC](compiler-options.md)<br/>
[MSVC Opcje konsolidatora](linker-options.md)
