---
description: 'Dowiedz się więcej na temat: TN023: standardowe zasoby MFC'
title: 'TN023: standardowe zasoby MFC'
ms.date: 11/04/2016
helpviewer_keywords:
- resources [MFC]
- TN023
- standard resources
ms.assetid: 60af8415-c576-4c2f-a711-ca5da0b9a1f2
ms.openlocfilehash: 8a78a029d67920b7cd711be6200ccced86d243e3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97215771"
---
# <a name="tn023-standard-mfc-resources"></a>TN023: standardowe zasoby MFC

Ta Uwaga opisuje zasoby standardowe dostarczone z programem i wymagające biblioteki MFC.

## <a name="standard-resources"></a>Zasoby standardowe

MFC oferuje dwie kategorie wstępnie zdefiniowanych zasobów, których można używać w aplikacji: zasoby clip art i standardowe zasoby struktury.

Zasoby Clip Art to dodatkowe zasoby, od których nie zależy platforma, ale które można chcieć dodać do interfejsu użytkownika aplikacji. Następujące zasoby clipart są zawarte w ogólnym przykładowym elemencie [clipart](../overview/visual-cpp-samples.md)MFC:

- Common. rc: pojedynczy plik zasobów zawierający:

  - Duża kolekcja ikon, które reprezentują różnorodne zadania biznesowe i przetwarzania danych.

  - Kilka typowych kursorów (Zobacz również plik AFXRES. RC).

  - Mapa bitowa paska narzędzi, która zawiera kilka przycisków paska narzędzi.

  - Zasoby bitmap i ikon, które są używane przez Commdlg.dll.

- Wskaż. rc: zawiera zasoby ciągu dla kluczowych wskaźników stanu, takich jak "CAP" dla blokady Caps Lock.

- Monits. rc: zawiera menu z wierszem wiersza polecenia dla każdego ze wstępnie zdefiniowanych poleceń, na przykład "Utwórz nowy dokument" dla ID_FILE_NEW.

- COMMDLG. rc: Visual C++ zgodny plik. RC, który zawiera standardowe szablony okien dialogowych COMMDLG.

Standardowe zasoby platformy to zasoby ze zdefiniowanymi przez AFX identyfikatorami, od których zależy struktura dla implementacji wewnętrznej. Rzadko trzeba będzie zmienić te zasoby zdefiniowane przez AFX. W takim przypadku należy postępować zgodnie z procedurą przedstawioną w dalszej części tego tematu.

W katalogu MFC\INCLUDE znajdują się następujące zasoby platformy:

- Plik AFXRES. rc: typowe zasoby używane przez platformę.

- Afxprint. rc: zasoby specyficzne dla drukowania.

- Afxolecl. rc: zasoby specyficzne dla aplikacji klienckich OLE.

- Afxolev. rc: zasoby specyficzne dla pełnych aplikacji serwera OLE.

## <a name="using-clip-art-resources"></a>Korzystanie z zasobów Clip-Art

#### <a name="to-use-a-clip-art-binary-resource"></a>Aby użyć zasobu binarnego clipart

1. Otwórz plik zasobów aplikacji w Visual C++.

1. Otwórz Common. rc. Ten plik zawiera wszystkie binarne zasoby clipart. Może to potrwać pewien czas, ponieważ jest kompilowany wspólny plik. rc.

1. Przytrzymaj klawisz CTRL podczas przeciągania zasobów, których chcesz użyć ze wspólnego. RC do pliku zasobów aplikacji.

Aby użyć innych zasobów clipart, wykonaj te same czynności. Jedyną różnicą jest to, że zostanie otwarty odpowiedni plik. RC zamiast Common. rc.

> [!NOTE]
> Należy uważać, aby nie przypadkowo przenieść zasobów z wspólnego. rc. Jeśli przytrzymaj klawisz CTRL podczas przeciągania zasobów, zostanie utworzona kopia. Jeśli podczas przeciągania nie zatrzymasz naciśniętego klawisza CTRL, zasoby zostaną przeniesione. Jeśli obawiasz się, że możesz przypadkowo wprowadzić zmiany w pliku Common. RC, kliknij przycisk "nie", gdy zostanie wyświetlony monit o zapisanie zmian w polu Common. rc.

> [!NOTE]
> Pliki zasobów. RC mają specjalne Zasoby TEXTINCLUDE, które uniemożliwią przypadkowe zapisanie w standardowych plikach. rc.

### <a name="customizing-standard-framework-resources"></a>Dostosowywanie standardowych zasobów platformy

Standardowe zasoby platformy są zwykle dołączane do aplikacji za pomocą polecenia #include w pliku zasobów aplikacji. AppWizard wygeneruje plik zasobów. Ten plik zawiera odpowiednie standardowe zasoby platformy, w zależności od wybranych opcji AppWizard. Możesz przeglądać, dodawać lub usuwać zasoby, które są uwzględniane przez zmianę dyrektyw czasu kompilacji. W tym celu otwórz menu **zasobów** , a następnie wybierz pozycję **zestaw zawiera**. Zapoznaj się z pozycją Edytuj "dyrektywy czasu kompilacji". Na przykład:

```
#include "afxres.rc"
#include "afxprint.rc"
```

Najbardziej typowym przypadkiem dostosowywania standardowych zasobów platformy jest dodanie lub usunięcie dodatkowych dołączeń do drukowania, klienta OLE i obsługi serwera OLE.

W niektórych rzadkich przypadkach warto dostosować zawartość standardowych zasobów platformy dla danej aplikacji, a nie tylko dodać i usunąć cały plik. W poniższych krokach pokazano, jak ograniczyć liczbę uwzględnionych zasobów:

##### <a name="to-customize-the-contents-of-a-standard-resource-file"></a>Aby dostosować zawartość standardowego pliku zasobów

1. Otwórz plik zasobów w Visual C++.

1. Za pomocą polecenia zestaw zasobów zawiera polecenie, Usuń `#include` dla standardowego pliku. RC, który chcesz dostosować. Na przykład, aby dostosować pasek narzędzi podglądu wydruku, Usuń `#include "afxprint.rc"` linię.

1. Otwórz odpowiednie pliki zasobów standardowych w programie MFC\INCLUDE. Zgodnie z przykładem znajdującym się wcześniej w tym temacie, odpowiedni plik to MFC\Include\Aafxprint.rc

1. Skopiuj wszystkie zasoby z pliku standardowego. RC do pliku zasobów aplikacji.

1. Zmodyfikuj kopię zasobów standardowych w pliku zasobów aplikacji.

> [!NOTE]
> Nie należy modyfikować zasobów bezpośrednio w standardowych plikach. rc. Spowoduje to modyfikację zasobów dostępnych w każdej aplikacji, a nie tylko w tym, nad którym pracujesz.

## <a name="see-also"></a>Zobacz też

[Uwagi techniczne według numeru](../mfc/technical-notes-by-number.md)<br/>
[Uwagi techniczne według kategorii](../mfc/technical-notes-by-category.md)
