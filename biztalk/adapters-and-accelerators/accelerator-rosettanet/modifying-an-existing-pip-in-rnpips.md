---
title: Rnpip の既存の PIP の変更 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- RNPIPs
- modifying, PIPs
- PIPs, modifying
- assemblies, RNPIPs
ms.assetid: f2ed25c4-1979-4691-9315-e7568e7cca8b
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ce7f87d9af24e6388199e76e9cbf0eba076ceacf
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26006291"
---
# <a name="modifying-an-existing-pip-in-rnpips"></a><span data-ttu-id="5583d-102">Rnpip の既存の PIP の変更</span><span class="sxs-lookup"><span data-stu-id="5583d-102">Modifying an Existing PIP in RNPIPs</span></span>
<span data-ttu-id="5583d-103">このトピックを変更し、再デプロイしてインストール プロセス PIP (Partner Interface) スキーマの 1 つの方法について説明[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]セットアップします。</span><span class="sxs-lookup"><span data-stu-id="5583d-103">This topic describes how to change and re-deploy one of the Partner Interface Process (PIP) schemas installed by [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] setup.</span></span> <span data-ttu-id="5583d-104">スキーマは、RNPIP アセンブリの一部として展開します。</span><span class="sxs-lookup"><span data-stu-id="5583d-104">You deploy the schema as part of the RNPIPs assembly.</span></span>  
  
### <a name="to-modify-an-existing-pip-in-rnpips"></a><span data-ttu-id="5583d-105">RNPIP の既存の PIP を変更するには</span><span class="sxs-lookup"><span data-stu-id="5583d-105">To modify an existing PIP in RNPIPs</span></span>  
  
1.  <span data-ttu-id="5583d-106">をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。</span><span class="sxs-lookup"><span data-stu-id="5583d-106">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="5583d-107">検索、 \<*ドライブ*\>\Program Files\Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\utilities\schema Generator フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="5583d-107">Locate the \<*drive*\>\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\Utilities\Schema Generator folder.</span></span>  
  
3.  <span data-ttu-id="5583d-108">コマンド プロンプトで次のように入力します。 **CScript InstallDTD.vbs**、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="5583d-108">At the command prompt, type **CScript InstallDTD.vbs**, and then press ENTER.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5583d-109">のみ、BizTalk Server をインストールした後 1 および 2 の 1 回の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5583d-109">You only have to do steps 1 and 2 one time after you install BizTalk Server.</span></span>  
  
4.  <span data-ttu-id="5583d-110">開始**Microsoft Visual Studio 2012**です。</span><span class="sxs-lookup"><span data-stu-id="5583d-110">Start **Microsoft Visual Studio 2012**.</span></span>  
  
5.  <span data-ttu-id="5583d-111">**ファイル** メニューのをポイント**開く**、クリックして**プロジェクト**です。</span><span class="sxs-lookup"><span data-stu-id="5583d-111">In the **File** menu, point to **Open**, and then click **Project**.</span></span>  
  
