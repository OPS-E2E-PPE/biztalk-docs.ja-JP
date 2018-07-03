---
title: '手順 1: を作成し、一般的なヘッダーと確認スキーマの展開 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- interrogative tutorial, headers
ms.assetid: e0f11f58-9a8c-4567-a537-3d182fa7dce2
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 988c2922d09412aa248c08c36e727709d45e5a66
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989267"
---
# <a name="step-1-create-and-deploy-common-header-and-acknowledgment-schemas"></a><span data-ttu-id="ae2b2-102">手順 1: を作成し、一般的なヘッダーと確認スキーマをデプロイします。</span><span class="sxs-lookup"><span data-stu-id="ae2b2-102">Step 1: Create and Deploy Common Header and Acknowledgment Schemas</span></span>
<span data-ttu-id="ae2b2-103">メッセージ インスタンスのヘッダー (MSH セグメント) を検証するのにには、ヘッダー スキーマを使用します。</span><span class="sxs-lookup"><span data-stu-id="ae2b2-103">You use the header schema to validate the header (MSH segment) of the message instance.</span></span> <span data-ttu-id="ae2b2-104">受信確認メッセージのインスタンスを生成するのにには、受信確認スキーマを使用します。</span><span class="sxs-lookup"><span data-stu-id="ae2b2-104">You use the acknowledgment schema to generate the acknowledgment for the message instance.</span></span> <span data-ttu-id="ae2b2-105">このプロセスは、HL7 スキーマのすべてのバージョン間で共通です。</span><span class="sxs-lookup"><span data-stu-id="ae2b2-105">This process is common across all HL7 schema versions.</span></span>  
  
### <a name="to-create-the-header-and-acknowledgment-schemas"></a><span data-ttu-id="ae2b2-106">ヘッダーと受信確認スキーマを作成するには</span><span class="sxs-lookup"><span data-stu-id="ae2b2-106">To create the header and acknowledgment schemas</span></span>  
  
1. <span data-ttu-id="ae2b2-107">開始**Microsoft Visual Studio 2012**します。</span><span class="sxs-lookup"><span data-stu-id="ae2b2-107">Start **Microsoft Visual Studio 2012**.</span></span>  
  
