---
title: その他のチュートリアルのプロジェクトを展開解除 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5fce837f-1853-4d5d-a680-8ae2a974c750
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1e5c4d7e20fc4d8e7c8bea724625dde770b4aca2
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26006419"
---
# <a name="undeploy-other-tutorial-projects"></a><span data-ttu-id="64937-102">その他のチュートリアルのプロジェクトを展開解除します。</span><span class="sxs-lookup"><span data-stu-id="64937-102">Undeploy Other Tutorial Projects</span></span>
<span data-ttu-id="64937-103">BizTalk Accelerator 用 HL7 に展開するときに ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) チュートリアル、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]チュートリアルのアセンブリ ファイル、構成データベース (BizTalk 管理データベースとも呼ばれます) と、グローバル アセンブリ キャッシュに格納します。</span><span class="sxs-lookup"><span data-stu-id="64937-103">When you deploy a BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) tutorials, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] stores the tutorial assembly files in the Configuration database (also known as the BizTalk Management database) and the global assembly cache.</span></span> <span data-ttu-id="64937-104">別に実行している場合[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]チュートリアル、および展開されたそのチュートリアルで作成したアセンブリときに、発生するエラー、バッチ処理のチュートリアルの 3 つの部分でアセンブリをテストします。</span><span class="sxs-lookup"><span data-stu-id="64937-104">If you have run another [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] tutorial, and deployed the assemblies that you created in that tutorial, you may encounter errors when you test your assemblies in the three parts of the Batching tutorial.</span></span> <span data-ttu-id="64937-105">1 つのメッセージ スキーマを一度に 1 つのみ展開できます可能性があります。</span><span class="sxs-lookup"><span data-stu-id="64937-105">This may occur because you can only deploy one message schema at one time.</span></span>  
  
 <span data-ttu-id="64937-106">前のチュートリアルに展開されたアセンブリを展開解除によってこれらのエラーを回避できます。</span><span class="sxs-lookup"><span data-stu-id="64937-106">You can avoid these errors by undeploying assemblies that you deployed in previous tutorials.</span></span> <span data-ttu-id="64937-107">必要な場合は、後でアセンブリを再配置することができます。</span><span class="sxs-lookup"><span data-stu-id="64937-107">You can re-deploy the assembly later if needed.</span></span>  
  
 <span data-ttu-id="64937-108">アセンブリを展開解除する前に、アセンブリ内のオーケストレーションを参加解除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="64937-108">Before undeploying an assembly, you need to unenlist orchestrations in the assembly.</span></span> <span data-ttu-id="64937-109">また、展開されたままにする他のアセンブリから、展開を解除するアセンブリへの参照を削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="64937-109">You also need to remove any reference to the assembly that you want to undeploy, from any other assembly that you want to keep deployed.</span></span> <span data-ttu-id="64937-110">代わりに別のチュートリアルを開始する前に、1 つのチュートリアルに関連付けられているすべての Dll の削除を開始します。</span><span class="sxs-lookup"><span data-stu-id="64937-110">An alternative is to delete all DLLs associated with one tutorial, before starting another tutorial.</span></span>  
  
### <a name="to-undeploy-an-assembly"></a><span data-ttu-id="64937-111">アセンブリを展開解除するには</span><span class="sxs-lookup"><span data-stu-id="64937-111">To undeploy an assembly</span></span>  
  
1.  <span data-ttu-id="64937-112">Visual Studio での BizTalk エクスプ ローラーでオーケストレーションをクリックし、をクリックして展開解除するアセンブリで使用するオーケストレーションを参加解除**参加解除**です。</span><span class="sxs-lookup"><span data-stu-id="64937-112">Unenlist orchestrations used in the assembly that you want to undeploy by clicking the orchestration in BizTalk Explorer of Visual Studio, and then clicking **Unenlist**.</span></span>  
  
2.  <span data-ttu-id="64937-113">展開されたままにする任意のアセンブリでは、展開解除するアセンブリへの参照を削除します。</span><span class="sxs-lookup"><span data-stu-id="64937-113">In any assembly that you want to keep deployed, remove references to assemblies that you want to undeploy.</span></span> <span data-ttu-id="64937-114">ソリューション エクスプ ローラー内の参照を右クリックし、をクリックして**削除**です。</span><span class="sxs-lookup"><span data-stu-id="64937-114">Right click the reference in Solution Explorer, and then click **Remove**.</span></span>  
  
3.  <span data-ttu-id="64937-115">BizTalk エクスプ ローラーを開きの展開を解除し、をクリックするアセンブリを右クリックして**Undeploy**です。</span><span class="sxs-lookup"><span data-stu-id="64937-115">Open BizTalk Explorer, right-click the assembly that you want to undeploy, and then click **Undeploy**.</span></span>  
  
 <span data-ttu-id="64937-116">アセンブリの展開解除の詳細については、「展開解除するアセンブリを使用して BizTalk エクスプ ローラー」BizTalk Server ヘルプを参照してください。</span><span class="sxs-lookup"><span data-stu-id="64937-116">For more information about undeploying an assembly, see "Undeploying an Assembly Using BizTalk Explorer" in BizTalk Server Help.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64937-117">参照</span><span class="sxs-lookup"><span data-stu-id="64937-117">See Also</span></span>  
 [<span data-ttu-id="64937-118">バッチ処理のチュートリアルを使用するための準備</span><span class="sxs-lookup"><span data-stu-id="64937-118">Preparing to Use the Batching Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/preparing-to-use-the-batching-tutorial.md)