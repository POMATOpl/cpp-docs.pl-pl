---
description: 'Dowiedz się więcej na temat: Przewodnik: dodawanie animacji do projektu MFC'
title: 'Wskazówki: dodawanie animacji do projektu MFC'
ms.date: 04/25/2019
helpviewer_keywords:
- animation [MFC]
- MFC, animation
ms.assetid: 004f832c-9fd5-4f88-9ca9-ae65dececdc2
ms.openlocfilehash: ef6d6fc8e17c8e6dc4c6f0f4e8d7407f2690927f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97143120"
---
# <a name="walkthrough-adding-animation-to-an-mfc-project"></a>Wskazówki: dodawanie animacji do projektu MFC

W tym instruktażu pokazano, jak dodać podstawowy animowany obiekt do projektu Visual C++, biblioteka MFC (MFC).

W tym przewodniku przedstawiono sposób wykonywania następujących zadań:

- Utwórz aplikację MFC.

- Dodaj menu, a następnie Dodaj polecenia do uruchamiania i zatrzymywania animacji.

- Utwórz programy obsługi dla poleceń Uruchom i Zatrzymaj.

- Dodaj animowany obiekt do projektu.

- Wyśrodkuj animowany obiekt w oknie.

- Sprawdź wyniki.

[!INCLUDE[note_settings_general](../mfc/includes/note_settings_general_md.md)]

## <a name="prerequisites"></a>Wymagania wstępne

Aby ukończyć ten przewodnik, musisz mieć program Visual Studio.

### <a name="to-create-an-mfc-application"></a>Aby utworzyć aplikację MFC

1. Użyj **Kreatora aplikacji MFC** , aby utworzyć aplikację MFC. Zobacz [Przewodnik: używanie nowych formantów powłoki MFC](walkthrough-using-the-new-mfc-shell-controls.md) w celu uzyskania instrukcji dotyczących sposobu otwierania Kreatora dla używanej wersji programu Visual Studio.

1. W polu **Nazwa** wpisz *MFCAnimationWalkthrough*. Kliknij przycisk **OK**.

1. W oknie dialogowym **Kreator aplikacji MFC** Sprawdź, czy **Typ aplikacji** to **wiele dokumentów**, **styl projektu** to **program Visual Studio**, a opcja **Obsługa architektury dokumentu/widoku** jest zaznaczona. Kliknij przycisk **Finish** (Zakończ).

### <a name="to-add-a-menu-and-then-add-commands-to-start-and-stop-an-animation"></a>Aby dodać menu, a następnie dodać polecenia do uruchamiania i zatrzymywania animacji

1. W menu **Widok** wskaż **inne okna** , a następnie kliknij przycisk **Widok zasobów**.

1. W **Widok zasobów** przejdź do folderu **menu** i otwórz go. Kliknij dwukrotnie zasób **IDR_MFCAnimationWalkthroughTYPE** , aby otworzyć go do modyfikacji.

1. Na pasku menu w polu **Wpisz tutaj** wpisz *&nimation* , aby utworzyć menu animacji.

1. W obszarze **animacja** w polu **Wpisz tutaj** wpisz *Rozpocznij &dalej* , aby utworzyć polecenie Uruchom do przodu.

1. W obszarze **Rozpocznij do przodu** w polu **Wpisz tutaj** wpisz *Start &do tyłu*.

1. W obszarze **Rozpocznij od tyłu**, w polu **Wpisz tutaj** wpisz *S&Top* , aby utworzyć polecenie zatrzymania.

1. Zapisz MFCAnimationWalkthrough. RC i zamknij go.

1. W **Eksplorator rozwiązań** kliknij dwukrotnie pozycję MainFrm. cpp, aby otworzyć ją do modyfikacji. W `CMainFrame::OnCreate` metodzie zlokalizuj sekcję, która zawiera kilka wywołań `lstBasicCommands.AddTail` . Zaraz po tej sekcji Dodaj następujący kod.

    ```cpp
    lstBasicCommands.AddTail(ID_ANIMATION_STARTFORWARD);
    lstBasicCommands.AddTail(ID_ANIMATION_STARTBACKWARD);
    lstBasicCommands.AddTail(ID_ANIMATION_STOP);
    ```

1. Zapisz plik i zamknij go.

### <a name="to-create-handlers-for-the-start-and-stop-commands"></a>Aby utworzyć programy obsługi dla poleceń Uruchom i Zatrzymaj

