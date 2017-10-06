---
title: "手順 1: を作成し、共通のヘッダーと受信確認スキーマを展開 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: interrogative tutorial, headers
ms.assetid: e0f11f58-9a8c-4567-a537-3d182fa7dce2
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a134071ee1973961e0fb4ed9b4da73ad87d8dbb1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-1-create-and-deploy-common-header-and-acknowledgment-schemas"></a><span data-ttu-id="7bcca-102">手順 1: を作成し、共通のヘッダーと受信確認スキーマを展開</span><span class="sxs-lookup"><span data-stu-id="7bcca-102">Step 1: Create and Deploy Common Header and Acknowledgment Schemas</span></span>
<span data-ttu-id="7bcca-103">メッセージ インスタンスのヘッダー (MSH セグメント) を検証するのにには、ヘッダー スキーマを使用します。</span><span class="sxs-lookup"><span data-stu-id="7bcca-103">You use the header schema to validate the header (MSH segment) of the message instance.</span></span> <span data-ttu-id="7bcca-104">メッセージ インスタンスの確認を生成するのにには、受信確認スキーマを使用します。</span><span class="sxs-lookup"><span data-stu-id="7bcca-104">You use the acknowledgment schema to generate the acknowledgment for the message instance.</span></span> <span data-ttu-id="7bcca-105">このプロセスは、HL7 スキーマのすべてのバージョンで共通です。</span><span class="sxs-lookup"><span data-stu-id="7bcca-105">This process is common across all HL7 schema versions.</span></span>  
  
### <a name="to-create-the-header-and-acknowledgment-schemas"></a><span data-ttu-id="7bcca-106">ヘッダーおよび受信確認応答スキーマを作成するには</span><span class="sxs-lookup"><span data-stu-id="7bcca-106">To create the header and acknowledgment schemas</span></span>  
  
1.  <span data-ttu-id="7bcca-107">開始**Microsoft Visual Studio 2012**です。</span><span class="sxs-lookup"><span data-stu-id="7bcca-107">Start **Microsoft Visual Studio 2012**.</span></span>  
  
