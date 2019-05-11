---
title: 手順 1:ヘッダーと確認スキーマ作成および展開 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- end-to-end tutorial, header schemas
- header schemas
ms.assetid: 3ff013a4-6c67-4bac-be97-81b2dc5b6119
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 03782a8c2692dea4af7df9e3e03526a919940257
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65288897"
---
# <a name="step-1-create-and-deploy-header-and-acknowledgment-schemas"></a><span data-ttu-id="4a391-102">手順 1:ヘッダーと確認スキーマ作成およびデプロイ</span><span class="sxs-lookup"><span data-stu-id="4a391-102">Step 1: Create and Deploy Header and Acknowledgment Schemas</span></span>
<span data-ttu-id="4a391-103">メッセージ インスタンスのヘッダー (MSH セグメント) を検証するのにには、ヘッダー スキーマを使用します。</span><span class="sxs-lookup"><span data-stu-id="4a391-103">You use the header schema to validate the header (MSH segment) of the message instance.</span></span> <span data-ttu-id="4a391-104">受信確認メッセージのインスタンスを生成するのにには、受信確認スキーマを使用します。</span><span class="sxs-lookup"><span data-stu-id="4a391-104">You use the acknowledgment schema to generate the acknowledgment for the message instance.</span></span> <span data-ttu-id="4a391-105">このプロセスは、すべてのスキーマ バージョンの間で共通[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]2.X。</span><span class="sxs-lookup"><span data-stu-id="4a391-105">This process is common across all schemas versions of [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 2.X.</span></span>  
  
### <a name="to-create-the-header-and-acknowledgment-schemas"></a><span data-ttu-id="4a391-106">ヘッダーと受信確認スキーマを作成するには</span><span class="sxs-lookup"><span data-stu-id="4a391-106">To create the header and acknowledgment schemas</span></span>  
  
1. <span data-ttu-id="4a391-107">開始**Microsoft Visual Studio 2012**します。</span><span class="sxs-lookup"><span data-stu-id="4a391-107">Start **Microsoft Visual Studio 2012**.</span></span>  
  
2. <span data-ttu-id="4a391-108">[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], の **ファイル** メニューをポイント **新規**, 、クリックして **プロジェクト**します。</span><span class="sxs-lookup"><span data-stu-id="4a391-108">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], on the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
3. <span data-ttu-id="4a391-109">新しいプロジェクト] ダイアログ ボックスで、**プロジェクトの種類**セクションで、展開**BizTalk プロジェクト**、し、[ **BTAHL7Projects**します。</span><span class="sxs-lookup"><span data-stu-id="4a391-109">In the New Project dialog box, in the **Project Types** section, expand **BizTalk Projects**, and then select **BTAHL7Projects**.</span></span>  
  
4. <span data-ttu-id="4a391-110">テンプレート セクションで**BTAHL7V2XCommon プロジェクト**、 をクリックし、 **OK**。</span><span class="sxs-lookup"><span data-stu-id="4a391-110">In the Templates section, select **BTAHL7V2XCommon Project**, and then click **OK**.</span></span>  
  
    <span data-ttu-id="4a391-111">ソリューション エクスプ ローラーでは、(ACK_24_GLO_DEF.xsd ACK_25_GLO_DEF.xsd、および MSH_25_GLO_DEF.xsd) の 3 つのスキーマをプロジェクトに含まれることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="4a391-111">In Solution Explorer, notice that the three schemas (ACK_24_GLO_DEF.xsd ACK_25_GLO_DEF.xsd, and MSH_25_GLO_DEF.xsd) are included in the project.</span></span>  
  
## <a name="step-1a-assign-a-strong-key-to-the-assembly-and-deploy"></a><span data-ttu-id="4a391-112">手順 1 a:アセンブリに厳密なキーを割り当てるとデプロイ</span><span class="sxs-lookup"><span data-stu-id="4a391-112">Step 1A: Assign a Strong Key to the Assembly and Deploy</span></span>  
 <span data-ttu-id="4a391-113">アセンブリに厳密なキーを割り当てるし、アセンブリを配置するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="4a391-113">Use the following procedure to assign a strong key to the assembly and then deploy the assembly.</span></span>  
  
#### <a name="to-assign-a-strong-key-and-deploy-the-assembly"></a><span data-ttu-id="4a391-114">強力なキーを割り当てるし、アセンブリを展開するには</span><span class="sxs-lookup"><span data-stu-id="4a391-114">To assign a strong key and deploy the assembly</span></span>  
  
1. <span data-ttu-id="4a391-115">開始**Visual Studio 2012 のコマンド プロンプト**します。</span><span class="sxs-lookup"><span data-stu-id="4a391-115">Start **Visual Studio 2012 Command Prompt**.</span></span>  
  
2. <span data-ttu-id="4a391-116">[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]コマンド プロンプトで、参照、 \<*ドライブ*\>: \Program Files\\Microsoft BizTalk\<バージョン\>Accelerator for HL7 \SDK\End-to-Endチュートリアル フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="4a391-116">At the [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] command prompt, browse to the \<*drive*\>:\Program Files\\Microsoft BizTalk \<version\> Accelerator for HL7 \SDK\End-to-End Tutorial folder.</span></span>  
  
3. <span data-ttu-id="4a391-117">コマンド プロンプトで「 **sn – k key.snk**し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="4a391-117">At the command prompt, type **sn –k key.snk**, and then press ENTER.</span></span> <span data-ttu-id="4a391-118">出力 ウィンドウで次の成功メッセージが表示されることを確認し、コマンド ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="4a391-118">Ensure the following success message appears in the output window, and then close the command window.</span></span>  
  
    <span data-ttu-id="4a391-119">**「キーの key.snk に書き込まれるペアです。」**</span><span class="sxs-lookup"><span data-stu-id="4a391-119">**"Key pair written to key.snk."**</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="4a391-120">適切なメッセージが表示されない場合は、使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]アセンブリのトラブルシューティングを行う。</span><span class="sxs-lookup"><span data-stu-id="4a391-120">If the correct message does not appear, use [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] to troubleshoot your assembly.</span></span>  
  