2. <span data-ttu-id="ae2b2-108">[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], の **ファイル** メニューをポイント **新規**, 、クリックして **プロジェクト**します。</span><span class="sxs-lookup"><span data-stu-id="ae2b2-108">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], on the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
3. <span data-ttu-id="ae2b2-109">新しいプロジェクト] ダイアログ ボックスで、**プロジェクトの種類**一覧で、展開**BizTalk プロジェクト**、し、[ **BTAHL7Projects**します。</span><span class="sxs-lookup"><span data-stu-id="ae2b2-109">In the New Project dialog box, in the **Project Types** list, expand **BizTalk Projects**, and then select **BTAHL7Projects**.</span></span>  
  
4. <span data-ttu-id="ae2b2-110">**テンプレート**一覧で、 **BTAHL7V2XCommon プロジェクト**します。</span><span class="sxs-lookup"><span data-stu-id="ae2b2-110">In the **Templates** list, select **BTAHL7V2XCommon Project**.</span></span>  
  
5. <span data-ttu-id="ae2b2-111">**名前**フィールドに「 **Interrogative_2XSchemas**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="ae2b2-111">In the **Name** field, type **Interrogative_2XSchemas**, and then click **OK**.</span></span>  
  
    <span data-ttu-id="ae2b2-112">ソリューション エクスプ ローラーでは、(ACK_24_GLO_DEF.xsd、ACK_25_GLO_DEF.xsd、および MSH_25_GLO_DEF.xsd) の 3 つのスキーマをプロジェクトに含まれることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="ae2b2-112">In Solution Explorer, notice that three schemas (ACK_24_GLO_DEF.xsd, ACK_25_GLO_DEF.xsd, and MSH_25_GLO_DEF.xsd) are included in the project.</span></span>  
  
    <span data-ttu-id="ae2b2-113">Visual Studio は開いたままにしておきます。</span><span class="sxs-lookup"><span data-stu-id="ae2b2-113">Leave Visual Studio open.</span></span>  
  
## <a name="step-1a-assign-a-strong-key-to-the-assembly-and-deploy"></a><span data-ttu-id="ae2b2-114">手順 1 a: アセンブリに厳密なキーを割り当てるとデプロイ</span><span class="sxs-lookup"><span data-stu-id="ae2b2-114">Step 1A: Assign a Strong Key to the Assembly and Deploy</span></span>  
 <span data-ttu-id="ae2b2-115">アセンブリに厳密なキーを割り当てるし、アセンブリを配置するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="ae2b2-115">Use the following procedure to assign a strong key to the assembly and then deploy the assembly.</span></span>  
  
#### <a name="to-assign-a-strong-key-and-deploy-the-assembly"></a><span data-ttu-id="ae2b2-116">強力なキーを割り当てるし、アセンブリを展開するには</span><span class="sxs-lookup"><span data-stu-id="ae2b2-116">To assign a strong key and deploy the assembly</span></span>  
  
1. <span data-ttu-id="ae2b2-117">開始**Visual Studio 2012 のコマンド プロンプト**します。</span><span class="sxs-lookup"><span data-stu-id="ae2b2-117">Start **Visual Studio 2012 Command Prompt**.</span></span>  
  
2. <span data-ttu-id="ae2b2-118">[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]コマンド プロンプトで、ディレクトリの変更、 \<*ドライブ*\>: \Program Files\Microsoft BizTalk\<バージョン\>HL7\SDK\Interrogative のアクセラレータチュートリアル フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="ae2b2-118">At the [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] command prompt, change your directory to the \<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\Interrogative Tutorial folder.</span></span>  
  
3. <span data-ttu-id="ae2b2-119">コマンド プロンプトで「 **sn – k key.snk**、押します **」と入力**します。</span><span class="sxs-lookup"><span data-stu-id="ae2b2-119">At the command prompt, type **sn –k key.snk**, and then press **Enter**.</span></span> <span data-ttu-id="ae2b2-120">成功メッセージが出力ウィンドウに表示されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ae2b2-120">Ensure that a success message appears in the output window.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="ae2b2-121">適切なメッセージが表示されない場合は、使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]アセンブリのトラブルシューティングを行う。</span><span class="sxs-lookup"><span data-stu-id="ae2b2-121">If the correct message does not appear, use [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] to troubleshoot your assembly.</span></span>  
  
4. <span data-ttu-id="ae2b2-122">ソリューション エクスプ ローラーで右クリックして**Interrogative_2XSchemas**プロジェクトをクリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="ae2b2-122">In Solution Explorer, right-click **Interrogative_2XSchemas** project, and then click **Properties**.</span></span>  
  
5. <span data-ttu-id="ae2b2-123">Interrogative_2XSchemas プロパティ ページ] ダイアログ ボックスで、[**アセンブリ**します。</span><span class="sxs-lookup"><span data-stu-id="ae2b2-123">In the Interrogative_2XSchemas Property Pages dialog box, click **Assembly**.</span></span>  
  
6. <span data-ttu-id="ae2b2-124">右側のペインでスクロールして、**厳密な名前**セクションで、フィールドの右側をクリックして**アセンブリ キー ファイル**、省略記号 (...) ボタンを順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="ae2b2-124">In the right pane, scroll down to the **Strong name** section, click the field to the right of **Assembly Key File**, and then click the ellipsis (…) button.</span></span>  
  
7. <span data-ttu-id="ae2b2-125">アセンブリ キー ファイル ダイアログ ボックスを参照\<*ドライブ*\>: \Program Files\Microsoft BizTalk\<バージョン\>HL7\SDK\Interrogative チュートリアルでは、アクセラレータをクリックします**key.snk**、 をクリックし、**オープン**します。</span><span class="sxs-lookup"><span data-stu-id="ae2b2-125">In the Assembly Key File dialog box, browse to \<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\Interrogative Tutorial, click **key.snk**, and then click **Open**.</span></span>  
  
8. <span data-ttu-id="ae2b2-126">Interrogative_2XSchemas プロパティ ページ] ダイアログ ボックスで、[ **OK**変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="ae2b2-126">In the Interrogative_2XSchemas Property Pages dialog box, click **OK** to save your changes.</span></span>  
  
9. <span data-ttu-id="ae2b2-127">[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、ソリューション エクスプ ローラーで右クリック**Interrogative_2XSchemas**プロジェクトをクリックして**デプロイ**します。</span><span class="sxs-lookup"><span data-stu-id="ae2b2-127">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], in Solution Explorer, right-click **Interrogative_2XSchemas** project, and then click **Deploy**.</span></span> <span data-ttu-id="ae2b2-128">成功メッセージが出力ウィンドウに表示を確認します。</span><span class="sxs-lookup"><span data-stu-id="ae2b2-128">Ensure a success message appears in the output window.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="ae2b2-129">デプロイの適切なメッセージが表示されない場合は、使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]デプロイのトラブルシューティングを行う。</span><span class="sxs-lookup"><span data-stu-id="ae2b2-129">If the correct deploy message does not appear, use [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] to troubleshoot your deployment.</span></span>  
  
   <span data-ttu-id="ae2b2-130">進みます[手順 2: V2.4 の一般的なスキーマを作成する](../../adapters-and-accelerators/accelerator-hl7/step-2-create-common-schemas-for-v2-4.md)します。</span><span class="sxs-lookup"><span data-stu-id="ae2b2-130">Proceed to [Step 2: Create Common Schemas for V2.4](../../adapters-and-accelerators/accelerator-hl7/step-2-create-common-schemas-for-v2-4.md).</span></span>