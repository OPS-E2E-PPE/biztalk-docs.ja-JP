---
title: "BizTalk Server にアダプターを追加する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- adapters [JD Edwards OneWorld adapters], installing
- installing, JD Edwards OneWorld adapters
- JD Edwards OneWorld adapters, installing
ms.assetid: e2018856-1943-48e9-b43f-7d527880e4bd
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 63de8824112c9891c6d67eee424a84dd4968976c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="adding-the-adapter-to-biztalk-server"></a><span data-ttu-id="c5b2e-102">BizTalk Server にアダプターを追加します。</span><span class="sxs-lookup"><span data-stu-id="c5b2e-102">Adding the Adapter to BizTalk Server</span></span>
<span data-ttu-id="c5b2e-103">Microsoft BizTalk Adapter for JD Edwards OneWorld には、受信ハンドラーと送信ハンドラーの両方のフォルダーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="c5b2e-103">Microsoft BizTalk Adapter for JD Edwards OneWorld contains both the Receive Handler and Send Handler folders.</span></span> <span data-ttu-id="c5b2e-104">送信ハンドラー フォルダーには、BizTalkServerApplication が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c5b2e-104">The Send Handler folder contains BizTalkServerApplication.</span></span> <span data-ttu-id="c5b2e-105">BizTalk Adapter for JD Edwards OneWorld は作成可能です。BizTalk Server とインプロセスで実行され、分離されたホスト プロセスでは実行されません。</span><span class="sxs-lookup"><span data-stu-id="c5b2e-105">BizTalk Adapter for JD Edwards OneWorld is creatable; it runs in-process with BizTalk Server and does not run in an isolated host process.</span></span>  
  
 <span data-ttu-id="c5b2e-106">BizTalk Server にアダプターを追加するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c5b2e-106">Use the following procedure to add the adapter to BizTalk Server.</span></span>  
  
### <a name="to-add-biztalk-adapter-for-jd-edwards-oneworld"></a><span data-ttu-id="c5b2e-107">BizTalk Adapter for JD Edwards OneWorld を追加するには</span><span class="sxs-lookup"><span data-stu-id="c5b2e-107">To add BizTalk Adapter for JD Edwards OneWorld</span></span>  
  
1.  <span data-ttu-id="c5b2e-108">**開始** メニューのをポイント**Program Files**、 をポイント[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]、順にクリック**BizTalk Server 管理コンソール**を開始する、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="c5b2e-108">On the **Start** menu, point to **Program Files**, point to [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)], and then click **BizTalk Server Administration** to start the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console.</span></span>  
  
2.  <span data-ttu-id="c5b2e-109">展開**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、順に展開**プラットフォームの設定**です。</span><span class="sxs-lookup"><span data-stu-id="c5b2e-109">Expand **BizTalk Server Administration**, expand **BizTalk Group**, and then expand **Platform Settings**.</span></span>  
  
3.  <span data-ttu-id="c5b2e-110">右クリック**アダプター**、指す**新規**、 をクリック**アダプター**です。</span><span class="sxs-lookup"><span data-stu-id="c5b2e-110">Right-click **Adapters**, point to **New**, and click **Adapter**.</span></span>  
  
4.  <span data-ttu-id="c5b2e-111">**アダプター プロパティ**ダイアログ ボックスで、アダプターの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="c5b2e-111">In the **Adapter Properties** dialog box, type a name for the adapter.</span></span> <span data-ttu-id="c5b2e-112">たとえば、JDEdwards です。</span><span class="sxs-lookup"><span data-stu-id="c5b2e-112">For example, JDEdwards.</span></span>  
  
5.  <span data-ttu-id="c5b2e-113">選択**[jdeoneworld]**から、**アダプター**一覧をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="c5b2e-113">Select **JDEOneWorld** from the **Adapter** list, and then click **OK**.</span></span>  
  