1. W menu **projekt** kliknij polecenie **Kreator klas**.

1. W **Kreatorze klasy MFC** w obszarze **Nazwa klasy** wybierz pozycję **CMFCAnimationWalkthroughView**.

1. Na karcie **polecenia** w polu **identyfikatory obiektów** wybierz pozycję **ID_ANIMATION_STARTFORWARD**, a następnie w polu **komunikaty** wybierz opcję **polecenie**. Kliknij przycisk **Dodaj program obsługi**.

1. W oknie dialogowym **Dodawanie funkcji członkowskiej** kliknij przycisk **OK**.

1. W polu **identyfikatory obiektów** wybierz pozycję **ID_ANIMATION_STARTBACKWARD**, a następnie w polu **komunikaty** wybierz opcję **polecenie**. Kliknij przycisk **Dodaj program obsługi**.

1. W oknie dialogowym **Dodawanie funkcji członkowskiej** kliknij przycisk **OK**.

1. W polu **identyfikatory obiektów** wybierz pozycję **ID_ANIMATION_STOP**, a następnie w polu **komunikaty** wybierz opcję **polecenie**. Kliknij przycisk **Dodaj procedurę obsługi** , a następnie kliknij przycisk **OK**.

1. W oknie dialogowym **Dodawanie funkcji członkowskiej** kliknij przycisk **OK**.

1. W **Kreatorze klasy MFC** kliknij przycisk **OK**.

1. Zapisz MFCAnimationWalkthroughView. cpp, który jest otwarty w edytorze, ale nie zamykaj go.

### <a name="to-add-an-animated-object-to-the-project"></a>Aby dodać animowany obiekt do projektu

1. W **Eksplorator rozwiązań** kliknij dwukrotnie pozycję MFCAnimationWalkthroughView. h, aby otworzyć ją do modyfikacji. Tuż przed definicją `CMFCAnimationWalkthroughView` klasy Dodaj następujący kod, aby utworzyć niestandardowy kontroler animacji, który będzie obsługiwał konflikty harmonogramu z obiektem animacji.

    ```cpp
    class CCustomAnimationController : public CAnimationController
    {
    public:
        CCustomAnimationController()
        {
        }

        virtual BOOL OnHasPriorityTrim(CAnimationGroup* pGroupScheduled,
            CAnimationGroup* pGroupNew,
            UI_ANIMATION_PRIORITY_EFFECT priorityEffect)
        {
            return TRUE;
        }
    };
    ```

1. Na końcu `CMFCAnimationWalkthroughView` klasy Dodaj następujący kod.

    ```cpp
    CCustomAnimationController m_animationController;
    CAnimationColor m_animationColor;
    CAnimationRect m_animationRect;
    ```

1. Po `DECLARE_MESSAGE_MAP()` wierszu Dodaj następujący kod.

    ```cpp
    void Animate(BOOL bDirection);
    ```

1. Zapisz plik i zamknij go.

1. W MFCAnimationWalkthroughView. cpp, w górnej części pliku po `#include` instrukcjach, ale przed dowolnymi metodami klas, Dodaj następujący kod.

    ```cpp
    static int nAnimationGroup = 0;
    static int nInfoAreaHeight = 40;
    ```

1. Na końcu konstruktora dla `CMFCAnimationWalkthroughView` , Dodaj następujący kod.

    ```cpp
    m_animationController.EnableAnimationTimerEventHandler();
    m_animationController.EnablePriorityComparisonHandler(UI_ANIMATION_PHT_TRIM);
    m_animationColor = RGB(255, 255, 255);
    m_animationRect = CRect(0, 0, 0, 0);
    m_animationColor.SetID(-1, nAnimationGroup);
    m_animationRect.SetID(-1, nAnimationGroup);
    m_animationController.AddAnimationObject(&m_animationColor);
    m_animationController.AddAnimationObject(&m_animationRect);
    ```

1. Znajdź `CAnimationWalthroughView::PreCreateWindow` metodę, a następnie zastąp ją poniższym kodem.

    ```cpp
    BOOL CMFCAnimationWalkthroughView::PreCreateWindow(CREATESTRUCT& cs)
    {
        // TODO: Modify the Window class or styles here by modifying
        //       the CREATESTRUCT cs
        m_animationController.SetRelatedWnd(this);

        return CView::PreCreateWindow(cs);
    }
    ```