6.  <span data-ttu-id="5583d-112">**プロジェクトを開く**] ダイアログ ボックスに移動\<*ドライブ*\>\Program Files\Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\クリックして、スキーマ **[RNPIPs.btproj**です。</span><span class="sxs-lookup"><span data-stu-id="5583d-112">In the **Open Project** dialog box, move to \<*drive*\>\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\Schemas, and then select **RNPIPs.btproj**.</span></span>  
  
7.  <span data-ttu-id="5583d-113">**ビュー**  メニューをクリックして**BizTalk エクスプ ローラー**です。</span><span class="sxs-lookup"><span data-stu-id="5583d-113">In the **View** menu, click **BizTalk Explorer**.</span></span> <span data-ttu-id="5583d-114">展開**アセンブリ**、し、右クリックし、 **Microsoft.Solutions.BTARN.Schemas.RNPIPs(3.3.0.0)** です。</span><span class="sxs-lookup"><span data-stu-id="5583d-114">Expand **Assemblies**, and then right-click **Microsoft.Solutions.BTARN.Schemas.RNPIPs(3.3.0.0)**.</span></span> <span data-ttu-id="5583d-115">をクリックして**展開解除**です。</span><span class="sxs-lookup"><span data-stu-id="5583d-115">Click **Undeploy**.</span></span>  
  
8.  <span data-ttu-id="5583d-116">開始**Visual Studio 2012 コマンド プロンプト**です。</span><span class="sxs-lookup"><span data-stu-id="5583d-116">Start **Visual Studio 2012 Command Prompt**.</span></span>  
  
9. <span data-ttu-id="5583d-117">コマンド プロンプトで「手順 6. で入力した場所に移動**sn-k RNPIPs.snk**、キーを押します**Enter**です。</span><span class="sxs-lookup"><span data-stu-id="5583d-117">Move to the location entered in step 6, at the command prompt, type **sn -k RNPIPs.snk**, and then press **Enter**.</span></span>  
  
10. <span data-ttu-id="5583d-118">ソリューション エクスプ ローラーで右クリック**Rnpip**、 をクリックして**プロパティ**、 をクリックして**共通プロパティ**、クリックして**アセンブリ。**</span><span class="sxs-lookup"><span data-stu-id="5583d-118">In Solution Explorer, right-click **RNPIPs**, click **Properties**, click **Common Properties**, and then click **Assembly.**</span></span>  
  
11. <span data-ttu-id="5583d-119">右側のペインで下にスクロール**厳密名**で、**アセンブリ キー ファイル**セクションで、省略記号ボタン ([...]) ボタンをクリックし、コマンド プロンプトで「手順 6. で入力した場所に移動**RNPIPs.snk**、クリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="5583d-119">In the right pane, scroll down to **Strong Name**, in the **Assembly Key File** section, click the ellipsis button (...) button, go to the location entered in step 6, at the command prompt, type **RNPIPs.snk**, and then click **OK**.</span></span>  
  
12. <span data-ttu-id="5583d-120">**プロパティ ページ**ダイアログ ボックスで、をクリックして**構成プロパティ**、 をクリックして**展開**、 をクリックして**再展開**を選択して`True`、クリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="5583d-120">In the **Property Pages** dialog box, click **Configuration Properties**, click **Deployment**, click **Redeploy**, select `True`, and then click **OK**.</span></span>  
  
13. <span data-ttu-id="5583d-121">必要に応じて RNPIP の既存のスキーマを編集します。</span><span class="sxs-lookup"><span data-stu-id="5583d-121">Edit any of the existing schemas in RNPIPs, as required.</span></span>  
  
14. <span data-ttu-id="5583d-122">をクリックして**ファイル**、クリックして**保存**です。</span><span class="sxs-lookup"><span data-stu-id="5583d-122">Click **File**, and then click **Save**.</span></span>  
  
15. <span data-ttu-id="5583d-123">プロジェクト名を右クリックし、をクリックして**ビルド**です。</span><span class="sxs-lookup"><span data-stu-id="5583d-123">Right-click the project name, and then click **Build**.</span></span>  
  
16. <span data-ttu-id="5583d-124">プロジェクト名を右クリックし、をクリックして**展開**です。</span><span class="sxs-lookup"><span data-stu-id="5583d-124">Right-click the project name, and then click **Deploy**.</span></span>  
  
17. <span data-ttu-id="5583d-125">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="5583d-125">Click **Start**, point to **All Programs**, point to **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
18. <span data-ttu-id="5583d-126">BizTalk 管理コンソールで、展開**Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)] **(ローカル)** の順に展開および**ホスト**です。</span><span class="sxs-lookup"><span data-stu-id="5583d-126">In BizTalk Administration Console, expand **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)] **(Local)**, and then expand **Hosts**.</span></span>  
  
19. <span data-ttu-id="5583d-127">右側のウィンドウで、ホストの名前を右クリックし、をクリックして**停止**です。</span><span class="sxs-lookup"><span data-stu-id="5583d-127">In the right pane, right-click the name of the host, and then click **Stop**.</span></span> <span data-ttu-id="5583d-128">サービスが停止した後、ホストの名前を右クリックし、をクリックして**開始**です。</span><span class="sxs-lookup"><span data-stu-id="5583d-128">After the service has stopped, right-click the name of the host, and then click **Start**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5583d-129">参照</span><span class="sxs-lookup"><span data-stu-id="5583d-129">See Also</span></span>  
 <span data-ttu-id="5583d-130">[プログラミング ガイド](../../adapters-and-accelerators/accelerator-rosettanet/programming-guide2.md) </span><span class="sxs-lookup"><span data-stu-id="5583d-130">[Programming Guide](../../adapters-and-accelerators/accelerator-rosettanet/programming-guide2.md) </span></span>  
 [<span data-ttu-id="5583d-131">新しい Partner Interface Process の組み込み</span><span class="sxs-lookup"><span data-stu-id="5583d-131">Incorporating a New Partner Interface Process</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/incorporating-a-new-partner-interface-process.md)