## <a name="verifying-the-adapter"></a><span data-ttu-id="c5b2e-114">アダプターの確認</span><span class="sxs-lookup"><span data-stu-id="c5b2e-114">Verifying the Adapter</span></span>  
 <span data-ttu-id="c5b2e-115">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、できることを確認するを確認して、アダプターが正しく機能している、**論理システム**ウィンドウです。</span><span class="sxs-lookup"><span data-stu-id="c5b2e-115">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, you can verify that the adapter is functioning correctly by looking at the **Logical System** window.</span></span> <span data-ttu-id="c5b2e-116">初回のインストレーションでは、このウィンドウは空です。これは、サーバー システムへの接続が未確立で、論理システムが作成されていないからです。</span><span class="sxs-lookup"><span data-stu-id="c5b2e-116">On initial installation, this window is empty because you have not yet established a connection to the server system, nor have you created any logical systems.</span></span>  
  
#### <a name="to-verify-that-the-adapter-is-running-correctly"></a><span data-ttu-id="c5b2e-117">アダプターが正常に動作していることを確認するには</span><span class="sxs-lookup"><span data-stu-id="c5b2e-117">To verify that the adapter is running correctly</span></span>  
  
1.  <span data-ttu-id="c5b2e-118">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、 **BizTalk グループ**、展開**プラットフォームの設定**、展開**アダプター**、し、 **[Jdeoneworld]**です。</span><span class="sxs-lookup"><span data-stu-id="c5b2e-118">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **BizTalk Group**, expand **Platform Settings**, expand **Adapters**, and then select **JDEOneWorld**.</span></span>  
  
2.  <span data-ttu-id="c5b2e-119">詳細ウィンドウで右クリック**BizTalkServerApplication**を選択して**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="c5b2e-119">In the details pane, right-click **BizTalkServerApplication**, and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="c5b2e-120">**[プロパティ]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c5b2e-120">Click the **Properties** tab.</span></span>  
  
4.  <span data-ttu-id="c5b2e-121">SQL 接続パラメーターを設定します。</span><span class="sxs-lookup"><span data-stu-id="c5b2e-121">Set the SQL Connection parameters.</span></span>  
  
    -   <span data-ttu-id="c5b2e-122">**SQL データベース パラメーターを定義する**SQL Server 名とデータベースがインストール時に設定します。</span><span class="sxs-lookup"><span data-stu-id="c5b2e-122">**Define SQL Database Parameters -** The SQL Server Name and Database are those you set at installation.</span></span> <span data-ttu-id="c5b2e-123">これは、テキスト領域がサーバーと、このアダプターのデータベースを再定義できることです。</span><span class="sxs-lookup"><span data-stu-id="c5b2e-123">This is the text area that you can redefine the server and database for this adapter.</span></span>  
  
5.  <span data-ttu-id="c5b2e-124">をクリックして**閉じる**を終了する、**論理システム**ウィンドウです。</span><span class="sxs-lookup"><span data-stu-id="c5b2e-124">Click **Close** to exit the **Logical System** window.</span></span>  
  
     <span data-ttu-id="c5b2e-125">次のステップでは、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] を使用して論理システムを追加します。</span><span class="sxs-lookup"><span data-stu-id="c5b2e-125">Your next step is to add a logical system using [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5b2e-126">参照</span><span class="sxs-lookup"><span data-stu-id="c5b2e-126">See Also</span></span>  
 <span data-ttu-id="c5b2e-127">[計画とアーキテクチャ](../core/planning-and-architecture17.md) </span><span class="sxs-lookup"><span data-stu-id="c5b2e-127">[Planning and Architecture](../core/planning-and-architecture17.md) </span></span>  
 <span data-ttu-id="c5b2e-128">[BizTalk Adapter for JD Edwards OneWorld のセキュリティ](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md) </span><span class="sxs-lookup"><span data-stu-id="c5b2e-128">[Security in BizTalk Adapter for JD Edwards OneWorld](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md) </span></span>  
 [<span data-ttu-id="c5b2e-129">追加の BizTalk Adapter for JD Edwards OneWorld</span><span class="sxs-lookup"><span data-stu-id="c5b2e-129">Adding BizTalk Adapter for JD Edwards OneWorld</span></span>](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md)