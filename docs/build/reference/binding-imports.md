---
description: 'Dowiedz się więcej o programie: tworzenie powiązań'
title: Powiązywanie importów
ms.date: 11/04/2016
helpviewer_keywords:
- /DELAY:NOBIND linker option
- DELAY:NOBIND linker option
ms.assetid: bb766038-deb1-41b1-bcbc-29a30e8c1e2a
ms.openlocfilehash: 7d1b4374bf1d3340a918f252d80102057febe053
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97182713"
---
# <a name="binding-imports"></a>Powiązywanie importów

Domyślne zachowanie konsolidatora polega na utworzeniu powiązanej tabeli adresów importu dla biblioteki DLL załadowanej z opóźnieniem. Jeśli biblioteka DLL jest powiązana, funkcja pomocnika podejmie próbę użycia informacji powiązanych zamiast wywoływania **GetProcAddress** dla każdego z przywoływanych importów. Jeśli sygnatura czasowa lub preferowany adres nie są zgodne z załadowanej biblioteki DLL, funkcja pomocnika przyjmie, że powiązana tabela adresów importowania jest nieaktualna i będzie działać tak, jakby nie istnieje.

Jeśli nigdy nie zamierzasz powiązać importowanych z opóźnieniem bibliotek DLL, określenie [/delay](delay-delay-load-import-settings.md): nobind w wierszu polecenia konsolidatora uniemożliwi wygenerowanie i zużywanie miejsca w pliku obrazu.

## <a name="see-also"></a>Zobacz też

[Obsługa konsolidatora dla Delay-Loaded bibliotek DLL](linker-support-for-delay-loaded-dlls.md)