1. Znajdź `CAnimationWalkthroughView::OnDraw` metodę, a następnie zastąp ją poniższym kodem.

    ```cpp
    void CMFCAnimationWalkthroughView::OnDraw(CDC* pDC)
    {
        CMFCAnimationWalkthroughDoc* pDoc = GetDocument();
        ASSERT_VALID(pDoc);
        if (!pDoc)
            return;

        // TODO: add draw code for native data here
        CMemDC dcMem(*pDC, this);
        CDC& dc = dcMem.GetDC();
        CRect rect;
        GetClientRect(rect);

        dc.FillSolidRect(rect, GetSysColor(COLOR_WINDOW));

        CString strRGB;
        strRGB.Format(_T("Fill Color is: %d; %d; %d"),
            GetRValue(m_animationColor),
            GetGValue(m_animationColor),
            GetBValue(m_animationColor));

        dc.DrawText(strRGB, rect, DT_CENTER);
        rect.top += nInfoAreaHeight;

        CBrush br;
        br.CreateSolidBrush(m_animationColor);
        CBrush* pBrushOld = dc.SelectObject(&br);

        dc.Rectangle((CRect)m_animationRect);

        dc.SelectObject(pBrushOld);
    }
    ```

1. Na końcu pliku Dodaj następujący kod.

    ```cpp
    void CMFCAnimationWalkthroughView::Animate(BOOL bDirection)
    {
        static UI_ANIMATION_SECONDS duration = 3;
        static DOUBLE dblSpeed = 35.;
        static BYTE nStartColor = 50;
        static BYTE nEndColor = 255;

        BYTE nRedColorFinal = bDirection ? nStartColor : nEndColor;
        BYTE nGreenColorFinal = bDirection ? nStartColor : nEndColor;
        BYTE nBlueColorFinal = bDirection ? nStartColor : nEndColor;

        CLinearTransition* pRedTransition =
            new CLinearTransition(duration, (DOUBLE)nRedColorFinal);

        CSmoothStopTransition* pGreenTransition =
            new CSmoothStopTransition(duration, (DOUBLE)nGreenColorFinal);

        CLinearTransitionFromSpeed* pBlueTransition =
            new CLinearTransitionFromSpeed(dblSpeed, (DOUBLE)nBlueColorFinal);

        m_animationColor.AddTransition(pRedTransition,
            pGreenTransition,
            pBlueTransition);

        CRect rectClient;
        GetClientRect(rectClient);

        rectClient.top += nInfoAreaHeight;

        int nLeftFinal = bDirection ? rectClient.left : rectClient.CenterPoint().x;
        int nTopFinal = bDirection ? rectClient.top : rectClient.CenterPoint().y;
        int nRightFinal = bDirection ? rectClient.right : rectClient.CenterPoint().x;
        int nBottomFinal = bDirection ? rectClient.bottom : rectClient.CenterPoint().y;

        CLinearTransition* pLeftTransition =
            new CLinearTransition(duration, nLeftFinal);

        CLinearTransition* pTopTransition =
            new CLinearTransition(duration, nTopFinal);

        CLinearTransition* pRightTransition =
            new CLinearTransition(duration, nRightFinal);

        CLinearTransition* pBottomTransition =
            new CLinearTransition(duration, nBottomFinal);

        m_animationRect.AddTransition(pLeftTransition,
            pTopTransition,
            pRightTransition,
            pBottomTransition);

        CBaseKeyFrame* pKeyframeStart =
            CAnimationController::GetKeyframeStoryboardStart();
        CKeyFrame* pKeyFrameEnd =
            m_animationController.CreateKeyframe(nAnimationGroup,
                pBlueTransition);

        pLeftTransition->SetKeyframes(pKeyframeStart, pKeyFrameEnd);
        pTopTransition->SetKeyframes(pKeyframeStart, pKeyFrameEnd);
        pRightTransition->SetKeyframes(pKeyframeStart, pKeyFrameEnd);
        pBottomTransition->SetKeyframes(pKeyframeStart, pKeyFrameEnd);

        m_animationController.AnimateGroup(nAnimationGroup);
    }
    ```

1. W menu **projekt** kliknij polecenie **Kreator klas**.

1. W **Kreatorze klasy MFC** w obszarze **Nazwa klasy** wybierz pozycję **CMFCAnimationWalkthroughView**.

