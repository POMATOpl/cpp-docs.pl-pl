---
description: 'Dowiedz się więcej o: ogólne zasady projektowania klas'
title: Ogólne zasady projektowania klas
ms.date: 11/04/2016
helpviewer_keywords:
- designing classes [MFC]
- MFC, Windows API
- Visual C, Windows API calls
- classes [MFC], MFC class design
- Windows API [MFC], and MFC
ms.assetid: e6861ae0-1581-4d9c-9ddf-63f9afcdb913
ms.openlocfilehash: 96069b5f30cbca8bb310de6b917fd65a280700b0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97193464"
---
# <a name="general-class-design-philosophy"></a>Ogólne zasady projektowania klas

System Microsoft Windows został zaprojektowany długo, zanim język C++ stał się popularny. Ze względu na to, że tysiące aplikacji korzysta z interfejsu programowania aplikacji systemu Windows (API) dla języka C, ten interfejs będzie obsługiwany w przyszłości. Każdy interfejs C++ systemu Windows musi być utworzony w oparciu o interfejs API języka C. Gwarantuje to, że aplikacje C++ będą mogły współistnieć z aplikacjami języka C.

Biblioteka MFC to interfejs zorientowany obiektowo dla systemu Windows, który spełnia następujące cele projektowe:

- Znacząca redukcja nakładu pracy w celu napisania aplikacji dla systemu Windows.

- Szybkość wykonywania porównywalna z tym interfejsem API języka C.

- Minimalny koszt rozmiaru kodu.

- Możliwość bezpośredniej wywołania dowolnej funkcji systemu Windows C.

- Łatwiejsza Konwersja istniejących aplikacji C do języka C++.

- Możliwość wykorzystania z istniejącej podstawy środowiska programowania systemu Windows w języku C.

- Łatwiejsze korzystanie z interfejsu API systemu Windows w języku C++ niż w przypadku języka C.

- Łatwiejsze w użyciu jeszcze zaawansowane abstrakcje skomplikowanych funkcji, takich jak kontrolki ActiveX, obsługa bazy danych, drukowanie, paski narzędzi i paski stanu.

- Prawdziwy interfejs API systemu Windows dla języka C++, który efektywnie korzysta z funkcji języka C++.

Aby uzyskać więcej informacji na temat projektowania biblioteki MFC, zobacz:

- [Struktura aplikacji](application-framework.md)

- [Relacja z interfejsem API języka C](relationship-to-the-c-language-api.md)

## <a name="see-also"></a>Zobacz też

[Przegląd klas](class-library-overview.md)