4. <span data-ttu-id="4a391-121">ソリューション エクスプ ローラーで右クリックして**BTAHL7V2XCommon Project1**、 をクリックし、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="4a391-121">In Solution Explorer, right-click **BTAHL7V2XCommon Project1**, and then click **Properties**.</span></span>  
  
5. <span data-ttu-id="4a391-122">BTAHL7V2XCommon Project1 プロパティ ページ ページで、次のようにクリックします。**アセンブリ**します。</span><span class="sxs-lookup"><span data-stu-id="4a391-122">On the BTAHL7V2XCommon Project1 Property Pages page, click **Assembly**.</span></span>  
  
6. <span data-ttu-id="4a391-123">右側のペインでスクロールして、**厳密な名前**セクションで、フィールドの右側をクリックして**アセンブリ キー ファイル**、クリックして、省略記号 (**.**) ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="4a391-123">In the right pane, scroll down to the **Strong name** section, click the field to the right of **Assembly Key File**, and then click the ellipsis (**…**) button.</span></span>  
  
7. <span data-ttu-id="4a391-124">アセンブリ キー ファイル ダイアログ ボックスを参照\<*ドライブ*\>: \Program Files\\Microsoft BizTalk\<バージョン\>HL7\SDK\End ツー エンド チュートリアルについては、アクセラレータ選択**key.snk**、 をクリックし、**オープン**します。</span><span class="sxs-lookup"><span data-stu-id="4a391-124">In the Assembly Key File dialog box, browse to \<*drive*\>:\Program Files\\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\End-to-End Tutorial, select **key.snk**, and then click **Open**.</span></span>  
  
8. <span data-ttu-id="4a391-125">BTAHL7V2XCommon プロジェクトのプロパティ ページで、次のようにクリックします。 **OK** 、変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="4a391-125">On the BTAHL7V2XCommon Project Property page, click **OK** to save your changes.</span></span>  
  
9. <span data-ttu-id="4a391-126">[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]の**ソリューション エクスプ ローラー**、右クリック**BTAHL7V2XCommon プロジェクト**、順にクリックします**デプロイ**します。</span><span class="sxs-lookup"><span data-stu-id="4a391-126">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], in **Solution Explorer**, right-click **BTAHL7V2XCommon Project**, and then click **Deploy**.</span></span> <span data-ttu-id="4a391-127">成功メッセージが出力ウィンドウに表示を確認します。</span><span class="sxs-lookup"><span data-stu-id="4a391-127">Ensure a success message appears in the output window.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="4a391-128">デプロイの適切なメッセージが表示されない場合は、使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]デプロイのトラブルシューティングを行う。</span><span class="sxs-lookup"><span data-stu-id="4a391-128">If the correct deploy message does not appear, use [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] to troubleshoot your deployment.</span></span>  
  
   <span data-ttu-id="4a391-129">続行する[手順 2。V2.3.1 の一般的なスキーマを作成する](../../adapters-and-accelerators/accelerator-hl7/step-2-create-common-schemas-for-v2-3-1.md)します。</span><span class="sxs-lookup"><span data-stu-id="4a391-129">Proceed to [Step 2: Create Common Schemas for V2.3.1](../../adapters-and-accelerators/accelerator-hl7/step-2-create-common-schemas-for-v2-3-1.md).</span></span>