1. Na karcie **komunikaty** w polu **komunikaty** wybierz pozycję **WM_ERASEBKGND**, kliknij pozycję **Dodaj obsługę**, a następnie kliknij przycisk **OK**.

1. W MFCAnimationWalkthroughView. cpp Zastąp implementację `OnEraseBkgnd` następującym kodem, aby zmniejszyć migotanie w animowanym obiekcie, gdy jest on ponownie rysowany.

    ```cpp
    BOOL CMFCAnimationWalkthroughView::OnEraseBkgnd(CDC* /*pDC*/)
    {
        return TRUE;
    }
    ```

1. Zastąp implementacje `CMFCAnimationWalkthroughView::OnAnimationStartforward` , `CMFCAnimationWalkthroughView::OnAnimationStartbackward` i `CMFCAnimationWalkthroughView::OnAnimationStop` z poniższym kodem.

    ```cpp
    void CMFCAnimationWalkthroughView::OnAnimationStartforward()
    {
        Animate(TRUE);
    }

    void CMFCAnimationWalkthroughView::OnAnimationStartbackward()
    {
        Animate(FALSE);
    }

    void CMFCAnimationWalkthroughView::OnAnimationStop()
    {
        IUIAnimationManager* pManager = m_animationController.GetUIAnimationManager();
        if (pManager != NULL)
        {
            pManager->AbandonAllStoryboards();

        }
    }
    ```

1. Zapisz plik i zamknij go.

### <a name="to-center-the-animated-object-in-the-window"></a>Aby wyśrodkować animowany obiekt w oknie

1. W **Eksplorator rozwiązań** kliknij dwukrotnie pozycję MFCAnimationWalkthroughView. h, aby otworzyć ją do modyfikacji. Na końcu `CMFCAnimationWalkthroughView` klasy, tuż po definicji `m_animationRect` , Dodaj następujący kod.

    ```cpp
    BOOL m_bCurrentDirection;
    ```

1. Zapisz plik i zamknij go.

1. W menu **projekt** kliknij polecenie **Kreator klas**.

1. W **Kreatorze klasy MFC** w obszarze **Nazwa klasy** wybierz pozycję **CMFCAnimationWalkthroughView**.

1. Na karcie **komunikaty** w polu **komunikaty** wybierz pozycję **WM_SIZE**, kliknij pozycję **Dodaj obsługę**, a następnie kliknij przycisk **OK**.

1. W MFCAnimationWalkthroughView. cpp Zastąp kod `CMFCAnimationWalkthroughView::OnSize` następującym kodem.

    ```cpp
    void CMFCAnimationWalkthroughView::OnSize(UINT nType, int cx, int cy)
    {
        CView::OnSize(nType, cx, cy);
        CRect rect;
        GetClientRect(rect);

        rect.top += nInfoAreaHeight;

        CRect rectAnim = m_animationRect;
        m_animationRect = CRect(CPoint(rect.CenterPoint().x - rectAnim.Width() / 2,
        rect.CenterPoint().y - rectAnim.Height() / 2),
        rectAnim.Size());

        if (m_animationController.IsAnimationInProgress())
        {
            Animate(m_bCurrentDirection);
        }
    }
    ```

1. Na początku konstruktora dla `CMFCAnimationWalkthroughView` , Dodaj następujący kod.

    ```cpp
    m_bCurrentDirection = TRUE;
    ```

1. Na początku `CMFCAnimationWalkthroughView::Animate` metody Dodaj następujący kod.

    ```cpp
    m_bCurrentDirection = bDirection;
    ```

1. Zapisz plik i zamknij go.

### <a name="to-verify-the-results"></a>Aby sprawdzić wyniki

1. Skompiluj i uruchom aplikację. W menu **animacja** kliknij pozycję **Rozpocznij dalej**. Powinien pojawić się prostokąt, a następnie wypełnić obszar środkowy. Po kliknięciu przycisku **Rozpocznij wstecz** animacja powinna zostać odwrócona, a po kliknięciu przycisku **Zatrzymaj** powinna zostać zatrzymana. Kolor wypełnienia prostokąta powinien się zmieniać w miarę postępu animacji, a bieżący kolor powinien być wyświetlany w górnej części okna animacji.

## <a name="see-also"></a>Zobacz też

[Wskazówki](../mfc/walkthroughs-mfc.md)
