---
description: 'Dowiedz się więcej na temat: używanie biblioteki importu i pliku eksportu'
title: Korzystanie z biblioteki importowanej oraz pliku eksportowanego
ms.date: 11/04/2016
helpviewer_keywords:
- circular exports
- import libraries, using
- export files
ms.assetid: 2634256a-8aa5-4495-8c9e-6cde10e4ed76
ms.openlocfilehash: f42a98ebe19cb32fb77964f26c37928776b5b30c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97247023"
---
# <a name="using-an-import-library-and-export-file"></a>Korzystanie z biblioteki importowanej oraz pliku eksportowanego

Gdy program (plik wykonywalny lub biblioteka DLL) eksportuje do innego programu, który również jest importowany z, lub jeśli więcej niż dwa programy są eksportowane do i importowane ze sobą, polecenia służące do łączenia tych programów muszą uwzględniać eksporty cykliczne.

W sytuacji bez eksportu cyklicznego podczas łączenia programu korzystającego z eksportu z innego programu należy określić bibliotekę importu dla programu eksportu. Biblioteka importu dla programu eksportu jest tworzona podczas łączenia tego programu eksportu. W związku z tym należy połączyć program eksportu przed programem importującym. Na przykład jeśli TWO.dll importuje się z ONE.dll, należy najpierw połączyć ONE.dll i pobrać bibliotekę importową o jednej. lib. Następnie podczas łączenia TWO.dll należy określić jedną bibliotekę. lib. Gdy konsolidator tworzy TWO.dll, tworzy również bibliotekę importu, dwie. lib. Użyj dwóch. lib podczas łączenia programów importowanych z TWO.dll.

Jednak w cyklicznej sytuacji eksportowej nie jest możliwe łączenie wszystkich programów zależnych za pomocą bibliotek importu innych programów. W powyższym przykładzie, jeśli TWO.dll również eksportować do ONE.dll, biblioteka importowa dla TWO.dll nie będzie jeszcze istnieć, gdy ONE.dll jest połączona. Gdy istnieją eksporty cykliczne, należy użyć LIB, aby utworzyć bibliotekę importu i wyeksportować plik dla jednego z programów.

Aby rozpocząć, wybierz jeden z programów, dla których chcesz uruchomić LIB. W obszarze polecenia LIB Wyświetl listę wszystkich obiektów i bibliotek dla programu i określ/DEF. Jeśli program używa pliku. def lub specyfikacji/EXPORT, należy również określić te.

Po utworzeniu biblioteki Import (. lib) i pliku eksportu (. EXP) dla programu należy użyć biblioteki importu podczas łączenia innego programu lub programów. LINK tworzy bibliotekę importu dla każdego wyeksportowanego programu, który go kompiluje. Na przykład jeśli uruchomisz LIB na obiektach i eksportach dla ONE.dll, utworzysz jeden. lib i jeden. EXP. Teraz można używać jednego. lib podczas łączenia TWO.dll; Ten krok powoduje także utworzenie biblioteki Imports dwóch. lib.

Na koniec Połącz program z programem. W poleceniu LINK Określ obiekty i biblioteki dla programu, plik. EXP, który został utworzony dla programu, oraz bibliotekę lub biblioteki importowane dla eksportów używanych przez program. Aby kontynuować przykład, polecenie LINK dla ONE.dll zawiera jeden. exp i dwa. lib, a także obiekty i biblioteki, które znajdują się w ONE.dll. Nie określaj pliku. def ani specyfikacji/EXPORT w poleceniu LINK; nie są one zbędne, ponieważ definicje eksportu są zawarte w pliku. EXP. W przypadku łączenia przy użyciu pliku. EXP LINK nie tworzy biblioteki importu, ponieważ zakłada, że został utworzony podczas tworzenia pliku. EXP.

## <a name="see-also"></a>Zobacz też

[Praca z bibliotekami importu i plikami eksportu](working-with-import-libraries-and-export-files.md)
