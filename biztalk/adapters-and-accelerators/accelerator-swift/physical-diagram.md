---
title: 物理的なダイアグラム |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying, network configuration
ms.assetid: 4291727b-8687-496a-8f03-0da4b3201967
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fafd068c0fe55d65d47518dcd0693a0ba1f71e3a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377091"
---
# <a name="physical-diagram"></a><span data-ttu-id="84852-102">物理的なダイアグラム</span><span class="sxs-lookup"><span data-stu-id="84852-102">Physical Diagram</span></span>
<span data-ttu-id="84852-103">一般的な展開には、メッセージング (送信および受信) の BizTalk Server コンピューターがクラスター化されたが、ビジネス プロセス (オーケストレーション)、InfoPath テンプレート (MRSR サイト) にアクセスするための BizTalk Server コンピューターを実行するための BizTalk Server コンピューターとクラスター化された SQL Server コンピューター。</span><span class="sxs-lookup"><span data-stu-id="84852-103">A typical deployment has clustered BizTalk Server computers for messaging (sending and receiving), BizTalk Server computers for executing the business process (orchestration), BizTalk Server computers for accessing the InfoPath templates (MRSR site), and clustered SQL Server computers.</span></span> <span data-ttu-id="84852-104">次のような配置により、イントラネットとインターネット ユーザーの両方からセキュリティで保護された環境です。</span><span class="sxs-lookup"><span data-stu-id="84852-104">The following deployment ensures a secure environment from both the intranet and Internet users.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="84852-105">この一般的な展開は、推奨される構成です。</span><span class="sxs-lookup"><span data-stu-id="84852-105">This typical deployment is the recommended configuration.</span></span> <span data-ttu-id="84852-106">独自のビジネス ニーズやサーバーの構成、デプロイが正常に動作していることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="84852-106">You will need to verify your own business needs and server configurations to make certain your deployment works correctly.</span></span>  
  
 <span data-ttu-id="84852-107">この展開アップまたはスケール ダウン、または使用状況のプロファイルと成長を続けるビジネス ニーズに応じて、スケールできます。</span><span class="sxs-lookup"><span data-stu-id="84852-107">You can scale this deployment up or down, out or back, depending on the usage profile and your growing business needs.</span></span> <span data-ttu-id="84852-108">スケーラビリティの一般的なシナリオにはより高い可用性やスループットを向上させることを確認するには、各クラスター内の 1 つまたは複数のサーバーの追加が含まれます。</span><span class="sxs-lookup"><span data-stu-id="84852-108">Typical scalability scenarios include adding one or more servers in each cluster to ensure higher availability or better throughput.</span></span> <span data-ttu-id="84852-109">小規模な企業が、同じサーバーでいずれかであるなど、複数の関数を実行して、デプロイをスケール バックを優先する可能性があります[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]コンピューターは、オーケストレーションとメッセージングの両方を処理します。</span><span class="sxs-lookup"><span data-stu-id="84852-109">Smaller enterprises might prefer scaling back their deployment to have the same servers perform multiple functions, such as having one [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] computer handle both orchestration and messaging.</span></span> <span data-ttu-id="84852-110">Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] 1 台のサーバーの展開をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="84852-110">Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] supports deployment on a single server.</span></span> <span data-ttu-id="84852-111">次の図は、完全な A4SWIFT 展開用の推奨される分散型展開環境の例を示します。</span><span class="sxs-lookup"><span data-stu-id="84852-111">The following figure shows an example of the recommended distributed deployment environment for a full A4SWIFT deployment.</span></span>  
  
 <span data-ttu-id="84852-112">![](../../adapters-and-accelerators/accelerator-swift/media/fsa-deploy-full.gif "FSA_Deploy_Full")</span><span class="sxs-lookup"><span data-stu-id="84852-112">![](../../adapters-and-accelerators/accelerator-swift/media/fsa-deploy-full.gif "FSA_Deploy_Full")</span></span>  
<span data-ttu-id="84852-113">A4SWIFT の完全なデプロイの例</span><span class="sxs-lookup"><span data-stu-id="84852-113">Example of a full A4SWIFT deployment</span></span>