2.  <span data-ttu-id="7bcca-108">[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]の**ファイル**メニューのをポイント**新規**、クリックして**プロジェクト**です。</span><span class="sxs-lookup"><span data-stu-id="7bcca-108">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], on the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="7bcca-109">新しいプロジェクト] ダイアログ ボックスで、**プロジェクトの種類**一覧で、展開**BizTalk プロジェクト**、し、[ **BTAHL7Projects**です。</span><span class="sxs-lookup"><span data-stu-id="7bcca-109">In the New Project dialog box, in the **Project Types** list, expand **BizTalk Projects**, and then select **BTAHL7Projects**.</span></span>  
  
4.  <span data-ttu-id="7bcca-110">**テンプレート**一覧で、 **BTAHL7V2XCommon プロジェクト**です。</span><span class="sxs-lookup"><span data-stu-id="7bcca-110">In the **Templates** list, select **BTAHL7V2XCommon Project**.</span></span>  
  
5.  <span data-ttu-id="7bcca-111">**名前**フィールドに「 **Interrogative_2XSchemas**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="7bcca-111">In the **Name** field, type **Interrogative_2XSchemas**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="7bcca-112">ソリューション エクスプ ローラーで、プロジェクトに 3 つのスキーマ (ACK_24_GLO_DEF.xsd、ACK_25_GLO_DEF.xsd、および MSH_25_GLO_DEF.xsd) が含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="7bcca-112">In Solution Explorer, notice that three schemas (ACK_24_GLO_DEF.xsd, ACK_25_GLO_DEF.xsd, and MSH_25_GLO_DEF.xsd) are included in the project.</span></span>  
  
     <span data-ttu-id="7bcca-113">Visual Studio は開いたままにしておきます。</span><span class="sxs-lookup"><span data-stu-id="7bcca-113">Leave Visual Studio open.</span></span>  
  
## <a name="step-1a-assign-a-strong-key-to-the-assembly-and-deploy"></a><span data-ttu-id="7bcca-114">手順 1 a: アセンブリに厳密なキーを割り当てると展開</span><span class="sxs-lookup"><span data-stu-id="7bcca-114">Step 1A: Assign a Strong Key to the Assembly and Deploy</span></span>  
 <span data-ttu-id="7bcca-115">アセンブリに厳密なキーを割り当てるし、アセンブリを配置するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="7bcca-115">Use the following procedure to assign a strong key to the assembly and then deploy the assembly.</span></span>  
  
#### <a name="to-assign-a-strong-key-and-deploy-the-assembly"></a><span data-ttu-id="7bcca-116">強力なキーを割り当てるし、アセンブリを展開するには</span><span class="sxs-lookup"><span data-stu-id="7bcca-116">To assign a strong key and deploy the assembly</span></span>  
  
1.  <span data-ttu-id="7bcca-117">開始**Visual Studio 2012 コマンド プロンプト**です。</span><span class="sxs-lookup"><span data-stu-id="7bcca-117">Start **Visual Studio 2012 Command Prompt**.</span></span>  
  
2.  <span data-ttu-id="7bcca-118">[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]コマンド プロンプトで、ディレクトリに移動、 \<*ドライブ*>: \Program Files\Microsoft BizTalk\<バージョン > Accelerator for HL7\SDK\Interrogative チュートリアル フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="7bcca-118">At the [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] command prompt, change your directory to the \<*drive*>:\Program Files\Microsoft BizTalk \<version> Accelerator for HL7\SDK\Interrogative Tutorial folder.</span></span>  
  
3.  <span data-ttu-id="7bcca-119">コマンド プロンプトで次のように入力します。 **sn – k key.snk**、キーを押します**Enter**です。</span><span class="sxs-lookup"><span data-stu-id="7bcca-119">At the command prompt, type **sn –k key.snk**, and then press **Enter**.</span></span> <span data-ttu-id="7bcca-120">成功メッセージが出力ウィンドウに表示されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="7bcca-120">Ensure that a success message appears in the output window.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7bcca-121">使用して、適切なメッセージが表示されない場合[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]アセンブリをトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="7bcca-121">If the correct message does not appear, use [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] to troubleshoot your assembly.</span></span>  
  
4.  <span data-ttu-id="7bcca-122">ソリューション エクスプ ローラーで右クリック**Interrogative_2XSchemas**プロジェクトをクリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="7bcca-122">In Solution Explorer, right-click **Interrogative_2XSchemas** project, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="7bcca-123">Interrogative_2XSchemas プロパティ ページ] ダイアログ ボックスで、[**アセンブリ**です。</span><span class="sxs-lookup"><span data-stu-id="7bcca-123">In the Interrogative_2XSchemas Property Pages dialog box, click **Assembly**.</span></span>  
  
6.  <span data-ttu-id="7bcca-124">右側のペインでスクロールして、**厳密な名前**セクションで、フィールドの右側をクリックして**アセンブリ キー ファイル**、省略記号 (...) ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="7bcca-124">In the right pane, scroll down to the **Strong name** section, click the field to the right of **Assembly Key File**, and then click the ellipsis (…) button.</span></span>  
  
7.  <span data-ttu-id="7bcca-125">アセンブリ キー ファイル ダイアログ ボックスでを参照\<*ドライブ*>: \Program Files\Microsoft BizTalk\<バージョン > Accelerator for HL7\SDK\Interrogative チュートリアルをクリックして**key.snk**、クリックして**開く**です。</span><span class="sxs-lookup"><span data-stu-id="7bcca-125">In the Assembly Key File dialog box, browse to \<*drive*>:\Program Files\Microsoft BizTalk \<version> Accelerator for HL7\SDK\Interrogative Tutorial, click **key.snk**, and then click **Open**.</span></span>  
  
8.  <span data-ttu-id="7bcca-126">Interrogative_2XSchemas プロパティ ページ] ダイアログ ボックスで、[ **OK**して変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="7bcca-126">In the Interrogative_2XSchemas Property Pages dialog box, click **OK** to save your changes.</span></span>  
  
9. <span data-ttu-id="7bcca-127">[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、ソリューション エクスプ ローラーで右クリック**Interrogative_2XSchemas**プロジェクトをクリックして**展開**です。</span><span class="sxs-lookup"><span data-stu-id="7bcca-127">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], in Solution Explorer, right-click **Interrogative_2XSchemas** project, and then click **Deploy**.</span></span> <span data-ttu-id="7bcca-128">成功メッセージが出力ウィンドウに表示を確認します。</span><span class="sxs-lookup"><span data-stu-id="7bcca-128">Ensure a success message appears in the output window.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7bcca-129">使用して、正しい配置メッセージが表示されない場合[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]展開のトラブルシューティングにします。</span><span class="sxs-lookup"><span data-stu-id="7bcca-129">If the correct deploy message does not appear, use [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] to troubleshoot your deployment.</span></span>  
  
 <span data-ttu-id="7bcca-130">進みます[手順 2: V2.4 の一般的なスキーマを作成する](../../adapters-and-accelerators/accelerator-hl7/step-2-create-common-schemas-for-v2-4.md)です。</span><span class="sxs-lookup"><span data-stu-id="7bcca-130">Proceed to [Step 2: Create Common Schemas for V2.4](../../adapters-and-accelerators/accelerator-hl7/step-2-create-common-schemas-for-v2-4.md).</span></span>