---
title: '手順 2: V2.3.1 用の共通のスキーマの作成 |Microsoft ドキュメント'
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
ms.openlocfilehash: e5f8ed36b4a1ae8553e8df488e8fd5a606c0eabd
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25960992"
---
# <a name="step-2-create-common-schemas-for-v231"></a><span data-ttu-id="2c71f-102">手順 2: V2.3.1 の一般的なスキーマを作成します。</span><span class="sxs-lookup"><span data-stu-id="2c71f-102">Step 2: Create Common Schemas for V2.3.1</span></span>
<span data-ttu-id="2c71f-103">V2.3.1 スキーマは、頻繁に参照されるスキーマは、メッセージ インスタンスの検証に使用します。</span><span class="sxs-lookup"><span data-stu-id="2c71f-103">The V2.3.1 schemas are commonly referenced schemas, which you use to validate the message instance.</span></span>  
  
### <a name="to-create-a-common-schema-for-v231"></a><span data-ttu-id="2c71f-104">V2.3.1 の共通のスキーマを作成するには</span><span class="sxs-lookup"><span data-stu-id="2c71f-104">To create a common schema for V2.3.1</span></span>  
  
1.  <span data-ttu-id="2c71f-105">[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]の**ファイル** メニューのをポイント**新規**、クリックして**プロジェクト**です。</span><span class="sxs-lookup"><span data-stu-id="2c71f-105">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], on the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="2c71f-106">新しいプロジェクト] ダイアログ ボックスで、**プロジェクトの種類**セクションで、展開**BizTalk プロジェクト**、し、[ **BTAHL7Projects**です。</span><span class="sxs-lookup"><span data-stu-id="2c71f-106">In the New Project dialog box, in the **Project Types** section, expand **BizTalk Projects**, and then select **BTAHL7Projects**.</span></span>  
  
3.  <span data-ttu-id="2c71f-107">テンプレート セクションで、 **BTAHL7V231Common プロジェクト**です。</span><span class="sxs-lookup"><span data-stu-id="2c71f-107">In the Templates section, select **BTAHL7V231Common Project**.</span></span>  
  
4.  <span data-ttu-id="2c71f-108">**名前**ボックスに、入力**BTAHL7V231Common プロジェクト**プロジェクト名として。</span><span class="sxs-lookup"><span data-stu-id="2c71f-108">In the **Name** box, enter **BTAHL7V231Common Project** as the project name.</span></span>  
  
5.  <span data-ttu-id="2c71f-109">**ソリューション**ボックスで、**ソリューションに追加**です。</span><span class="sxs-lookup"><span data-stu-id="2c71f-109">In the **Solution** box, select **Add to Solution**.</span></span>  
  
6.  <span data-ttu-id="2c71f-110">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2c71f-110">Click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2c71f-111">ソリューション エクスプ ローラーで、3 つのスキーマ (datatypes_231.xsd、segments_231.xsd、および tablevalues_231.xsd) は、プロジェクトに含まれます。</span><span class="sxs-lookup"><span data-stu-id="2c71f-111">In Solution Explorer, three schemas (datatypes_231.xsd, segments_231.xsd, and tablevalues_231.xsd) are included in the project.</span></span>  
  
7.  <span data-ttu-id="2c71f-112">ソリューション エクスプ ローラーで右クリック**BTAHL7V231Common プロジェクト**、クリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="2c71f-112">In Solution Explorer, right-click **BTAHL7V231Common Project**, and then click **Properties**.</span></span>  
  
8.  <span data-ttu-id="2c71f-113">BTAHL7V231Common プロパティ ページで、をクリックして**署名**です。</span><span class="sxs-lookup"><span data-stu-id="2c71f-113">On the BTAHL7V231Common Property Page, click **Signing**.</span></span>  
  
9. <span data-ttu-id="2c71f-114">選択、**アセンブリに署名**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="2c71f-114">Select the **Sign the assembly** check box.</span></span>  
  
10. <span data-ttu-id="2c71f-115">**厳密な名前キー ファイルを選択して** **\<を参照しています.\>** .</span><span class="sxs-lookup"><span data-stu-id="2c71f-115">In **Choose a strong name key file**, select **\<Browse…\>** .</span></span>  
  
11. <span data-ttu-id="2c71f-116">参照\<ドライブ\>: \Batching チュートリアルでは、選択**key.snk**、クリックして**開く**です。</span><span class="sxs-lookup"><span data-stu-id="2c71f-116">Browse to \<drive\>:\Batching Tutorial, select **key.snk**, and then click **Open**.</span></span>  
  
12. <span data-ttu-id="2c71f-117">ソリューション エクスプ ローラーで右クリック**BTAHL7V231Common プロジェクト**、クリックして**展開**です。</span><span class="sxs-lookup"><span data-stu-id="2c71f-117">In Solution Explorer, right-click **BTAHL7V231Common Project**, and then click **Deploy**.</span></span> <span data-ttu-id="2c71f-118">成功メッセージが出力ウィンドウに表示を確認します。</span><span class="sxs-lookup"><span data-stu-id="2c71f-118">Ensure a success message appears in the output window.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2c71f-119">使用して、適切なメッセージが表示されない場合[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]スキーマをトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="2c71f-119">If the correct message does not appear, use [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] to troubleshoot your schemas.</span></span>  
  
 <span data-ttu-id="2c71f-120">進みます[手順 3: トリガー イベント (メッセージ) スキーマを追加](../../adapters-and-accelerators/accelerator-hl7/step-3-add-a-trigger-event-message-schema.md)です。</span><span class="sxs-lookup"><span data-stu-id="2c71f-120">Proceed to [Step 3: Add a Trigger Event (Message) Schema](../../adapters-and-accelerators/accelerator-hl7/step-3-add-a-trigger-event-message-schema.md).</span></span>