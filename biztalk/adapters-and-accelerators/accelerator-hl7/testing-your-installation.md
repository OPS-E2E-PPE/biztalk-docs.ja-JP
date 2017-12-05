---
title: "インストールのテスト |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- testing installation
- installing, testing installation
ms.assetid: db27a75c-db7f-46ff-b8ef-2624ff18dcc8
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b7fc94930ba5ff0851114e36d728ee7f3ffb73ab
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="testing-your-installation"></a><span data-ttu-id="4f1fa-102">インストールのテスト</span><span class="sxs-lookup"><span data-stu-id="4f1fa-102">Testing Your Installation</span></span>
<span data-ttu-id="4f1fa-103">設定することができます、[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]テスト、エンド ツー エンド チュートリアルを手動で実行して、またはエンド ツー エンド チュートリアル プログラムを実行してインストールします。</span><span class="sxs-lookup"><span data-stu-id="4f1fa-103">You can set up your [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] installation for testing either by manually running through the end-to-end tutorial or by executing the end-to-end tutorial program.</span></span> <span data-ttu-id="4f1fa-104">プログラムを実行するをクリックするか、 **Launch Tutorial**セットアップ中にボタンをクリックしてしたり、C:\Program files \microsoft BizTalk で EndToEndTutorial.exe を実行\<バージョン\>HL7\SDK\ のアクセラレータエンド ツー エンド チュートリアル フォルダー (インストールと構成を実行している)。</span><span class="sxs-lookup"><span data-stu-id="4f1fa-104">To exercise the program, either click the **Launch Tutorial** button during setup or execute EndToEndTutorial.exe in the C:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\End-to-End Tutorial folder (after running installation and configuration).</span></span> <span data-ttu-id="4f1fa-105">これらの自動化されたアクションのいずれかの操作はチュートリアルを実行して、手動で実行する同じセットアップ手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="4f1fa-105">Either of these automated actions will perform the same setup steps that you would manually perform by running through the tutorial.</span></span> <span data-ttu-id="4f1fa-106">エンド ツー エンド チュートリアル プログラムは次のとおり</span><span class="sxs-lookup"><span data-stu-id="4f1fa-106">The end-to-end tutorial program does the following:</span></span>  
  
-   <span data-ttu-id="4f1fa-107">MSH と確認のスキーマを展開します。</span><span class="sxs-lookup"><span data-stu-id="4f1fa-107">Deploys MSH and ACK schemas</span></span>  
  
-   <span data-ttu-id="4f1fa-108">Version 2.3.1 の一般的なスキーマを展開します。</span><span class="sxs-lookup"><span data-stu-id="4f1fa-108">Deploys Version 2.3.1 common schemas</span></span>  
  
-   <span data-ttu-id="4f1fa-109">ADT スキーマを展開します。</span><span class="sxs-lookup"><span data-stu-id="4f1fa-109">Deploys ADT schemas</span></span>  
  
-   <span data-ttu-id="4f1fa-110">作成、Tutorial_1WayReceive 受信ポート</span><span class="sxs-lookup"><span data-stu-id="4f1fa-110">Creates the Tutorial_1WayReceive receive port</span></span>  
  
-   <span data-ttu-id="4f1fa-111">作成、Tutorial_MLLPReceive 受信場所</span><span class="sxs-lookup"><span data-stu-id="4f1fa-111">Creates the Tutorial_MLLPReceive receive location</span></span>  
  
-   <span data-ttu-id="4f1fa-112">作成、Tutorial_BTAHL7PickUp 受信ポート</span><span class="sxs-lookup"><span data-stu-id="4f1fa-112">Creates the Tutorial_BTAHL7PickUp receive port</span></span>  
  
-   <span data-ttu-id="4f1fa-113">作成、Tutorial_FileReceiveLoc 受信場所</span><span class="sxs-lookup"><span data-stu-id="4f1fa-113">Creates the Tutorial_FileReceiveLoc receive location</span></span>  
  
-   <span data-ttu-id="4f1fa-114">Tutorial_sendAck_ADT 送信ポートが作成されます。</span><span class="sxs-lookup"><span data-stu-id="4f1fa-114">Creates the Tutorial_sendAck_ADT send port</span></span>  
  
-   <span data-ttu-id="4f1fa-115">Tutorial_sendMsg_RX 送信ポートが作成されます。</span><span class="sxs-lookup"><span data-stu-id="4f1fa-115">Creates the Tutorial_sendMsg_RX send port</span></span>  
  
-   <span data-ttu-id="4f1fa-116">Tutorial_BTAHL7Drop 送信ポートが作成されます。</span><span class="sxs-lookup"><span data-stu-id="4f1fa-116">Creates the Tutorial_BTAHL7Drop send port</span></span>  
  
-   <span data-ttu-id="4f1fa-117">Tutorial_MLLPSend 送信ポートが作成されます。</span><span class="sxs-lookup"><span data-stu-id="4f1fa-117">Creates the Tutorial_MLLPSend send port</span></span>  
  
