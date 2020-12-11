---
description: 'Dowiedz się więcej na temat: klasy i wątki ODBC'
title: Klasy i wątki ODBC
ms.date: 11/04/2016
helpviewer_keywords:
- ODBC classes, and threads
- ODBC, multithreaded applications
- threading [MFC], ODBC support
ms.assetid: 16543926-7331-41a6-ba50-72288f2a61b7
ms.openlocfilehash: bff5ef5a53543b2e0ffa7888f469ed4ce1e54a37
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97161081"
---
# <a name="odbc-classes-and-threads"></a>Klasy i wątki ODBC

Począwszy od MFC 4,2, istnieje obsługa wielowątkowości dla klas MFC ODBC. Należy jednak pamiętać, że MFC nie zapewnia obsługi wielowątkowości dla klas DAO.

Obsługa wielowątkowości dla klas ODBC ma pewne ograniczenia. Ponieważ te klasy zawijają interfejs API ODBC, są ograniczone do obsługi wielowątkowości składników, na których zostały skompilowane. Na przykład wiele sterowników ODBC nie jest bezpieczny wątkowo. w związku z tym klasy MFC ODBC nie są bezpieczne wątkowo, jeśli są używane z jednym z tych sterowników. Należy sprawdzić, czy konkretny sterownik jest bezpieczny dla wątków.

Podczas tworzenia aplikacji wielowątkowej należy zachować ostrożność przy użyciu wielu wątków do manipulowania tym samym obiektem. Na przykład użycie tego samego `CRecordset` obiektu w dwóch wątkach może powodować problemy podczas pobierania danych; operacja pobierania w jednym wątku może zastąpić dane pobrane w innym wątku. Bardziej typowym zastosowaniem klas MFC ODBC w oddzielnych wątkach jest udostępnienie otwartego `CDatabase` obiektu w wątkach w celu użycia tego samego połączenia ODBC z oddzielnym `CRecordset` obiektem w każdym wątku. Należy zauważyć, że nie należy przekazywać nieotwartego `CDatabase` obiektu do `CRecordset` obiektu w innym wątku.

> [!NOTE]
> Jeśli trzeba mieć wiele wątków manipuluje tym samym obiektem, należy zaimplementować odpowiednie mechanizmy synchronizacji, takie jak sekcje krytyczne. Należy pamiętać, że niektóre operacje, takie jak `Open` , nie są chronione. Należy się upewnić, że operacje te nie zostaną wywołane współbieżnie z oddzielnych wątków.

Aby uzyskać więcej informacji na temat tworzenia aplikacji wielowątkowych, zobacz [temat wielowątkowość](../../parallel/multithreading-support-for-older-code-visual-cpp.md).

## <a name="see-also"></a>Zobacz też

[Open Database Connectivity (ODBC)](../../data/odbc/open-database-connectivity-odbc.md)<br/>
[Programowanie dostępu do danych (MFC/ATL)](../../data/data-access-programming-mfc-atl.md)
