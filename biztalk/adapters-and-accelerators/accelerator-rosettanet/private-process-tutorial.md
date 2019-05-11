---
title: プライベート プロセス チュートリアル |Microsoft Docs
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
ms.openlocfilehash: adb94c1f7897ecd848d63f9141d2c244fccd0a07
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65282585"
---
# <a name="private-process-tutorial"></a><span data-ttu-id="bad75-102">プライベート プロセス チュートリアル</span><span class="sxs-lookup"><span data-stu-id="bad75-102">Private Process Tutorial</span></span>
<span data-ttu-id="bad75-103">このチュートリアルには、Microsoft® を使用して完全なエンド ツー エンド ソリューションが含まれています。[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="bad75-103">This tutorial contains a complete end-to-end solution using Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)].</span></span> <span data-ttu-id="bad75-104">このチュートリアルには、2 つの架空の企業間取引シナリオを作成して、RosettaNet 準拠のソリューションを実装するために従う必要のある手順が詳しく説明します。Contoso、サプライヤーの組織と Fabrikam の購入者組織の場合は。</span><span class="sxs-lookup"><span data-stu-id="bad75-104">The tutorial details the steps that you have to follow to implement a RosettaNet-compliant solution by creating a trading scenario between two fictitious companies: Contoso, the supplier organization, and Fabrikam, the buyer organization.</span></span>  
  
 <span data-ttu-id="bad75-105">このチュートリアルを実装するシナリオでは、3 a 2 Price and Availability パートナー インターフェイス プロセス (PIP) を使用します。</span><span class="sxs-lookup"><span data-stu-id="bad75-105">The scenario this tutorial implements uses the 3A2-Price and Availability Partner Interface Process (PIP).</span></span> <span data-ttu-id="bad75-106">、購入する前に、その、購入者で、Fabrikam が 3 a 2 Price and Availability Request をサプライヤーである Contoso に送信します。</span><span class="sxs-lookup"><span data-stu-id="bad75-106">Before a purchase, the buyer, Fabrikam, sends a 3A2-Price and Availability Request to the supplier, Contoso.</span></span> <span data-ttu-id="bad75-107">この PIP により、Fabrikam は製品を購入するかどうかを決定するビジネス ルールを処理できる、特定の商品に関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="bad75-107">This PIP enables Fabrikam to obtain information about a certain product that they can then process through business rules to make a determination about whether to purchase the product.</span></span> <span data-ttu-id="bad75-108">次の図は、3 a 2 PIP の交換中に、イニシエーターとレスポンダーの組織間の通信パターンを示します。</span><span class="sxs-lookup"><span data-stu-id="bad75-108">The following figure shows the communication pattern between the initiator and responder organizations during a 3A2 PIP exchange.</span></span>  
  
 <span data-ttu-id="bad75-109">![&#60;変更なし&#62;](../../adapters-and-accelerators/accelerator-rosettanet/media/rn3-intro-eetut-3a2flow.gif "RN3_Intro_EETut_3A2Flow")</span><span class="sxs-lookup"><span data-stu-id="bad75-109">![&#60;No Change&#62;](../../adapters-and-accelerators/accelerator-rosettanet/media/rn3-intro-eetut-3a2flow.gif "RN3_Intro_EETut_3A2Flow")</span></span>  
  
 <span data-ttu-id="bad75-110">このチュートリアルの焦点は、Contoso ソリューションです。</span><span class="sxs-lookup"><span data-stu-id="bad75-110">The focus of this tutorial is on the Contoso solution.</span></span> <span data-ttu-id="bad75-111">これには、RosettaNet ベースのソリューションを作成する、ERP の統合、ビジネス ポリシーの実施、プライベート プロセスのカスタマイズ、およびセキュリティで保護された通信の昇格のさまざまな側面について説明します。</span><span class="sxs-lookup"><span data-stu-id="bad75-111">It outlines various aspects of creating a RosettaNet-based solution, including ERP integration, business policy enforcement, private process customization, and promoting secure communication.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bad75-112">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="bad75-112">In This Section</span></span>  
  
-   [<span data-ttu-id="bad75-113">プライベート プロセス チュートリアルの準備</span><span class="sxs-lookup"><span data-stu-id="bad75-113">Preparing for the Private Process Tutorial</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/preparing-for-the-private-process-tutorial.md)  
  
-   [<span data-ttu-id="bad75-114">Contoso ソリューションの作成</span><span class="sxs-lookup"><span data-stu-id="bad75-114">Creating the Contoso Solution</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/creating-the-contoso-solution.md)  
  
-   [<span data-ttu-id="bad75-115">Fabrikam ソリューションの作成</span><span class="sxs-lookup"><span data-stu-id="bad75-115">Creating the Fabrikam Solution</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/creating-the-fabrikam-solution.md)  
  
-   [<span data-ttu-id="bad75-116">ソリューションのテスト</span><span class="sxs-lookup"><span data-stu-id="bad75-116">Testing the Solution</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/testing-the-solution.md)