-   <span data-ttu-id="4f1fa-118">Tutorial_ADTSystem パーティを作成します。</span><span class="sxs-lookup"><span data-stu-id="4f1fa-118">Creates the Tutorial_ADTSystem party</span></span>  
  
-   <span data-ttu-id="4f1fa-119">Tutorial_RXSystem パーティを作成します。</span><span class="sxs-lookup"><span data-stu-id="4f1fa-119">Creates the Tutorial_RXSystem party</span></span>  
  
-   <span data-ttu-id="4f1fa-120">Tutorial_HISystem パーティを作成します。</span><span class="sxs-lookup"><span data-stu-id="4f1fa-120">Creates the Tutorial_HISystem party</span></span>  
  
-   <span data-ttu-id="4f1fa-121">BizTalk サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="4f1fa-121">Restarts the BizTalk Service</span></span>  
  
 <span data-ttu-id="4f1fa-122">エンド ツー エンド チュートリアル プログラムを実行した場合は、事前に定義されたフォルダーに HL7 のテスト インスタンスを削除できます。</span><span class="sxs-lookup"><span data-stu-id="4f1fa-122">If you have executed the end-to-end tutorial program, you can drop a test instance for HL7 in a pre-defined folder.</span></span> <span data-ttu-id="4f1fa-123">フォルダーに関連付けられている受信パイプラインは、メッセージを取得し、それを処理します。</span><span class="sxs-lookup"><span data-stu-id="4f1fa-123">The receive pipeline associated with the folder picks up the message and processes it.</span></span> <span data-ttu-id="4f1fa-124">フィルターに基づいて、送信パイプラインは、コピー先のフォルダーにドキュメントをルーティングします。</span><span class="sxs-lookup"><span data-stu-id="4f1fa-124">Based on filters, a send pipeline routes the document to the destination folder.</span></span> <span data-ttu-id="4f1fa-125">単純な「ラウンド トリップ」がこの基本的な構成要素の実行、 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) エンジンし、インストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4f1fa-125">This simple "round-trip" exercises the basic building blocks of the [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) engine and confirms your installation.</span></span>  
  
### <a name="to-test-your-installation"></a><span data-ttu-id="4f1fa-126">インストールをテストするには</span><span class="sxs-lookup"><span data-stu-id="4f1fa-126">To test your installation</span></span>  
  
1.  <span data-ttu-id="4f1fa-127">使用して[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]エクスプ ローラーで、参照、 \<*ドライブ*\>: \Program Files\Microsoft BizTalk\<バージョン\>Accelerator for HL7\SDK\End エンドツー エンド チュートリアル フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="4f1fa-127">Using [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Explorer, browse to the \<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\End-to-End Tutorial folder.</span></span>  
  
2.  <span data-ttu-id="4f1fa-128">右クリックし、 **TutorialSampleInstance.txt**ファイルを開き、をクリックして**コピー**です。</span><span class="sxs-lookup"><span data-stu-id="4f1fa-128">Right-click the **TutorialSampleInstance.txt** file, and then click **Copy**.</span></span>  
  
3.  <span data-ttu-id="4f1fa-129">使用して[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]エクスプ ローラーで、参照、 \<*ドライブ*\>: \Program Files\Microsoft BizTalk\<バージョン\>HL7\SDK\End エンドツー エンド Tutorial\Tutorial_ のアクセラレータBTAHL7PickUp フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="4f1fa-129">Using [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Explorer, browse to the \<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\End-to-End Tutorial\Tutorial_BTAHL7PickUp folder.</span></span>  
  
4.  <span data-ttu-id="4f1fa-130">フォルダーを右クリックし、をクリックして**貼り付け**です。</span><span class="sxs-lookup"><span data-stu-id="4f1fa-130">Right-click the folder, and then click **Paste**.</span></span>  
  
5.  <span data-ttu-id="4f1fa-131">使用して[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]エクスプ ローラーで、参照、 \<*ドライブ*\>: \Program Files\Microsoft BizTalk\<バージョン\>HL7\SDK\End エンドツー エンド Tutorial\Tutorial_ のアクセラレータBTAHL7Drop フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="4f1fa-131">Using [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Explorer, browse to the \<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\End-to-End Tutorial\Tutorial_BTAHL7Drop folder.</span></span>  
  
     <span data-ttu-id="4f1fa-132">かどうか、インストールが正常に処理済みのインスタンスが表示される場合を確認することができます、 **Tutorial_BTAHL7Drop**としてフォルダー \< *Guid*\>.txt です。</span><span class="sxs-lookup"><span data-stu-id="4f1fa-132">You can verify if your installation was successful if the processed instance appears in the **Tutorial_BTAHL7Drop** folder as \<*Guid*\>.txt.</span></span>  
  
 <span data-ttu-id="4f1fa-133">次の手順に進む[、チュートリアルを使用する準備](../../adapters-and-accelerators/accelerator-hl7/preparing-to-use-the-tutorial2.md)です。</span><span class="sxs-lookup"><span data-stu-id="4f1fa-133">Proceed to the next step, [Preparing to Use the Tutorial](../../adapters-and-accelerators/accelerator-hl7/preparing-to-use-the-tutorial2.md).</span></span>