---
redirect_url: /biztalk/core/adding-biztalk-adapter-for-jd-edwards-oneworld/
redirect_document_id: True
ROBOTS: NOINDEX
ms.openlocfilehash: 0491ac0f26b19a96d11cf633263010026961c58b
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
---
# <a name="adding-the-adapter-to-biztalk-server"></a><span data-ttu-id="cc56f-101">BizTalk Server にアダプターを追加します。</span><span class="sxs-lookup"><span data-stu-id="cc56f-101">Adding the Adapter to BizTalk Server</span></span>
<span data-ttu-id="cc56f-102">Microsoft BizTalk Adapter for JD Edwards OneWorld には、受信ハンドラーと送信ハンドラーの両方のフォルダーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="cc56f-102">Microsoft BizTalk Adapter for JD Edwards OneWorld contains both the Receive Handler and Send Handler folders.</span></span> <span data-ttu-id="cc56f-103">送信ハンドラー フォルダーには、BizTalkServerApplication が含まれています。</span><span class="sxs-lookup"><span data-stu-id="cc56f-103">The Send Handler folder contains BizTalkServerApplication.</span></span> <span data-ttu-id="cc56f-104">BizTalk Adapter for JD Edwards OneWorld は作成可能です。BizTalk Server とインプロセスで実行され、分離されたホスト プロセスでは実行されません。</span><span class="sxs-lookup"><span data-stu-id="cc56f-104">BizTalk Adapter for JD Edwards OneWorld is creatable; it runs in-process with BizTalk Server and does not run in an isolated host process.</span></span>  
  
 <span data-ttu-id="cc56f-105">BizTalk Server にアダプターを追加するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="cc56f-105">Use the following procedure to add the adapter to BizTalk Server.</span></span>  
  
### <a name="to-add-biztalk-adapter-for-jd-edwards-oneworld"></a><span data-ttu-id="cc56f-106">BizTalk Adapter for JD Edwards OneWorld を追加するには</span><span class="sxs-lookup"><span data-stu-id="cc56f-106">To add BizTalk Adapter for JD Edwards OneWorld</span></span>  
  
1.  <span data-ttu-id="cc56f-107">**開始** メニューのをポイント**Program Files**、 をポイント[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]、順にクリック**BizTalk Server 管理コンソール**を開始する、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="cc56f-107">On the **Start** menu, point to **Program Files**, point to [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)], and then click **BizTalk Server Administration** to start the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console.</span></span>  
  
2.  <span data-ttu-id="cc56f-108">展開**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、順に展開**プラットフォームの設定**です。</span><span class="sxs-lookup"><span data-stu-id="cc56f-108">Expand **BizTalk Server Administration**, expand **BizTalk Group**, and then expand **Platform Settings**.</span></span>  
  
3.  <span data-ttu-id="cc56f-109">右クリック**アダプター**、指す**新規**、 をクリック**アダプター**です。</span><span class="sxs-lookup"><span data-stu-id="cc56f-109">Right-click **Adapters**, point to **New**, and click **Adapter**.</span></span>  
  
4.  <span data-ttu-id="cc56f-110">**アダプター プロパティ**ダイアログ ボックスで、アダプターの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="cc56f-110">In the **Adapter Properties** dialog box, type a name for the adapter.</span></span> <span data-ttu-id="cc56f-111">たとえば、JDEdwards です。</span><span class="sxs-lookup"><span data-stu-id="cc56f-111">For example, JDEdwards.</span></span>  
  
5.  <span data-ttu-id="cc56f-112">選択**[jdeoneworld]**から、**アダプター**一覧をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="cc56f-112">Select **JDEOneWorld** from the **Adapter** list, and then click **OK**.</span></span>  
  
