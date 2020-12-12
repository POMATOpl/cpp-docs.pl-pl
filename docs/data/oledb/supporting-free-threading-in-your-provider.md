---
description: 'Dowiedz się więcej na temat: obsługa bezpłatnej wielowątkowości w dostawcy'
title: Obsługa wolnych wątków w dostawcy
ms.date: 11/04/2016
helpviewer_keywords:
- OLE DB providers, multithreaded
- threading [C++], providers
ms.assetid: a91270dc-cdf9-4855-88e7-88a54be7cbe8
ms.openlocfilehash: 4f6785dd85ae043ce0ee74c1dda4fa365c566729
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97286478"
---
# <a name="supporting-free-threading-in-your-provider"></a>Obsługa wolnych wątków w dostawcy

Wszystkie klasy dostawcy OLE DB są bezpieczne dla wątków, a wpisy rejestru są odpowiednio ustawiane. Dobrym pomysłem jest wsparcie bezpłatnego wątku w celu zapewnienia wysokiego poziomu wydajności w sytuacjach wielodostępnych. Aby zapewnić bezpieczeństwo wątków dostawcy, należy sprawdzić, czy kod jest prawidłowo zablokowany. Za każdym razem, gdy zapisujesz lub zapisujesz dane, musisz zablokować dostęp z sekcji krytycznych.

Każdy obiekt szablonu dostawcy OLE DB ma swoją własną sekcję krytyczną. Aby ułatwić blokowanie, każda utworzona nowa klasa powinna być klasą szablonu przyjmującą nazwę klasy nadrzędnej jako argument.

Poniższy przykład pokazuje, jak zablokować kod:

```cpp
template <class T>
class CMyObject<T> : public...

HRESULT MyObject::MyMethod(void)
{
   T* pT = (T*)this;      // this gets the parent class

// You don't need to do anything if you are only reading information

// If you want to write information, do the following:
   pT->Lock();         // engages critical section in the object
   ...;                // write whatever information you wish
   pT->Unlock();       // disengages the critical section
}
```

Aby uzyskać więcej informacji na temat ochrony krytycznych sekcji za pomocą `Lock` i `Unlock` , zobacz [wielowątkowość: jak używać klas synchronizacji](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).

Sprawdź, czy wszystkie metody, które zostały zastąpione (na przykład `Execute` ), są bezpieczne dla wątków.

## <a name="see-also"></a>Zobacz też

[Praca z szablonami dostawców OLE DB](../../data/oledb/working-with-ole-db-provider-templates.md)
