---
title: 相互依存オーケストレーションを開発する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5464096e-66d8-48de-bc02-c754c5cfbada
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a6375add6d27e6ce0d3dff89bd2b172a2b693356
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992403"
---
# <a name="how-to-develop-interdependent-orchestrations"></a><span data-ttu-id="2f5cb-102">相互依存オーケストレーションを開発する方法</span><span class="sxs-lookup"><span data-stu-id="2f5cb-102">How to Develop Interdependent Orchestrations</span></span>
<span data-ttu-id="2f5cb-103">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] を使用して、相互に依存する Web サービスを持つオーケストレーションのセットを開発できます。</span><span class="sxs-lookup"><span data-stu-id="2f5cb-103">You can use [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] to develop a set of orchestrations that have interdependent Web services.</span></span> <span data-ttu-id="2f5cb-104">このシナリオは、複数のオーケストレーションが、それらを呼び出すオーケストレーションのデータ型とポートのどちらか一方または両方を参照する場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="2f5cb-104">This scenario arises when you have orchestrations that reference data types and/or ports in the orchestration from which they were called.</span></span> <span data-ttu-id="2f5cb-105">この種類のシナリオの例は、次のような特徴で示すことができます。</span><span class="sxs-lookup"><span data-stu-id="2f5cb-105">An example of this type of scenario is characterized by the following:</span></span>  
  
- <span data-ttu-id="2f5cb-106">2 つ以上のオーケストレーションがあります。</span><span class="sxs-lookup"><span data-stu-id="2f5cb-106">You have two or more orchestrations.</span></span>  
  
- <span data-ttu-id="2f5cb-107">最初のオーケストレーション (Orch1) が、一方向の Web サービス呼び出しで 2 番目のオーケストレーション (Orch2) を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="2f5cb-107">The first orchestration (Orch1) calls the second orchestration (Orch2) with a one-way Web service call.</span></span>  
  
- <span data-ttu-id="2f5cb-108">Orch2 は、Web サービス呼び出しで Orch1 に応答します。</span><span class="sxs-lookup"><span data-stu-id="2f5cb-108">Orch2 responds back to Orch1 with a Web service call.</span></span>  
  
  <span data-ttu-id="2f5cb-109">この種類のプロジェクトの一例は、[チュートリアル 2: 発注プロセス](http://msdn.microsoft.com/library/a324ef1b-39b3-49ab-9719-a13f526cb467)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2f5cb-109">For one example of this type of project, see [Tutorial 2: Purchase Order Process](http://msdn.microsoft.com/library/a324ef1b-39b3-49ab-9719-a13f526cb467).</span></span>  
  
### <a name="to-develop-two-interdependent-orchestrations-orch1-and-orch2"></a><span data-ttu-id="2f5cb-110">相互に依存する 2 つのオーケストレーション Orch1 と Orch2 を開発するには</span><span class="sxs-lookup"><span data-stu-id="2f5cb-110">To develop two interdependent orchestrations Orch1 and Orch2</span></span>  
  
1. <span data-ttu-id="2f5cb-111">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] を使用して、Web サービスとして公開される受信ポートを持つ Orch1 の部分的なバージョンを作成します。</span><span class="sxs-lookup"><span data-stu-id="2f5cb-111">Using [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], create a partial version of the Orch1 that has a receive port which will be exposed as a Web service.</span></span>  
  
2. <span data-ttu-id="2f5cb-112">Orch1 をコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="2f5cb-112">Compile Orch1.</span></span>  
  
3. <span data-ttu-id="2f5cb-113">Web サービス公開ウィザードを実行して、ポートを公開します。</span><span class="sxs-lookup"><span data-stu-id="2f5cb-113">Run the Web Services Publishing Wizard and publish the port.</span></span>  
  
4. <span data-ttu-id="2f5cb-114">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] を使用して、Orch1 の Web サービスを使用する Orch2 をすべて作成します。</span><span class="sxs-lookup"><span data-stu-id="2f5cb-114">Using [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], create and complete all of Orch2, consuming Orch1's web service.</span></span>  
  
5. <span data-ttu-id="2f5cb-115">Orch2 をコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="2f5cb-115">Compile Orch2.</span></span>  
  
6. <span data-ttu-id="2f5cb-116">Web サービス公開ウィザードを実行し、ポートを公開します。</span><span class="sxs-lookup"><span data-stu-id="2f5cb-116">Run the Web Services Publishing Wizard and publish the port(s).</span></span>  
  
7. <span data-ttu-id="2f5cb-117">必要に応じて、Orch2 の Web サービスを使用する Orch1 を作成します。</span><span class="sxs-lookup"><span data-stu-id="2f5cb-117">Complete Orch1, consuming Orch2's web service(s) as needed.</span></span>  
  
8. <span data-ttu-id="2f5cb-118">Orch1 を再コンパイルします。</span><span class="sxs-lookup"><span data-stu-id="2f5cb-118">Recompile Orch1.</span></span>  
  
9. <span data-ttu-id="2f5cb-119">Orch1 と Orch2 を展開します。</span><span class="sxs-lookup"><span data-stu-id="2f5cb-119">Deploy Orch1 and Orch2.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f5cb-120">参照</span><span class="sxs-lookup"><span data-stu-id="2f5cb-120">See Also</span></span>  
 [<span data-ttu-id="2f5cb-121">BizTalk Web サービス公開ウィザードを使用して、オーケストレーションを Web サービスとして公開する方法</span><span class="sxs-lookup"><span data-stu-id="2f5cb-121">How to Use the BizTalk Web Services Publishing Wizard to Publish an Orchestration as a Web Service</span></span>](../core/publish-orchestration-as-web-service--biztalk-web-services-publishing-wizard.md)