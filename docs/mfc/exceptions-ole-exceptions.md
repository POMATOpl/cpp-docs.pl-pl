---
description: 'Dowiedz się więcej o: wyjątki: wyjątki OLE'
title: 'Wyjątki: wyjątki OLE'
ms.date: 11/04/2016
helpviewer_keywords:
- OLE, exceptions
- OLE exceptions [MFC]
- exceptions [MFC], OLE
- exception handling [MFC], OLE
- OLE exceptions [MFC], classes for handling
ms.assetid: 2f8e0161-b94f-48bb-a5a2-6f644b192527
ms.openlocfilehash: da2a92d23dc7c11735c75482febea60916af289f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97290521"
---
# <a name="exceptions-ole-exceptions"></a>Wyjątki: wyjątki OLE

Techniki i obiekty obsługujące wyjątki w mechanizmie OLE są takie same jak w przypadku obsługi innych wyjątków. Aby uzyskać więcej informacji na temat obsługi wyjątków, zobacz artykuł [nowoczesne C++ Best Practices for Exceptions and erroring](../cpp/errors-and-exception-handling-modern-cpp.md).

Wszystkie obiekty wyjątków są wyprowadzane z abstrakcyjnej klasy bazowej `CException` . MFC udostępnia dwie klasy do obsługi wyjątków OLE:

- [COleException](reference/coleexception-class.md) Obsługa ogólnych wyjątków OLE.

- [COleDispatchException](reference/coledispatchexception-class.md) Do generowania i obsługi wyjątków wysyłania OLE (Automation).

Różnica między tymi dwiema klasami to ilość informacji, które zapewnia i gdzie są używane. `COleException` ma publiczny element członkowski danych zawierający kod stanu OLE dla wyjątku. `COleDispatchException` dostarcza więcej informacji, w tym następujące:

- Kod błędu specyficzny dla aplikacji

- Opis błędu, taki jak "dysk zapełniony"

- Kontekst pomocy, który może być używany przez aplikację w celu podania dodatkowych informacji dla użytkownika

- Nazwa pliku pomocy aplikacji

- Nazwa aplikacji, która wygenerowała wyjątek.

`COleDispatchException` zawiera więcej informacji, dzięki którym można korzystać z produktów, takich jak Microsoft Visual Basic. Opisowy błąd można użyć w oknie komunikatu lub w innym powiadomieniu; informacje pomocy mogą pomóc użytkownikowi odpowiedzieć na warunki, które spowodowały wyjątek.

Dwie funkcje globalne odpowiadają dwóm klasom wyjątków OLE: [AfxThrowOleException](reference/exception-processing.md#afxthrowoleexception) i [AfxThrowOleDispatchException](reference/exception-processing.md#afxthrowoledispatchexception). Są one używane do rzutowania ogólnych wyjątków OLE i wyjątków wysyłania OLE.

## <a name="see-also"></a>Zobacz też

[Obsługa wyjątków](exception-handling-in-mfc.md)
