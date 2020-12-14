---
description: 'Dowiedz się więcej na temat: błąd krytyczny C1010'
title: Błąd krytyczny C1010
ms.date: 09/03/2019
f1_keywords:
- C1010
helpviewer_keywords:
- C1010
ms.assetid: dfd035f1-a7a2-40bc-bc92-dc4d7f456767
ms.openlocfilehash: 2c6d57b2390f727e37d546d7077217e25db40fef
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97262532"
---
# <a name="fatal-error-c1010"></a>Błąd krytyczny C1010

> nieoczekiwany koniec pliku podczas wyszukiwania prekompilowanego nagłówka. Czy zapomnisz dodać "#include *name*" do źródła?

## <a name="remarks"></a>Uwagi

Plik dołączany określony przez [/Yu](../../build/reference/yu-use-precompiled-header-file.md) nie znajduje się w pliku źródłowym. Ta opcja jest domyślnie włączona w wielu typach projektów Visual Studio C++. Domyślny plik dołączania określony przez tę opcję to *PCH. h* lub *stdafx. h* w programie Visual Studio 2017 i jego wcześniejszych wersjach.

W środowisku programu Visual Studio Użyj jednej z następujących metod, aby rozwiązać ten problem:

- Upewnij się, że plik nagłówkowy *PCH. h* ani plik źródłowy *PCH. cpp* nie został przypadkowo usunięty, nie zmieniono jego nazwy ani nie został usunięty z bieżącego projektu. (W starszych projektach te pliki mogą mieć nazwę *stdafx. h* i *stdafx. cpp*).

- Upewnij się, że plik nagłówka *PCH. h* lub *stdafx. h* jest zawarty przed wszelkimi innymi dyrektywami kodu lub preprocesora w plikach źródłowych. (W programie Visual Studio ten plik nagłówkowy jest określony przez **prekompilowaną właściwość projektu pliku nagłówkowego** ).

- Można wyłączyć użycie prekompilowanego nagłówka. Wyłączenie prekompilowanych nagłówków może poważnie wpłynąć na wydajność kompilacji.

### <a name="to-turn-off-precompiled-headers"></a>Aby wyłączyć prekompilowane nagłówki

Aby wyłączyć użycie prekompilowanego nagłówka w projekcie, wykonaj następujące kroki:

1. W oknie **Eksplorator rozwiązań** kliknij prawym przyciskiem myszy nazwę projektu, a następnie wybierz polecenie **Właściwości** , aby otworzyć okno dialogowe **strony właściwości** projektu.

1. Z listy rozwijanej **Konfiguracja** wybierz pozycję **wszystkie konfiguracje**.

1. Wybierz   >  stronę właściwości  >  **prekompilowanego nagłówka** C/C++ właściwości konfiguracji.

1. Na liście właściwości wybierz listę rozwijaną dla właściwości **prekompilowanego nagłówka** , a następnie wybierz opcję **nie używa prekompilowanych nagłówków**. Wybierz **przycisk OK** , aby zapisać zmiany.

1. W oknie **Eksplorator rozwiązań** kliknij prawym przyciskiem myszy plik źródłowy *PCH. cpp* w projekcie. (W starszych projektach plik może mieć nazwę *stdafx. cpp*). Wybierz opcję **Wyklucz z projektu** , aby usunąć go z kompilacji.

1. Użyj polecenia menu **Kompiluj**  >  **czyste rozwiązanie** dla każdej kompilacji, którą tworzysz, aby usunąć wszystkie *Project_Name pliki. PCH* do pośrednich katalogów kompilacji.

## <a name="see-also"></a>Zobacz też

[Wstępnie skompilowane pliki nagłówkowe](../../build/creating-precompiled-header-files.md)\
[/YC (Utwórz prekompilowany plik nagłówkowy)](../../build/reference/yc-create-precompiled-header-file.md)\
[/Yu (Korzystaj z prekompilowanego pliku nagłówka)](../../build/reference/yu-use-precompiled-header-file.md)
