---
title: 手順 2:V2.3.1 の一般的なスキーマを作成する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- end-to-end tutorial, common schemas
- common schemas
ms.assetid: db1a2206-559f-475a-803d-55522cce007e
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 869eadf2c52b9def861aa93d451ca8c53bfcb26e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65289009"
---
# <a name="step-2-create-common-schemas-for-v231"></a><span data-ttu-id="470d1-102">手順 2:V2.3.1 の一般的なスキーマを作成します。</span><span class="sxs-lookup"><span data-stu-id="470d1-102">Step 2: Create Common Schemas for V2.3.1</span></span>
<span data-ttu-id="470d1-103">V2.3.1 スキーマは、頻繁に参照されるスキーマは、メッセージ インスタンスの検証に使用します。</span><span class="sxs-lookup"><span data-stu-id="470d1-103">The V2.3.1 schemas are commonly referenced schemas, which you use to validate the message instance.</span></span>  
  
### <a name="to-create-a-common-schema-for-v231"></a><span data-ttu-id="470d1-104">V2.3.1 の一般的なスキーマを作成するには</span><span class="sxs-lookup"><span data-stu-id="470d1-104">To create a common schema for V2.3.1</span></span>  
  
1. <span data-ttu-id="470d1-105">[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], の **ファイル** メニューをポイント **新規**, 、クリックして **プロジェクト**します。</span><span class="sxs-lookup"><span data-stu-id="470d1-105">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], on the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
2. <span data-ttu-id="470d1-106">新しいプロジェクト] ダイアログ ボックスで、**プロジェクトの種類**セクションで、展開**BizTalk プロジェクト**、し、[ **BTAHL7Projects**します。</span><span class="sxs-lookup"><span data-stu-id="470d1-106">In the New Project dialog box, in the **Project Types** section, expand **BizTalk Projects**, and then select **BTAHL7Projects**.</span></span>  
  
3. <span data-ttu-id="470d1-107">[テンプレート] セクションで**BTAHL7V231Common プロジェクト**します。</span><span class="sxs-lookup"><span data-stu-id="470d1-107">In the Templates section, select **BTAHL7V231Common Project**.</span></span>  
  
4. <span data-ttu-id="470d1-108">**名前**ボックスに、入力**BTAHL7V231Common プロジェクト**プロジェクト名として。</span><span class="sxs-lookup"><span data-stu-id="470d1-108">In the **Name** box, enter **BTAHL7V231Common Project** as the project name.</span></span>  
  
5. <span data-ttu-id="470d1-109">**ソリューション**ボックスで、**ソリューションに追加**します。</span><span class="sxs-lookup"><span data-stu-id="470d1-109">In the **Solution** box, select **Add to Solution**.</span></span>  
  
6. <span data-ttu-id="470d1-110">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="470d1-110">Click **OK**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="470d1-111">ソリューション エクスプ ローラーでプロジェクトの 3 つのスキーマ (datatypes_231.xsd、segments_231.xsd、および tablevalues_231.xsd) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="470d1-111">In Solution Explorer, three schemas (datatypes_231.xsd, segments_231.xsd, and tablevalues_231.xsd) are included in the project.</span></span>  
  
7. <span data-ttu-id="470d1-112">ソリューション エクスプ ローラーで右クリックして**BTAHL7V231Common プロジェクト**、 をクリックし、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="470d1-112">In Solution Explorer, right-click **BTAHL7V231Common Project**, and then click **Properties**.</span></span>  
  
8. <span data-ttu-id="470d1-113">BTAHL7V231Common プロパティ ページで、次のようにクリックします。**署名**します。</span><span class="sxs-lookup"><span data-stu-id="470d1-113">On the BTAHL7V231Common Property Page, click **Signing**.</span></span>  
  
9. <span data-ttu-id="470d1-114">選択、**アセンブリに署名**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="470d1-114">Select the **Sign the assembly** check box.</span></span>  
  
10. <span data-ttu-id="470d1-115">**厳密な名前キー ファイルを選択して**を選択します**\<を参照しています.\>** .</span><span class="sxs-lookup"><span data-stu-id="470d1-115">In **Choose a strong name key file**, select **\<Browse…\>** .</span></span>  
  
11. <span data-ttu-id="470d1-116">参照\<ドライブ\>: \Batching チュートリアルでは、選択**key.snk**、 をクリックし、**オープン**します。</span><span class="sxs-lookup"><span data-stu-id="470d1-116">Browse to \<drive\>:\Batching Tutorial, select **key.snk**, and then click **Open**.</span></span>  
  
12. <span data-ttu-id="470d1-117">ソリューション エクスプ ローラーで右クリックして**BTAHL7V231Common プロジェクト**、 をクリックし、**デプロイ**します。</span><span class="sxs-lookup"><span data-stu-id="470d1-117">In Solution Explorer, right-click **BTAHL7V231Common Project**, and then click **Deploy**.</span></span> <span data-ttu-id="470d1-118">成功メッセージが出力ウィンドウに表示を確認します。</span><span class="sxs-lookup"><span data-stu-id="470d1-118">Ensure a success message appears in the output window.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="470d1-119">適切なメッセージが表示されない場合は、使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]スキーマのトラブルシューティングを行う。</span><span class="sxs-lookup"><span data-stu-id="470d1-119">If the correct message does not appear, use [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] to troubleshoot your schemas.</span></span>  
  
    <span data-ttu-id="470d1-120">続行する[手順 3。トリガー イベント (メッセージ) スキーマを追加](../../adapters-and-accelerators/accelerator-hl7/step-3-add-a-trigger-event-message-schema.md)します。</span><span class="sxs-lookup"><span data-stu-id="470d1-120">Proceed to [Step 3: Add a Trigger Event (Message) Schema](../../adapters-and-accelerators/accelerator-hl7/step-3-add-a-trigger-event-message-schema.md).</span></span>