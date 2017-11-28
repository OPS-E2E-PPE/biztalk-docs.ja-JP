---
title: "ListTypes コマンド |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 94febe8a-4c1e-4581-a6d1-ef579633e745
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: afe2519fc5507ae0975d050a998faec78f2940a3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="listtypes-command"></a><span data-ttu-id="2dda3-102">ListTypes コマンド</span><span class="sxs-lookup"><span data-stu-id="2dda3-102">ListTypes Command</span></span>
<span data-ttu-id="2dda3-103">追加できるアイテムの種類のすべてを一覧表示[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を使用して、 **AddResource**コマンド。</span><span class="sxs-lookup"><span data-stu-id="2dda3-103">Lists all of the artifact types that you can add to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] by using the **AddResource** command.</span></span> <span data-ttu-id="2dda3-104">詳細については、 **AddResource**コマンドを参照してください[AddResource コマンド](../core/addresource-command.md)です。</span><span class="sxs-lookup"><span data-stu-id="2dda3-104">For more information about the **AddResource** command, see [AddResource Command](../core/addresource-command.md).</span></span>  
  
 <span data-ttu-id="2dda3-105">サポートされているアイテムの種類の完全修飾名は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2dda3-105">The fully qualified names of the supported artifact types are as follows:</span></span>  
  
-   <span data-ttu-id="2dda3-106">.NET アセンブリ: System.BizTalk:Assembly</span><span class="sxs-lookup"><span data-stu-id="2dda3-106">.NET assembly: System.BizTalk:Assembly</span></span>  
  
-   <span data-ttu-id="2dda3-107">BAM 定義: System.BizTalk:Bam</span><span class="sxs-lookup"><span data-stu-id="2dda3-107">BAM definition: System.BizTalk:Bam</span></span>  
  
-   <span data-ttu-id="2dda3-108">BizTalk アセンブリ: System.BizTalk:BizTalkAssembly</span><span class="sxs-lookup"><span data-stu-id="2dda3-108">BizTalk assembly: System.BizTalk:BizTalkAssembly</span></span>  
  
-   <span data-ttu-id="2dda3-109">BizTalk バインド ファイル: System.BizTalk:BizTalkBinding</span><span class="sxs-lookup"><span data-stu-id="2dda3-109">BizTalk binding file: System.BizTalk:BizTalkBinding</span></span>  
  
-   <span data-ttu-id="2dda3-110">セキュリティ証明書: System.BizTalk:Certificate</span><span class="sxs-lookup"><span data-stu-id="2dda3-110">Security certificate: System.BizTalk:Certificate</span></span>  
  
-   <span data-ttu-id="2dda3-111">COM コンポーネント: System.BizTalk:Com</span><span class="sxs-lookup"><span data-stu-id="2dda3-111">COM component: System.BizTalk:Com</span></span>  
  
-   <span data-ttu-id="2dda3-112">アドホック ファイル: System.BizTalk:File</span><span class="sxs-lookup"><span data-stu-id="2dda3-112">Ad hoc file: System.BizTalk:File</span></span>  
  
-   <span data-ttu-id="2dda3-113">処理後のスクリプト: System.BizTalk:PostProcessingScript</span><span class="sxs-lookup"><span data-stu-id="2dda3-113">Postprocessing script: System.BizTalk:PostProcessingScript</span></span>  
  
-   <span data-ttu-id="2dda3-114">スクリプトを前処理: System.BizTalk:PreProcessingScript</span><span class="sxs-lookup"><span data-stu-id="2dda3-114">Preprocessing script: System.BizTalk:PreProcessingScript</span></span>  
  
-   <span data-ttu-id="2dda3-115">ポリシーまたはルール: System.BizTalk:Rules</span><span class="sxs-lookup"><span data-stu-id="2dda3-115">Policy or rule: System.BizTalk:Rules</span></span>  
  
-   <span data-ttu-id="2dda3-116">仮想ディレクトリ: System.BizTalk:WebDirectory</span><span class="sxs-lookup"><span data-stu-id="2dda3-116">Virtual directory: System.BizTalk:WebDirectory</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2dda3-117">名前空間の競合を防ぐため、単独の型名 (Assembly など) ではなく、完全な型名 (System.BizTalk:Assembly) を使用するようにしてください。</span><span class="sxs-lookup"><span data-stu-id="2dda3-117">To avoid namespace conflicts, you should always use the full type name (such as System.BizTalk:Assembly) rather than the type name alone (such as Assembly).</span></span>  
  
## <a name="usage"></a><span data-ttu-id="2dda3-118">使用方法</span><span class="sxs-lookup"><span data-stu-id="2dda3-118">Usage</span></span>  
 <span data-ttu-id="2dda3-119">**BTSTask ListTypes**</span><span class="sxs-lookup"><span data-stu-id="2dda3-119">**BTSTask ListTypes**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2dda3-120">参照</span><span class="sxs-lookup"><span data-stu-id="2dda3-120">See Also</span></span>  
 [<span data-ttu-id="2dda3-121">BTSTask コマンド ライン リファレンス</span><span class="sxs-lookup"><span data-stu-id="2dda3-121">BTSTask Command-Line Reference</span></span>](../core/btstask-command-line-reference.md)