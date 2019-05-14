---
title: Rnpip の既存の PIP の変更 |Microsoft Docs
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
ms.openlocfilehash: c9f7b7bf3f3095e5ac1f5bc87b730935de70d63e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65282916"
---
# <a name="modifying-an-existing-pip-in-rnpips"></a><span data-ttu-id="9eda5-102">Rnpip の既存の PIP の変更</span><span class="sxs-lookup"><span data-stu-id="9eda5-102">Modifying an Existing PIP in RNPIPs</span></span>
<span data-ttu-id="9eda5-103">このトピックでは、変更し、Microsoft がインストールされているパートナー インターフェイス Process (PIP) スキーマの 1 つを再デプロイする方法を説明します[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]セットアップします。</span><span class="sxs-lookup"><span data-stu-id="9eda5-103">This topic describes how to change and re-deploy one of the Partner Interface Process (PIP) schemas installed by Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] setup.</span></span> <span data-ttu-id="9eda5-104">Rnpip アセンブリの一部としてスキーマを展開するとします。</span><span class="sxs-lookup"><span data-stu-id="9eda5-104">You deploy the schema as part of the RNPIPs assembly.</span></span>  
  
### <a name="to-modify-an-existing-pip-in-rnpips"></a><span data-ttu-id="9eda5-105">Rnpip の既存の PIP を変更するには</span><span class="sxs-lookup"><span data-stu-id="9eda5-105">To modify an existing PIP in RNPIPs</span></span>  
  
1. <span data-ttu-id="9eda5-106">をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。</span><span class="sxs-lookup"><span data-stu-id="9eda5-106">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="9eda5-107">検索、 \<*ドライブ*\>\Program Files\Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\utilities\schema Generator フォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="9eda5-107">Locate the \<*drive*\>\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\Utilities\Schema Generator folder.</span></span>  
  
3. <span data-ttu-id="9eda5-108">コマンド プロンプトで「 **CScript InstallDTD.vbs**し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="9eda5-108">At the command prompt, type **CScript InstallDTD.vbs**, and then press ENTER.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="9eda5-109">のみ、BizTalk Server をインストールした後 1 と 2 つの 1 回の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9eda5-109">You only have to do steps 1 and 2 one time after you install BizTalk Server.</span></span>  
  
4. <span data-ttu-id="9eda5-110">開始**Microsoft Visual Studio 2012**します。</span><span class="sxs-lookup"><span data-stu-id="9eda5-110">Start **Microsoft Visual Studio 2012**.</span></span>  
  
5. <span data-ttu-id="9eda5-111">**ファイル**メニューで、**オープン**、 をクリックし、**プロジェクト**します。</span><span class="sxs-lookup"><span data-stu-id="9eda5-111">In the **File** menu, point to **Open**, and then click **Project**.</span></span>  
  
6. <span data-ttu-id="9eda5-112">**プロジェクトを開く** ダイアログ ボックスに移動\<*ドライブ*\>\Program Files\Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\スキーマ、および選択**RNPIPs.btproj**します。</span><span class="sxs-lookup"><span data-stu-id="9eda5-112">In the **Open Project** dialog box, move to \<*drive*\>\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\Schemas, and then select **RNPIPs.btproj**.</span></span>  
  
7. <span data-ttu-id="9eda5-113">**ビュー**  メニューのをクリックして**BizTalk エクスプ ローラー**します。</span><span class="sxs-lookup"><span data-stu-id="9eda5-113">In the **View** menu, click **BizTalk Explorer**.</span></span> <span data-ttu-id="9eda5-114">展開**アセンブリ**、右クリックし、 **Microsoft.Solutions.BTARN.Schemas.RNPIPs(3.3.0.0)** します。</span><span class="sxs-lookup"><span data-stu-id="9eda5-114">Expand **Assemblies**, and then right-click **Microsoft.Solutions.BTARN.Schemas.RNPIPs(3.3.0.0)**.</span></span> <span data-ttu-id="9eda5-115">クリックして**展開解除**します。</span><span class="sxs-lookup"><span data-stu-id="9eda5-115">Click **Undeploy**.</span></span>  
  
8. <span data-ttu-id="9eda5-116">開始**Visual Studio 2012 のコマンド プロンプト**します。</span><span class="sxs-lookup"><span data-stu-id="9eda5-116">Start **Visual Studio 2012 Command Prompt**.</span></span>  
  
9. <span data-ttu-id="9eda5-117">型であるコマンド プロンプトで、手順 6. で入力した場所に移動**sn-k RNPIPs.snk**、し、キーを押します**Enter**します。</span><span class="sxs-lookup"><span data-stu-id="9eda5-117">Move to the location entered in step 6, at the command prompt, type **sn -k RNPIPs.snk**, and then press **Enter**.</span></span>  
  
