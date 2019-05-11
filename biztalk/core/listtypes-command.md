---
title: ListTypes コマンド |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 94febe8a-4c1e-4581-a6d1-ef579633e745
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fda39d682bfb4649fc22afd892dd13849bfd1b09
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380725"
---
# <a name="listtypes-command"></a><span data-ttu-id="55abb-102">ListTypes コマンド</span><span class="sxs-lookup"><span data-stu-id="55abb-102">ListTypes Command</span></span>
<span data-ttu-id="55abb-103">追加できる成果物の種類のすべてを一覧表示[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を使用して、 **AddResource**コマンド。</span><span class="sxs-lookup"><span data-stu-id="55abb-103">Lists all of the artifact types that you can add to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] by using the **AddResource** command.</span></span> <span data-ttu-id="55abb-104">詳細については、 **AddResource**コマンドを参照してください[AddResource コマンド](../core/addresource-command.md)します。</span><span class="sxs-lookup"><span data-stu-id="55abb-104">For more information about the **AddResource** command, see [AddResource Command](../core/addresource-command.md).</span></span>  
  
 <span data-ttu-id="55abb-105">サポートされている成果物の種類の完全修飾名は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="55abb-105">The fully qualified names of the supported artifact types are as follows:</span></span>  
  
-   <span data-ttu-id="55abb-106">.NET アセンブリ:System.BizTalk:Assembly</span><span class="sxs-lookup"><span data-stu-id="55abb-106">.NET assembly: System.BizTalk:Assembly</span></span>  
  
-   <span data-ttu-id="55abb-107">BAM 定義:System.BizTalk:Bam</span><span class="sxs-lookup"><span data-stu-id="55abb-107">BAM definition: System.BizTalk:Bam</span></span>  
  
-   <span data-ttu-id="55abb-108">BizTalk アセンブリ:System.BizTalk:BizTalkAssembly</span><span class="sxs-lookup"><span data-stu-id="55abb-108">BizTalk assembly: System.BizTalk:BizTalkAssembly</span></span>  
  
-   <span data-ttu-id="55abb-109">BizTalk バインド ファイル:System.BizTalk:BizTalkBinding</span><span class="sxs-lookup"><span data-stu-id="55abb-109">BizTalk binding file: System.BizTalk:BizTalkBinding</span></span>  
  
-   <span data-ttu-id="55abb-110">セキュリティ証明書:System.BizTalk:Certificate</span><span class="sxs-lookup"><span data-stu-id="55abb-110">Security certificate: System.BizTalk:Certificate</span></span>  
  
-   <span data-ttu-id="55abb-111">COM コンポーネント:System.BizTalk:Com</span><span class="sxs-lookup"><span data-stu-id="55abb-111">COM component: System.BizTalk:Com</span></span>  
  
-   <span data-ttu-id="55abb-112">アドホック ファイル:System.BizTalk:File</span><span class="sxs-lookup"><span data-stu-id="55abb-112">Ad hoc file: System.BizTalk:File</span></span>  
  
-   <span data-ttu-id="55abb-113">処理後のスクリプト:System.BizTalk:PostProcessingScript</span><span class="sxs-lookup"><span data-stu-id="55abb-113">Postprocessing script: System.BizTalk:PostProcessingScript</span></span>  
  
-   <span data-ttu-id="55abb-114">処理前のスクリプト:System.BizTalk:PreProcessingScript</span><span class="sxs-lookup"><span data-stu-id="55abb-114">Preprocessing script: System.BizTalk:PreProcessingScript</span></span>  
  
-   <span data-ttu-id="55abb-115">ポリシーまたはルール:System.BizTalk:Rules</span><span class="sxs-lookup"><span data-stu-id="55abb-115">Policy or rule: System.BizTalk:Rules</span></span>  
  
-   <span data-ttu-id="55abb-116">仮想ディレクトリ:System.BizTalk:WebDirectory</span><span class="sxs-lookup"><span data-stu-id="55abb-116">Virtual directory: System.BizTalk:WebDirectory</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="55abb-117">名前空間の競合を避けるためには、型名のみ (アセンブリ) などではなく、完全な型名 (System.BizTalk:Assembly) などを常に使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="55abb-117">To avoid namespace conflicts, you should always use the full type name (such as System.BizTalk:Assembly) rather than the type name alone (such as Assembly).</span></span>  
  
## <a name="usage"></a><span data-ttu-id="55abb-118">使用方法</span><span class="sxs-lookup"><span data-stu-id="55abb-118">Usage</span></span>  
 <span data-ttu-id="55abb-119">**BTSTask ListTypes**</span><span class="sxs-lookup"><span data-stu-id="55abb-119">**BTSTask ListTypes**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55abb-120">参照</span><span class="sxs-lookup"><span data-stu-id="55abb-120">See Also</span></span>  
 [<span data-ttu-id="55abb-121">BTSTask コマンド ライン リファレンス</span><span class="sxs-lookup"><span data-stu-id="55abb-121">BTSTask Command-Line Reference</span></span>](../core/btstask-command-line-reference.md)