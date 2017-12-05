---
title: "レッスン 2: プロジェクト参照の追加 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- references [projects]
- projects, adding references
ms.assetid: ddc2bf49-cddd-4edb-8043-870897879655
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b00fc7d49024cec6f9c300444646da82069e16cc
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="lesson-2-adding-project-references"></a><span data-ttu-id="1b1e1-102">レッスン 2: プロジェクト参照の追加</span><span class="sxs-lookup"><span data-stu-id="1b1e1-102">Lesson 2: Adding Project References</span></span>
<span data-ttu-id="1b1e1-103">プロジェクト参照を追加する、パイプライン Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.dll ファイル内にある既定の実行時のスキーマにアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="1b1e1-103">You add project references so your pipelines can access the default runtime schemas located in the Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.dll file.</span></span> <span data-ttu-id="1b1e1-104">このアセンブリ ファイルには、メッセージ型の解決に必要な昇格させたプロパティを持つヘッダー スキーマが含まれています。</span><span class="sxs-lookup"><span data-stu-id="1b1e1-104">This assembly file contains the header schema with promoted properties required for message-type resolution.</span></span>  
  
 <span data-ttu-id="1b1e1-105">逆アセンブル コンポーネントを受信パイプラインに追加するときに、ヘッダー スキーマを後で参照します。</span><span class="sxs-lookup"><span data-stu-id="1b1e1-105">You reference the header schemas later when you add the disassembly component to the receive pipeline.</span></span>  
  
### <a name="to-add-a-reference-to-the-default-swift-runtimeschemas-assembly"></a><span data-ttu-id="1b1e1-106">既定の SWIFT RuntimeSchemas アセンブリへの参照を追加するには</span><span class="sxs-lookup"><span data-stu-id="1b1e1-106">To add a reference to the default SWIFT RuntimeSchemas assembly</span></span>  
  
1.  <span data-ttu-id="1b1e1-107">ソリューション エクスプ ローラーでいることを確認、 **SWIFTPipelines**プロジェクトを展開します。</span><span class="sxs-lookup"><span data-stu-id="1b1e1-107">In Solution Explorer, ensure that the **SWIFTPipelines** project is expanded.</span></span> <span data-ttu-id="1b1e1-108">右クリック**参照**、クリックして**参照の追加**です。</span><span class="sxs-lookup"><span data-stu-id="1b1e1-108">Right-click **References**, and then click **Add Reference**.</span></span>  
  
2.  <span data-ttu-id="1b1e1-109">[参照の追加] ダイアログ ボックス、**参照**タブです。</span><span class="sxs-lookup"><span data-stu-id="1b1e1-109">In the Add Reference dialog box, click the **Browse** tab.</span></span>  
  
3.  <span data-ttu-id="1b1e1-110">参照  **\<*ドライブ*\>: \Program Files\Microsoft BizTalk Accelerator for SWIFT\Assemblies * *。</span><span class="sxs-lookup"><span data-stu-id="1b1e1-110">Browse to **\<*drive*\>:\Program Files\Microsoft BizTalk Accelerator for SWIFT\Assemblies**.</span></span>  
  
4.  <span data-ttu-id="1b1e1-111">選択、 **Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.dll**ファイル。</span><span class="sxs-lookup"><span data-stu-id="1b1e1-111">Select the **Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.dll** file.</span></span>  
  
5.  <span data-ttu-id="1b1e1-112">をクリックして**追加**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="1b1e1-112">Click **Add**, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1b1e1-113">これで、選択した RuntimeSchemas アセンブリ (dll) は、コレクション SWIFTPipelines プロジェクト内の参照が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1b1e1-113">The RuntimeSchemas assembly (dll) that you selected now appears in the references collection in the SWIFTPipelines project.</span></span>  
  
#### <a name="to-add-a-reference-to-the-swiftpipelines-schemas-assembly"></a><span data-ttu-id="1b1e1-114">SWIFTPipelines スキーマ アセンブリへの参照を追加するには</span><span class="sxs-lookup"><span data-stu-id="1b1e1-114">To add a reference to the SWIFTPipelines schemas assembly</span></span>  
  
1.  <span data-ttu-id="1b1e1-115">ソリューション エクスプ ローラーで、、 **SWIFTPipelines**プロジェクトを右クリックして**参照**、順にクリック**参照の追加**です。</span><span class="sxs-lookup"><span data-stu-id="1b1e1-115">In Solution Explorer, under the **SWIFTPipelines** project, right-click **References**, and then click **Add Reference**.</span></span>  
  
2.  <span data-ttu-id="1b1e1-116">参照の追加 ダイアログ ボックスで、**プロジェクト** タブで、をクリックして、 **SWIFTSchemas**プロジェクトで、をクリックして**追加**、順にクリック**ok**です。</span><span class="sxs-lookup"><span data-stu-id="1b1e1-116">In the Add Reference dialog box, on the **Projects** tab, click the **SWIFTSchemas** project, click **Add**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="1b1e1-117">**ファイル** メニューのをクリックして**すべて保存**して変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="1b1e1-117">On the **File** menu, click **Save All** to save your changes.</span></span>  
  
 <span data-ttu-id="1b1e1-118">進みます[レッスン 3: カスタム受信パイプラインを追加する](../../adapters-and-accelerators/accelerator-swift/lesson-3-adding-a-custom-receive-pipeline.md)です。</span><span class="sxs-lookup"><span data-stu-id="1b1e1-118">Proceed to [Lesson 3: Adding a Custom Receive Pipeline](../../adapters-and-accelerators/accelerator-swift/lesson-3-adding-a-custom-receive-pipeline.md).</span></span>