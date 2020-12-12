---
description: 'Dowiedz się więcej na temat: błąd kompilacji projektu PRJ0003'
title: Błąd PRJ0003 kompilacji projektu
ms.date: 11/04/2016
f1_keywords:
- PRJ0003
helpviewer_keywords:
- PRJ0003
ms.assetid: fc5a84bb-c6d3-41d6-8dd6-475455820778
ms.openlocfilehash: cefd56e1d11da77f288333fb0e1f9c10ef684d12
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97119411"
---
# <a name="project-build-error-prj0003"></a>Błąd PRJ0003 kompilacji projektu

> Wystąpił błąd podczas duplikowania "*wiersz polecenia*".

Polecenie *wiersza polecenia* utworzone na podstawie danych wejściowych w oknie dialogowym **strony właściwości** zwróciło kod błędu, ale w oknie **danych wyjściowych** nie są wyświetlane żadne informacje.

Możliwe przyczyny tego błędu to:

- Projekt zależy od serwera ATL. Począwszy od programu Visual Studio 2008, serwer ATL nie jest już uwzględniony jako część programu Visual Studio, ale został wystawiony jako projekt udostępnionego źródła w CodePlex. Aby pobrać kod źródłowy i narzędzia programu ATL Server, przejdź do [biblioteki i narzędzi serwera ATL](https://go.microsoft.com/fwlink/p/?linkid=81979).

- Niskie zasoby systemowe. Zamknij niektóre aplikacje, aby rozwiązać ten problem.

- Niewystarczające uprawnienia zabezpieczeń. Sprawdź, czy masz wystarczające uprawnienia zabezpieczeń.

- Ścieżki plików wykonywalnych określone w **katalogach VC + +** nie zawierają ścieżki do narzędzia, które próbujesz uruchomić. Aby uzyskać więcej informacji, zobacz [Ustawianie właściwości kompilatora i Build](../../build/working-with-project-properties.md)

- W przypadku projektów pliku reguł programu make brakuje polecenia do uruchomienia w **wierszu polecenia kompilacji** lub **ponownie skompiluj wiersz polecenia**.

## <a name="see-also"></a>Zobacz też

[Błędy i ostrzeżenia kompilacji projektu (PRJxxxx)](../../error-messages/tool-errors/project-build-errors-and-warnings-prjxxxx.md)
