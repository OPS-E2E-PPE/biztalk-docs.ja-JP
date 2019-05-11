---
title: 手順 2:V2.4 の一般的なスキーマを作成する |Microsoft Docs
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
ms.openlocfilehash: 5149ba2e39f36b85f03af8f3bfb81656a5647b64
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65288655"
---
# <a name="step-2-create-common-schemas-for-v24"></a><span data-ttu-id="17bc3-102">手順 2:V2.4 の一般的なスキーマを作成します。</span><span class="sxs-lookup"><span data-stu-id="17bc3-102">Step 2: Create Common Schemas for V2.4</span></span>
<span data-ttu-id="17bc3-103">V2.4 スキーマは、頻繁に参照されるスキーマは、クエリと応答メッセージ インスタンスの検証に使用します。</span><span class="sxs-lookup"><span data-stu-id="17bc3-103">The V2.4 schemas are commonly referenced schemas, which you use to validate the query and response message instances.</span></span>  
  
### <a name="to-create-the-common-schemas-for-v24"></a><span data-ttu-id="17bc3-104">V2.4 の一般的なスキーマを作成するには</span><span class="sxs-lookup"><span data-stu-id="17bc3-104">To create the common schemas for V2.4</span></span>  
  
1. <span data-ttu-id="17bc3-105">[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], の **ファイル** メニューをポイント **新規**, 、クリックして **プロジェクト**します。</span><span class="sxs-lookup"><span data-stu-id="17bc3-105">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], on the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
2. <span data-ttu-id="17bc3-106">新しいプロジェクト] ダイアログ ボックスで、**プロジェクトの種類**一覧で、展開**BizTalk プロジェクト**、し、[ **BTAHL7Projects**します。</span><span class="sxs-lookup"><span data-stu-id="17bc3-106">In the New Project dialog box, in the **Project Types** list, expand **BizTalk Projects**, and then select **BTAHL7Projects**.</span></span>  
  
3. <span data-ttu-id="17bc3-107">**テンプレート**一覧で、 **BTAHL7V24Common プロジェクト**します。</span><span class="sxs-lookup"><span data-stu-id="17bc3-107">In the **Templates** list, select **BTAHL7V24Common Project**.</span></span>  
  
4. <span data-ttu-id="17bc3-108">**名前**フィールドに「 **Interrogative_24Schemas**します。</span><span class="sxs-lookup"><span data-stu-id="17bc3-108">In the **Name** field, type **Interrogative_24Schemas**.</span></span>  
  
5. <span data-ttu-id="17bc3-109">ソリューションのフィールドで、選択**ソリューションに追加**、順にクリックします**OK**。</span><span class="sxs-lookup"><span data-stu-id="17bc3-109">In the Solution field, select **Add to Solution**, and then click **OK**.</span></span>  
  
    <span data-ttu-id="17bc3-110">ソリューション エクスプ ローラーでは、(datatypes_24.xsd、segments_24.xsd、および tablevalues_24.xsd) の 3 つのスキーマをプロジェクトに含まれることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="17bc3-110">In Solution Explorer, notice that three schemas (datatypes_24.xsd, segments_24.xsd, and tablevalues_24.xsd) are included in the project.</span></span>  
  
6. <span data-ttu-id="17bc3-111">ソリューション エクスプ ローラーで右クリックして**Interrogative_24Schemas**プロジェクトをクリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="17bc3-111">In Solution Explorer, right-click **Interrogative_24Schemas** project,and then click **Properties**.</span></span>  
  
7. <span data-ttu-id="17bc3-112">Interrogative_24Schemas プロパティ ページ] ダイアログ ボックスで、[**アセンブリ**します。</span><span class="sxs-lookup"><span data-stu-id="17bc3-112">In the Interrogative_24Schemas Property Pages dialog box, click **Assembly**.</span></span>  
  
8. <span data-ttu-id="17bc3-113">右側のペインでスクロールして、**厳密な名前**セクションで、フィールドの右側をクリックして**アセンブリ キー ファイル**、省略記号 (...) ボタンを順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="17bc3-113">In the right pane, scroll down to the **Strong name** section, click the field to the right of **Assembly Key File**, and then click the ellipsis (…) button.</span></span>  
  
9. <span data-ttu-id="17bc3-114">**アセンブリ キー ファイル** ダイアログ ボックスを参照\<*ドライブ*\>: \Program Files\Microsoft BizTalk\<バージョン\>HL7\SDK\ のアクセラレータInterrogative チュートリアル, をクリックして**key.snk**、 をクリックし、**オープン**します。</span><span class="sxs-lookup"><span data-stu-id="17bc3-114">In the **Assembly Key File** dialog box, browse to \<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\Interrogative Tutorial, click **key.snk**, and then click **Open**.</span></span>  
  
10. <span data-ttu-id="17bc3-115">Interrogative_24Schemas プロパティ ページ] ダイアログ ボックスで、[ **OK**変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="17bc3-115">In the Interrogative_24Schemas Property Pages dialog box, click **OK** to save your changes.</span></span>  
  
11. <span data-ttu-id="17bc3-116">ソリューション エクスプ ローラーで右クリックして**Interrogative_24Schemas**プロジェクトをクリックして**デプロイ**します。</span><span class="sxs-lookup"><span data-stu-id="17bc3-116">In Solution Explorer, right-click **Interrogative_24Schemas** project, and then click **Deploy**.</span></span> <span data-ttu-id="17bc3-117">をクリックして**OK**をソリューションに変更を保存することを確認するダイアログ ボックスにします。</span><span class="sxs-lookup"><span data-stu-id="17bc3-117">Click **OK** to the dialog box asking you to save changes to the solution.</span></span> <span data-ttu-id="17bc3-118">成功メッセージが出力ウィンドウに表示を確認します。</span><span class="sxs-lookup"><span data-stu-id="17bc3-118">Ensure a success message appears in the output window.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="17bc3-119">適切なメッセージが表示されない場合は、使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]スキーマのトラブルシューティングを行う。</span><span class="sxs-lookup"><span data-stu-id="17bc3-119">If the correct message does not appear, use [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] to troubleshoot your schemas.</span></span>  
  
    <span data-ttu-id="17bc3-120">続行する[手順 3。作成し、トリガー イベント (メッセージ) プロジェクトを配置](../../adapters-and-accelerators/accelerator-hl7/step-3-create-and-deploy-a-trigger-event-message-project-hl7-main.md)します。</span><span class="sxs-lookup"><span data-stu-id="17bc3-120">Proceed to [Step 3: Create and Deploy a Trigger Event (Message) Project](../../adapters-and-accelerators/accelerator-hl7/step-3-create-and-deploy-a-trigger-event-message-project-hl7-main.md).</span></span>