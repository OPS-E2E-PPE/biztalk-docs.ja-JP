---
title: プライベート プロセス チュートリアル |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- private processes, tutorial
- private process tutorial
- tutorials, private process tutorial
ms.assetid: 58affc48-af73-406e-895f-696bc284d945
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6c017d8b9b52c1f477aba62308ca2e65a1550564
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22209922"
---
# <a name="private-process-tutorial"></a><span data-ttu-id="e4dbe-102">プライベート プロセス チュートリアル</span><span class="sxs-lookup"><span data-stu-id="e4dbe-102">Private Process Tutorial</span></span>
<span data-ttu-id="e4dbe-103">このチュートリアルには、[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] を使用した完全なエンドツーエンドのソリューションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e4dbe-103">This tutorial contains a complete end-to-end solution using [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)].</span></span> <span data-ttu-id="e4dbe-104">ここでは、RosettaNet 準拠のソリューションを実装するために従う必要のある手順について詳しく説明します。この手順では、Contoso 社 (サプライヤー組織) と Fabrikam 社 (購入者組織) という 2 つの架空の会社間の取引シナリオを作成します。</span><span class="sxs-lookup"><span data-stu-id="e4dbe-104">The tutorial details the steps that you have to follow to implement a RosettaNet-compliant solution by creating a trading scenario between two fictitious companies: Contoso, the supplier organization, and Fabrikam, the buyer organization.</span></span>  
  
 <span data-ttu-id="e4dbe-105">このチュートリアルが実装するシナリオでは、3A2 - Price and Availability PIP (Partner Interface Process) を使用します。</span><span class="sxs-lookup"><span data-stu-id="e4dbe-105">The scenario this tutorial implements uses the 3A2-Price and Availability Partner Interface Process (PIP).</span></span> <span data-ttu-id="e4dbe-106">購入の前に、購入者である Fabrikam が 3A2 - Price and Availability Request をサプライヤーである Contoso に送信します。</span><span class="sxs-lookup"><span data-stu-id="e4dbe-106">Before a purchase, the buyer, Fabrikam, sends a 3A2-Price and Availability Request to the supplier, Contoso.</span></span> <span data-ttu-id="e4dbe-107">この PIP により、Fabrikam は製品に関する情報を取得し、その情報をビジネス ルールによって処理して、製品を購入するかどうかを決定することができます。</span><span class="sxs-lookup"><span data-stu-id="e4dbe-107">This PIP enables Fabrikam to obtain information about a certain product that they can then process through business rules to make a determination about whether to purchase the product.</span></span> <span data-ttu-id="e4dbe-108">次の図は、3A2 PIP の交換時における開始側の組織と応答側の組織の通信パターンを示しています。</span><span class="sxs-lookup"><span data-stu-id="e4dbe-108">The following figure shows the communication pattern between the initiator and responder organizations during a 3A2 PIP exchange.</span></span>  
  
 <span data-ttu-id="e4dbe-109">![(& m); 60変更なし &#62;。] (../../adapters-and-accelerators/accelerator-rosettanet/media/rn3-intro-eetut-3a2flow.gif "RN3_Intro_EETut_3A2Flow")</span><span class="sxs-lookup"><span data-stu-id="e4dbe-109">![&#60;No Change&#62;](../../adapters-and-accelerators/accelerator-rosettanet/media/rn3-intro-eetut-3a2flow.gif "RN3_Intro_EETut_3A2Flow")</span></span>  
  
 <span data-ttu-id="e4dbe-110">このチュートリアルでは、Contoso ソリューションに焦点を当てています。</span><span class="sxs-lookup"><span data-stu-id="e4dbe-110">The focus of this tutorial is on the Contoso solution.</span></span> <span data-ttu-id="e4dbe-111">ここでは、ERP の統合、ビジネス ポリシーの実施、プライベート プロセスのカスタマイズ、およびセキュリティで保護された通信の使用など、RosettaNet ベースのソリューションの作成についてさまざまな角度から概説しています。</span><span class="sxs-lookup"><span data-stu-id="e4dbe-111">It outlines various aspects of creating a RosettaNet-based solution, including ERP integration, business policy enforcement, private process customization, and promoting secure communication.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e4dbe-112">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="e4dbe-112">In This Section</span></span>  
  
-   [<span data-ttu-id="e4dbe-113">プライベート プロセス チュートリアルの準備</span><span class="sxs-lookup"><span data-stu-id="e4dbe-113">Preparing for the Private Process Tutorial</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/preparing-for-the-private-process-tutorial.md)  
  
-   [<span data-ttu-id="e4dbe-114">Contoso ソリューションの作成</span><span class="sxs-lookup"><span data-stu-id="e4dbe-114">Creating the Contoso Solution</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/creating-the-contoso-solution.md)  
  
-   [<span data-ttu-id="e4dbe-115">Fabrikam ソリューションの作成</span><span class="sxs-lookup"><span data-stu-id="e4dbe-115">Creating the Fabrikam Solution</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/creating-the-fabrikam-solution.md)  
  
-   [<span data-ttu-id="e4dbe-116">ソリューションをテストします。</span><span class="sxs-lookup"><span data-stu-id="e4dbe-116">Testing the Solution</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/testing-the-solution.md)