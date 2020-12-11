---
description: 'Dowiedz się więcej na temat: Określanie stron właściwości'
title: Określanie stron właściwości (ATL)
ms.date: 11/04/2016
helpviewer_keywords:
- ISpecifyPropertyPages method
- property pages, specifying
ms.assetid: ee8678cf-c708-49ab-b0ad-fc2db31f1ac3
ms.openlocfilehash: 171440dde11178c85d1f636874b0b161691cb9cc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97157428"
---
# <a name="specifying-property-pages"></a>Określanie stron właściwości

Podczas tworzenia kontrolki ActiveX często chcesz skojarzyć ją ze stronami właściwości, których można użyć do ustawiania właściwości formantu. Kontenery formantów używają `ISpecifyPropertyPages` interfejsu, aby dowiedzieć się, które strony właściwości mogą być używane do ustawiania właściwości kontrolki. Należy zaimplementować ten interfejs na kontrolce.

Aby zaimplementować `ISpecifyPropertyPages` przy użyciu biblioteki ATL, wykonaj następujące czynności:

1. Utwórz klasę z [ISpecifyPropertyPagesImpl](../atl/reference/ispecifypropertypagesimpl-class.md).

1. Dodaj wpis do `ISpecifyPropertyPages` mapy com klasy.

1. Dodaj wpis [PROP_PAGE](reference/property-map-macros.md#prop_page) do mapy właściwości dla każdej strony skojarzonej z kontrolką.

> [!NOTE]
> Podczas generowania kontrolki standardowej przy użyciu [Kreatora kontrolki ATL](../atl/reference/atl-control-wizard.md)należy dodać tylko wpisy PROP_PAGE do mapy właściwości. Kreator generuje kod niezbędny dla innych kroków.

Prawidłowo działające kontenery będą wyświetlały określone strony właściwości w tej samej kolejności co PROP_PAGE wpisów na mapie właściwości. Ogólnie rzecz biorąc, należy umieścić standardowe wpisy strony właściwości po wpisach dla stron niestandardowych na mapie właściwości, aby użytkownicy widzieli najpierw strony specyficzne dla kontrolki.

## <a name="example"></a>Przykład

W poniższej klasie kontrolki Calendar jest używany `ISpecifyPropertyPages` interfejs do informowania kontenerów, których właściwości można ustawić za pomocą niestandardowej strony daty i koloru strony.

[!code-cpp[NVC_ATL_Windowing#72](../atl/codesnippet/cpp/specifying-property-pages_1.h)]

## <a name="see-also"></a>Zobacz też

[Strony właściwości](../atl/atl-com-property-pages.md)<br/>
[Przykład ATLPages](../overview/visual-cpp-samples.md)
