---
title: '手順 2: V2.4 用の共通のスキーマの作成 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- interrogative tutorial, common schemas
ms.assetid: 333ae85a-a307-4ab1-97f4-4d7b986e91de
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 60b199bcd350a3341640baa05b875347c4f04bb5
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="step-2-create-common-schemas-for-v24"></a><span data-ttu-id="2184d-102">手順 2: V2.4 の一般的なスキーマを作成します。</span><span class="sxs-lookup"><span data-stu-id="2184d-102">Step 2: Create Common Schemas for V2.4</span></span>
<span data-ttu-id="2184d-103">V2.4 スキーマは、頻繁に参照されるスキーマは、クエリと応答メッセージ インスタンスの検証に使用します。</span><span class="sxs-lookup"><span data-stu-id="2184d-103">The V2.4 schemas are commonly referenced schemas, which you use to validate the query and response message instances.</span></span>  
  
### <a name="to-create-the-common-schemas-for-v24"></a><span data-ttu-id="2184d-104">V2.4 の一般的なスキーマを作成するには</span><span class="sxs-lookup"><span data-stu-id="2184d-104">To create the common schemas for V2.4</span></span>  
  
1.  <span data-ttu-id="2184d-105">[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]の**ファイル** メニューのをポイント**新規**、クリックして**プロジェクト**です。</span><span class="sxs-lookup"><span data-stu-id="2184d-105">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], on the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="2184d-106">新しいプロジェクト] ダイアログ ボックスで、**プロジェクトの種類**一覧で、展開**BizTalk プロジェクト**、し、[ **BTAHL7Projects**です。</span><span class="sxs-lookup"><span data-stu-id="2184d-106">In the New Project dialog box, in the **Project Types** list, expand **BizTalk Projects**, and then select **BTAHL7Projects**.</span></span>  
  
3.  <span data-ttu-id="2184d-107">**テンプレート**一覧で、 **BTAHL7V24Common プロジェクト**です。</span><span class="sxs-lookup"><span data-stu-id="2184d-107">In the **Templates** list, select **BTAHL7V24Common Project**.</span></span>  
  
4.  <span data-ttu-id="2184d-108">**名前**フィールドに「 **Interrogative_24Schemas**です。</span><span class="sxs-lookup"><span data-stu-id="2184d-108">In the **Name** field, type **Interrogative_24Schemas**.</span></span>  
  
5.  <span data-ttu-id="2184d-109">ソリューション フィールドで、選択**ソリューションに追加**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="2184d-109">In the Solution field, select **Add to Solution**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="2184d-110">ソリューション エクスプ ローラーで、プロジェクトに 3 つのスキーマ (datatypes_24.xsd、segments_24.xsd、および tablevalues_24.xsd) が含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2184d-110">In Solution Explorer, notice that three schemas (datatypes_24.xsd, segments_24.xsd, and tablevalues_24.xsd) are included in the project.</span></span>  
  
6.  <span data-ttu-id="2184d-111">ソリューション エクスプ ローラーで右クリック**Interrogative_24Schemas**プロジェクトをクリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="2184d-111">In Solution Explorer, right-click **Interrogative_24Schemas** project,and then click **Properties**.</span></span>  
  
7.  <span data-ttu-id="2184d-112">Interrogative_24Schemas プロパティ ページ] ダイアログ ボックスで、[**アセンブリ**です。</span><span class="sxs-lookup"><span data-stu-id="2184d-112">In the Interrogative_24Schemas Property Pages dialog box, click **Assembly**.</span></span>  
  
8.  <span data-ttu-id="2184d-113">右側のペインでスクロールして、**厳密な名前**セクションで、フィールドの右側をクリックして**アセンブリ キー ファイル**、省略記号 (...) ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="2184d-113">In the right pane, scroll down to the **Strong name** section, click the field to the right of **Assembly Key File**, and then click the ellipsis (…) button.</span></span>  
  
9. <span data-ttu-id="2184d-114">**アセンブリ キー ファイル** ダイアログ ボックスを参照\<*ドライブ*\>: \Program Files\Microsoft BizTalk\<バージョン\>HL7\SDK\ のアクセラレータInterrogative チュートリアルをクリックして**key.snk**、順にクリック**開く**です。</span><span class="sxs-lookup"><span data-stu-id="2184d-114">In the **Assembly Key File** dialog box, browse to \<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\Interrogative Tutorial, click **key.snk**, and then click **Open**.</span></span>  
  
10. <span data-ttu-id="2184d-115">Interrogative_24Schemas プロパティ ページ] ダイアログ ボックスで、[ **OK**して変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="2184d-115">In the Interrogative_24Schemas Property Pages dialog box, click **OK** to save your changes.</span></span>  
  
11. <span data-ttu-id="2184d-116">ソリューション エクスプ ローラーで右クリック**Interrogative_24Schemas**プロジェクトをクリックして**展開**です。</span><span class="sxs-lookup"><span data-stu-id="2184d-116">In Solution Explorer, right-click **Interrogative_24Schemas** project, and then click **Deploy**.</span></span> <span data-ttu-id="2184d-117">をクリックして**OK**ソリューションに変更を保存するように求めるダイアログ ボックスにします。</span><span class="sxs-lookup"><span data-stu-id="2184d-117">Click **OK** to the dialog box asking you to save changes to the solution.</span></span> <span data-ttu-id="2184d-118">成功メッセージが出力ウィンドウに表示を確認します。</span><span class="sxs-lookup"><span data-stu-id="2184d-118">Ensure a success message appears in the output window.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2184d-119">使用して、適切なメッセージが表示されない場合[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]スキーマをトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="2184d-119">If the correct message does not appear, use [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] to troubleshoot your schemas.</span></span>  
  
 <span data-ttu-id="2184d-120">進みます[手順 3: を作成し、トリガー イベント (メッセージ) プロジェクトを配置](../../adapters-and-accelerators/accelerator-hl7/step-3-create-and-deploy-a-trigger-event-message-project-hl7-main.md)です。</span><span class="sxs-lookup"><span data-stu-id="2184d-120">Proceed to [Step 3: Create and Deploy a Trigger Event (Message) Project](../../adapters-and-accelerators/accelerator-hl7/step-3-create-and-deploy-a-trigger-event-message-project-hl7-main.md).</span></span>