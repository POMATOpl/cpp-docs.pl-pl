---
description: 'Dowiedz się więcej na temat: Tworzenie szablonu dokumentu'
title: Tworzenie szablonu dokumentu
ms.date: 11/04/2016
helpviewer_keywords:
- document templates [MFC]
- constructors [MFC], document template
- document templates [MFC], creating
- MFC, document templates
- templates [MFC], document templates
ms.assetid: c87f1821-7cbf-442e-9690-f126ae7fb783
ms.openlocfilehash: 60f85cf0a1c16e1aaa6057160c5b986001e18d84
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97330259"
---
# <a name="document-template-creation"></a>Tworzenie szablonu dokumentu

Podczas tworzenia nowego dokumentu w odpowiedzi na **nowe** lub **otwarte** polecenie z menu **plik** , szablon dokumentu tworzy również nowe okno ramek, za pomocą którego można wyświetlić dokument.

Konstruktor dokumentu-szablonu określa typy dokumentów, okien i widoków, które będą mogły zostać utworzone przez szablon. Jest to określane przez argumenty przekazywane do konstruktora dokumentu-szablonu. Poniższy kod ilustruje tworzenie [CMultiDocTemplate](reference/cmultidoctemplate-class.md) dla przykładowej aplikacji:

[!code-cpp[NVC_MFCDocView#7](codesnippet/cpp/document-template-creation_1.cpp)]

Wskaźnik do nowego `CMultiDocTemplate` obiektu jest używany jako argument do [AddDocTemplate](reference/cwinapp-class.md#adddoctemplate). Argumenty `CMultiDocTemplate` konstruktora obejmują identyfikator zasobu skojarzony z menu i akceleratory typu dokumentu oraz trzy zastosowania makra [RUNTIME_CLASS](reference/run-time-object-model-services.md#runtime_class) . `RUNTIME_CLASS` zwraca obiekt [CRuntimeClass](reference/cruntimeclass-structure.md) dla klasy C++ o nazwie jako argument. Trzy obiekty przenoszone `CRuntimeClass` do konstruktora dokumentu-szablonu dostarczają informacje konieczne do utworzenia nowych obiektów określonych klas podczas procesu tworzenia dokumentu. W przykładzie pokazano Tworzenie szablonu dokumentu, który tworzy `CScribDoc` obiekty z `CScribView` dołączonymi obiektami. Widoki są obramowane według standardowych okienek podrzędnych MDI.

## <a name="see-also"></a>Zobacz też

[Szablony dokumentów i proces tworzenia dokumentu/widoku](document-templates-and-the-document-view-creation-process.md)<br/>
[Tworzenie dokumentu/widoku](document-view-creation.md)<br/>
[Relacje między obiektami MFC](relationships-among-mfc-objects.md)<br/>
[Tworzenie nowych dokumentów, okien i widoków](creating-new-documents-windows-and-views.md)