## <a name="verifying-the-adapter"></a><span data-ttu-id="cc56f-113">アダプターの確認</span><span class="sxs-lookup"><span data-stu-id="cc56f-113">Verifying the Adapter</span></span>  
 <span data-ttu-id="cc56f-114">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、できることを確認するを確認して、アダプターが正しく機能している、**論理システム**ウィンドウです。</span><span class="sxs-lookup"><span data-stu-id="cc56f-114">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, you can verify that the adapter is functioning correctly by looking at the **Logical System** window.</span></span> <span data-ttu-id="cc56f-115">初回のインストレーションでは、このウィンドウは空です。これは、サーバー システムへの接続が未確立で、論理システムが作成されていないからです。</span><span class="sxs-lookup"><span data-stu-id="cc56f-115">On initial installation, this window is empty because you have not yet established a connection to the server system, nor have you created any logical systems.</span></span>  
  
#### <a name="to-verify-that-the-adapter-is-running-correctly"></a><span data-ttu-id="cc56f-116">アダプターが正常に動作していることを確認するには</span><span class="sxs-lookup"><span data-stu-id="cc56f-116">To verify that the adapter is running correctly</span></span>  
  
1.  <span data-ttu-id="cc56f-117">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、 **BizTalk グループ**、展開**プラットフォームの設定**、展開**アダプター**、し、 **[Jdeoneworld]**です。</span><span class="sxs-lookup"><span data-stu-id="cc56f-117">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **BizTalk Group**, expand **Platform Settings**, expand **Adapters**, and then select **JDEOneWorld**.</span></span>  
  
2.  <span data-ttu-id="cc56f-118">詳細ウィンドウで右クリック**BizTalkServerApplication**を選択して**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="cc56f-118">In the details pane, right-click **BizTalkServerApplication**, and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="cc56f-119">**[プロパティ]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="cc56f-119">Click the **Properties** tab.</span></span>  
  
4.  <span data-ttu-id="cc56f-120">SQL 接続パラメーターを設定します。</span><span class="sxs-lookup"><span data-stu-id="cc56f-120">Set the SQL Connection parameters.</span></span>  
  
    -   <span data-ttu-id="cc56f-121">**SQL データベース パラメーターを定義する**SQL Server 名とデータベースがインストール時に設定します。</span><span class="sxs-lookup"><span data-stu-id="cc56f-121">**Define SQL Database Parameters -** The SQL Server Name and Database are those you set at installation.</span></span> <span data-ttu-id="cc56f-122">これは、テキスト領域がサーバーと、このアダプターのデータベースを再定義できることです。</span><span class="sxs-lookup"><span data-stu-id="cc56f-122">This is the text area that you can redefine the server and database for this adapter.</span></span>  
  
5.  <span data-ttu-id="cc56f-123">をクリックして**閉じる**を終了する、**論理システム**ウィンドウです。</span><span class="sxs-lookup"><span data-stu-id="cc56f-123">Click **Close** to exit the **Logical System** window.</span></span>  
  
     <span data-ttu-id="cc56f-124">次のステップでは、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] を使用して論理システムを追加します。</span><span class="sxs-lookup"><span data-stu-id="cc56f-124">Your next step is to add a logical system using [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc56f-125">参照</span><span class="sxs-lookup"><span data-stu-id="cc56f-125">See Also</span></span>  
 <span data-ttu-id="cc56f-126">[計画とアーキテクチャ](../core/planning-and-architecture17.md) </span><span class="sxs-lookup"><span data-stu-id="cc56f-126">[Planning and Architecture](../core/planning-and-architecture17.md) </span></span>  
 <span data-ttu-id="cc56f-127">[BizTalk Adapter for JD Edwards OneWorld のセキュリティ](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md) </span><span class="sxs-lookup"><span data-stu-id="cc56f-127">[Security in BizTalk Adapter for JD Edwards OneWorld](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md) </span></span>  
 [<span data-ttu-id="cc56f-128">BizTalk Adapter for JD Edwards OneWorld の追加</span><span class="sxs-lookup"><span data-stu-id="cc56f-128">Adding BizTalk Adapter for JD Edwards OneWorld</span></span>](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md)