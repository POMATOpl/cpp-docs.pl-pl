---
description: 'Dowiedz się więcej na temat: lokalny magazyn wątków'
title: Lokalny magazyn wątków
ms.date: 11/04/2016
helpviewer_keywords:
- thread-local variables
- TLS (thread local storage)
- thread storage-class attribute
- thread-local storage
- storage, thread local storage
ms.assetid: a0f1b109-c953-4079-aa10-e47f5483173d
ms.openlocfilehash: 188646ec6ae980cc61bd5882c15e2e9040e4a7ca
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97114341"
---
# <a name="thread-local-storage"></a>Lokalny magazyn wątków

**Specyficzne dla firmy Microsoft**

Lokalny magazyn wątków (TLS) to mechanizm, za pomocą którego każdy wątek w danym procesie wielowątkowym przydziela magazyn dla danych specyficznych dla wątku. W standardowych programach wielowątkowych, dane są współużytkowane przez wszystkie wątki danego procesu, natomiast pamięć lokalna wątku jest mechanizmem przydzielania danych osobno dla danego wątku. Aby uzyskać pełną dyskusję na temat wątków, zobacz [procesy i wątki](/windows/win32/ProcThread/processes-and-threads) w Windows SDK.

Język języka Microsoft C zawiera rozszerzony atrybut klasy magazynu, wątek, który jest używany z słowem kluczowym __declspec, aby zadeklarować zmienną lokalną wątku. Na przykład, poniższy kod deklaruje lokalną zmienną całkowitą wątku i inicjuje ją wartością:

```
__declspec( thread ) int tls_i = 1;
```

Te wskazówki muszą być przestrzegane, gdy deklarując statycznie powiązane zmienne lokalne wątku:

- Zmienne lokalne wątku, które mają inicjalizację dynamiczną, są inicjowane tylko w wątku, który powoduje załadowanie biblioteki DLL, oraz wątki, które są już uruchomione w procesie. Aby uzyskać więcej informacji, zobacz [wątek](../cpp/thread.md).

- Atrybut Thread można zastosować tylko do deklaracji i definicji danych. Nie można jej używać w deklaracjach lub definicjach funkcji. Na przykład poniższy kod generuje błąd kompilatora:

    ```C
    #define Thread   __declspec( thread )
    Thread void func();      /* Error */
    ```

- Można określić atrybut wątku tylko dla elementów danych ze statycznym okresem przechowywania. Obejmuje to dane globalne (statyczne i zewnętrzne) oraz lokalne dane statyczne. Nie można zadeklarować automatycznych danych przy użyciu atrybutu wątku. Na przykład poniższy kod generuje błędy kompilatora:

    ```C
    #define Thread   __declspec( thread )
    void func1()
    {
        Thread int tls_i;            /* Error */
    }

    int func2( Thread int tls_i )    /* Error */
    {
       return tls_i;
    }
    ```

- Należy użyć atrybutu wątku dla deklaracji i definicji danych lokalnych wątku, niezależnie od tego, czy deklaracja i definicja występują w tym samym pliku lub oddzielnych plikach. Na przykład poniższy kod generuje błąd:

    ```C
    #define Thread   __declspec( thread )
    extern int tls_i;     /* This generates an error, because the   */
    int Thread tls_i;     /* declaration and the definition differ. */
    ```

- Nie można użyć atrybutu wątku jako modyfikatora typu. Na przykład poniższy kod generuje błąd kompilatora:

    ```C
    char *ch __declspec( thread );      /* Error */
    ```

- Adres zmiennej lokalnej wątku nie jest uważany za stałą i każde wyrażenie, w którym znajduje się taki adres, nie jest traktowane jako wyrażenie stałe. Oznacza to, że nie można użyć adresu zmiennej lokalnej wątku jako inicjatora wskaźnika. Na przykład kompilator flaguje następujący kod jako błąd:

    ```C
    #define Thread   __declspec( thread )
    Thread int tls_i;
    int *p = &tls_i;      /* Error */
    ```

- C zezwala na inicjowanie zmiennej z wyrażeniem, w którym uczestniczy odwołanie do samego siebie, ale tylko dla obiektów niestatycznych. Na przykład:

    ```C
    #define Thread   __declspec( thread )
    Thread int tls_i = tls_i;             /* Error */
    int j = j;                            /* Error */
    Thread int tls_i = sizeof( tls_i )    /* Okay  */
    ```

   Należy zauważyć, że wyrażenie sizeof zawierające zainicjowaną zmienną nie stanowi odwołania do samego siebie i jest dozwolone.

- Korzystanie z **\_ \_ declspec (thread)** może zakłócać [ładowanie](../build/reference/linker-support-for-delay-loaded-dlls.md) importów dll.

Aby uzyskać więcej informacji o używaniu atrybutu thread, zobacz [temat wielowątkowość](../parallel/multithreading-support-for-older-code-visual-cpp.md).

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Rozszerzone atrybuty Storage-Class języka C](../c-language/c-extended-storage-class-attributes.md)
