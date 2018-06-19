---
title: 物理図 |Microsoft ドキュメント
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
ms.openlocfilehash: 0fcd0558d8fe3d45063a53800b1f3c082a2ba056
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22213962"
---
# <a name="physical-diagram"></a><span data-ttu-id="70343-102">物理的なダイアグラム</span><span class="sxs-lookup"><span data-stu-id="70343-102">Physical Diagram</span></span>
<span data-ttu-id="70343-103">一般的な展開には、メッセージング (送信および受信) を BizTalk Server コンピューターがクラスター化されたビジネス プロセス (オーケストレーション)、InfoPath テンプレート (MRSR サイト) にアクセスするための BizTalk Server コンピューターを実行するための BizTalk Server コンピューターとクラスター化された SQL Server コンピューター。</span><span class="sxs-lookup"><span data-stu-id="70343-103">A typical deployment has clustered BizTalk Server computers for messaging (sending and receiving), BizTalk Server computers for executing the business process (orchestration), BizTalk Server computers for accessing the InfoPath templates (MRSR site), and clustered SQL Server computers.</span></span> <span data-ttu-id="70343-104">次の展開では、イントラネットとインターネット ユーザーの両方からセキュリティで保護された環境が保証されます。</span><span class="sxs-lookup"><span data-stu-id="70343-104">The following deployment ensures a secure environment from both the intranet and Internet users.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="70343-105">この一般的な展開は、推奨される構成です。</span><span class="sxs-lookup"><span data-stu-id="70343-105">This typical deployment is the recommended configuration.</span></span> <span data-ttu-id="70343-106">独自のビジネス ニーズとサーバーの構成、展開が正常に動作を確認することを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="70343-106">You will need to verify your own business needs and server configurations to make certain your deployment works correctly.</span></span>  
  
 <span data-ttu-id="70343-107">この展開を上下、out、または利用状況のプロファイルと増大するビジネス ニーズに応じてを拡張することができます。</span><span class="sxs-lookup"><span data-stu-id="70343-107">You can scale this deployment up or down, out or back, depending on the usage profile and your growing business needs.</span></span> <span data-ttu-id="70343-108">一般的なスケーラビリティ シナリオには、高い可用性やスループットを向上させることを確認するには、各クラスター内の 1 つまたは複数のサーバーの追加が含まれます。</span><span class="sxs-lookup"><span data-stu-id="70343-108">Typical scalability scenarios include adding one or more servers in each cluster to ensure higher availability or better throughput.</span></span> <span data-ttu-id="70343-109">小規模な企業を使用しても、同じサーバーを 1 つを持つなど、複数の機能を実行して、展開でスケール バック[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]コンピューターは、オーケストレーションとメッセージングの両方を処理します。</span><span class="sxs-lookup"><span data-stu-id="70343-109">Smaller enterprises might prefer scaling back their deployment to have the same servers perform multiple functions, such as having one [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] computer handle both orchestration and messaging.</span></span> [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="70343-110">[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]単一のサーバーに展開をサポートします。</span><span class="sxs-lookup"><span data-stu-id="70343-110">[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] supports deployment on a single server.</span></span> <span data-ttu-id="70343-111">次の図は、完全な A4SWIFT 展開に推奨される分散デプロイ環境の例を示します。</span><span class="sxs-lookup"><span data-stu-id="70343-111">The following figure shows an example of the recommended distributed deployment environment for a full A4SWIFT deployment.</span></span>  
  
 ![](../../adapters-and-accelerators/accelerator-swift/media/fsa-deploy-full.gif "FSA_Deploy_Full")  
<span data-ttu-id="70343-112">A4SWIFT の完全展開の例</span><span class="sxs-lookup"><span data-stu-id="70343-112">Example of a full A4SWIFT deployment</span></span>