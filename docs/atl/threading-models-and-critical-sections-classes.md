---
description: 'Dowiedz się więcej na temat: model wątkowości i klasy sekcji krytycznych'
title: Modele wątkowości i klasy sekcji krytycznych (ATL)
ms.date: 11/04/2016
helpviewer_keywords:
- ATL, critical sections
- ATL, multithreading
- threading [ATL], models
- critical sections
ms.assetid: 759f05ef-6285-4be6-a2cc-78572dd75146
ms.openlocfilehash: 51ad5a5f2f03bfe080395966d0c480615c49a109
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97138284"
---
# <a name="threading-models-and-critical-sections-classes"></a>Modele wątkowości i klasy sekcji krytycznych

Poniższe klasy definiują model wątkowości i sekcję krytyczną:

- [CAtlAutoThreadModule](../atl/reference/catlautothreadmodule-class.md) Implementuje serwer COM z pulą wątków, model typu Apartment.

- [CAtlAutoThreadModuleT](../atl/reference/catlautothreadmodulet-class.md) Zapewnia metody implementowania serwera COM w puli wątków.

- [CComMultiThreadModel](../atl/reference/ccommultithreadmodel-class.md) Zapewnia bezpieczne dla wątków metody zwiększania i zmniejszania zmiennej. Zawiera sekcję krytyczną.

- [CComMultiThreadModelNoCS](../atl/reference/ccommultithreadmodelnocs-class.md) Zapewnia bezpieczne dla wątków metody zwiększania i zmniejszania zmiennej. Nie zawiera sekcji krytycznej.

- [CComSingleThreadModel](../atl/reference/ccomsinglethreadmodel-class.md) Zapewnia metody zwiększania i zmniejszania wartości zmiennej. Nie zawiera sekcji krytycznej.

- [CComObjectThreadModel](../atl/reference/atl-typedefs.md#ccomobjectthreadmodel) Określa odpowiednią klasę threading-model dla pojedynczej klasy obiektu.

- [CComGlobalsThreadModel](../atl/reference/atl-typedefs.md#ccomglobalsthreadmodel) Określa odpowiednią klasę threading-model dla obiektu, który jest dostępny globalnie.

- [CComAutoCriticalSection](../atl/reference/ccomautocriticalsection-class.md) Zawiera metody uzyskiwania i zwalniania sekcji krytycznej. Sekcja krytyczna jest inicjowana automatycznie.

- [CComCriticalSection](../atl/reference/ccomcriticalsection-class.md) Zawiera metody uzyskiwania i zwalniania sekcji krytycznej. Sekcja krytyczna musi być zainicjowana jawnie.

- [CComFakeCriticalSection](../atl/reference/ccomfakecriticalsection-class.md) Odzwierciedla metody z `CComCriticalSection` bez podawania sekcji krytycznej. W tej metodzie `CComFakeCriticalSection` nic nie rób.

- [CRTThreadTraits](../atl/reference/crtthreadtraits-class.md) Udostępnia funkcję tworzenia dla wątku CRT. Użyj tej klasy, jeśli wątek będzie używać funkcji CRT.

- [Win32ThreadTraits](../atl/reference/win32threadtraits-class.md) Udostępnia funkcję tworzenia dla wątku systemu Windows. Użyj tej klasy, jeśli wątek nie będzie używać funkcji CRT.

## <a name="see-also"></a>Zobacz też

[Przegląd klas](../atl/atl-class-overview.md)