10. <span data-ttu-id="9eda5-118">ソリューション エクスプ ローラーで右クリックして**Rnpip**、 をクリックして**プロパティ**、 をクリックして**共通プロパティ**、 をクリックし、**アセンブリ。**</span><span class="sxs-lookup"><span data-stu-id="9eda5-118">In Solution Explorer, right-click **RNPIPs**, click **Properties**, click **Common Properties**, and then click **Assembly.**</span></span>  
  
11. <span data-ttu-id="9eda5-119">右側のペインでスクロールして**厳密な名前**の**アセンブリ キー ファイル**セクションで、省略記号ボタン (…) ボタンをクリックして、型、コマンド プロンプトで、手順 6. で入力した場所に移動**RNPIPs.snk**、 をクリックし、 **OK**します。</span><span class="sxs-lookup"><span data-stu-id="9eda5-119">In the right pane, scroll down to **Strong Name**, in the **Assembly Key File** section, click the ellipsis button (...) button, go to the location entered in step 6, at the command prompt, type **RNPIPs.snk**, and then click **OK**.</span></span>  
  
12. <span data-ttu-id="9eda5-120">**プロパティ ページ**ダイアログ ボックスで、をクリックして**構成プロパティ**、 をクリックして**展開**、 をクリックして**再デプロイ**を選択します`True`。、 をクリックし、 **OK**します。</span><span class="sxs-lookup"><span data-stu-id="9eda5-120">In the **Property Pages** dialog box, click **Configuration Properties**, click **Deployment**, click **Redeploy**, select `True`, and then click **OK**.</span></span>  
  
13. <span data-ttu-id="9eda5-121">必要に応じてで Rnpip の既存のスキーマのいずれかを編集します。</span><span class="sxs-lookup"><span data-stu-id="9eda5-121">Edit any of the existing schemas in RNPIPs, as required.</span></span>  
  
14. <span data-ttu-id="9eda5-122">クリックして**ファイル**、 をクリックし、**保存**します。</span><span class="sxs-lookup"><span data-stu-id="9eda5-122">Click **File**, and then click **Save**.</span></span>  
  
15. <span data-ttu-id="9eda5-123">プロジェクト名を右クリックし、**ビルド**します。</span><span class="sxs-lookup"><span data-stu-id="9eda5-123">Right-click the project name, and then click **Build**.</span></span>  
  
16. <span data-ttu-id="9eda5-124">プロジェクト名を右クリックし、**デプロイ**します。</span><span class="sxs-lookup"><span data-stu-id="9eda5-124">Right-click the project name, and then click **Deploy**.</span></span>  
  
17. <span data-ttu-id="9eda5-125">**[スタート]** ボタンをクリックして、 **[すべてのプログラム]**、 \*\*Microsoft\*\*\*\* [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]の順にポイントし、 **[BizTalk Server 管理]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9eda5-125">Click **Start**, point to **All Programs**, point to **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
18. <span data-ttu-id="9eda5-126">BizTalk 管理コンソールで  **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)] **(Local)**、順に展開**ホスト**します。</span><span class="sxs-lookup"><span data-stu-id="9eda5-126">In BizTalk Administration Console, expand **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)] **(Local)**, and then expand **Hosts**.</span></span>  
  
19. <span data-ttu-id="9eda5-127">右側のウィンドウで、ホストの名前を右クリックし をクリックし、**停止**します。</span><span class="sxs-lookup"><span data-stu-id="9eda5-127">In the right pane, right-click the name of the host, and then click **Stop**.</span></span> <span data-ttu-id="9eda5-128">サービスが停止したら、ホストの名前を右クリックし をクリックし、**開始**します。</span><span class="sxs-lookup"><span data-stu-id="9eda5-128">After the service has stopped, right-click the name of the host, and then click **Start**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9eda5-129">参照</span><span class="sxs-lookup"><span data-stu-id="9eda5-129">See Also</span></span>  
 <span data-ttu-id="9eda5-130">[プログラミング ガイド](../../adapters-and-accelerators/accelerator-rosettanet/programming-guide2.md) </span><span class="sxs-lookup"><span data-stu-id="9eda5-130">[Programming Guide](../../adapters-and-accelerators/accelerator-rosettanet/programming-guide2.md) </span></span>  
 [<span data-ttu-id="9eda5-131">新しい Partner Interface Process の組み込み</span><span class="sxs-lookup"><span data-stu-id="9eda5-131">Incorporating a New Partner Interface Process</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/incorporating-a-new-partner-interface-process.md)