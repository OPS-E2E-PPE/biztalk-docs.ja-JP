---
title: 手順 6:BizTalk オーケストレーション サーバーの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestration server, configuring
- configuring, orchestration servers
ms.assetid: 1eb38fac-264d-4730-b16b-572dbb6fabd9
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 59b1eea5ca26e951f25ebda75a09941afba6fabf
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530112"
---
# <a name="step-6-configuring-the-biztalk-orchestration-servers"></a><span data-ttu-id="2395b-102">手順 6:BizTalk オーケストレーション サーバーの構成</span><span class="sxs-lookup"><span data-stu-id="2395b-102">Step 6: Configuring the BizTalk Orchestration Servers</span></span>
<span data-ttu-id="2395b-103">このセクションでは、BizTalk オーケストレーション サーバーの構成のガイドラインを提供します。</span><span class="sxs-lookup"><span data-stu-id="2395b-103">This section provides guidelines on configuring the BizTalk Orchestration servers.</span></span>  
  
### <a name="to-configure-the-biztalk-orchestration-servers"></a><span data-ttu-id="2395b-104">BizTalk オーケストレーション サーバーを構成するには</span><span class="sxs-lookup"><span data-stu-id="2395b-104">To configure the BizTalk Orchestration servers</span></span>  
  
1. <span data-ttu-id="2395b-105">追加/削除 から選択して、ネットワーク分散トランザクション コーディネーター (DTC) アクセスを有効にする[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]アプリケーション サーバーのカテゴリの下にあるコンポーネント。</span><span class="sxs-lookup"><span data-stu-id="2395b-105">Enable Network Distributed Transaction Coordinator (DTC) access by selecting it from the Add/Remove [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Components under the Application Server category.</span></span> <span data-ttu-id="2395b-106">ネットワーク DTC クライアント アクセスが有効で、[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]前の手順でコンピューター。</span><span class="sxs-lookup"><span data-stu-id="2395b-106">Network DTC client access was enabled on the [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] computer in an earlier step.</span></span> <span data-ttu-id="2395b-107">DTC の問題のトラブルシューティングについては、Microsoft ヘルプとサポート Web サイトでは、次のサポート技術情報の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2395b-107">See the following Knowledge Base articles on the Microsoft Help and Support Web site for information about troubleshooting DTC issues:</span></span>  
  
   - <span data-ttu-id="2395b-108">MS DTC ファイアウォールの問題のトラブルシューティングにあるどの[ http://go.microsoft.com/fwlink/?linkid=48870](http://go.microsoft.com/fwlink/?linkid=48870)します。</span><span class="sxs-lookup"><span data-stu-id="2395b-108">How To Troubleshoot MS DTC Firewall Issues, located at [http://go.microsoft.com/fwlink/?linkid=48870](http://go.microsoft.com/fwlink/?linkid=48870).</span></span>  
  
   - <span data-ttu-id="2395b-109">使用 DTCTester ツールには、ある[ http://go.microsoft.com/fwlink/?linkid=48871](http://go.microsoft.com/fwlink/?linkid=48871)します。</span><span class="sxs-lookup"><span data-stu-id="2395b-109">How To Use DTCTester Tool, located at [http://go.microsoft.com/fwlink/?linkid=48871](http://go.microsoft.com/fwlink/?linkid=48871).</span></span>  
  
   - <span data-ttu-id="2395b-110">DTC をファイアウォールの背後にある場合は、構成する Microsoft 分散トランザクション コーディネーター (DTC) をファイアウォール経由で動作にあるを参照してください。 [ http://go.microsoft.com/fwlink/?linkid=48872](http://go.microsoft.com/fwlink/?linkid=48872)します。</span><span class="sxs-lookup"><span data-stu-id="2395b-110">If DTC is behind a firewall, see Configuring Microsoft Distributed Transaction Coordinator (DTC) to Work Through a Firewall, located at [http://go.microsoft.com/fwlink/?linkid=48872](http://go.microsoft.com/fwlink/?linkid=48872).</span></span>  
  
2. <span data-ttu-id="2395b-111">追加のソフトウェアの前提条件、BizTalk Server のインストールをインストールして、BizTalk Server を構成する」の説明に従って[オーケストレーション サーバーに BizTalk Server の構成をインストールおよび](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-server-on-the-orchestration-servers.md)します。</span><span class="sxs-lookup"><span data-stu-id="2395b-111">Install additional software prerequisites for BizTalk Server, and install and configure BizTalk Server, as described in [Installing and Configuring BizTalk Server on the Orchestration Servers](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-server-on-the-orchestration-servers.md).</span></span>  
  
3. <span data-ttu-id="2395b-112">インストールし、構成[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]インストール」の説明に従って、 [BizTalk Accelerator for SWIFT のメッセージング サーバーに構成をインストールおよび](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-accelerator-for-swift-on-messaging-servers.md)します。</span><span class="sxs-lookup"><span data-stu-id="2395b-112">Install and configure [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] as described in Installing and [Installing and Configuring BizTalk Accelerator for SWIFT on Messaging Servers](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-accelerator-for-swift-on-messaging-servers.md).</span></span>  
  
   <span data-ttu-id="2395b-113">このセクションには、次のトピックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="2395b-113">This section contains:</span></span>  
  
-   [<span data-ttu-id="2395b-114">オーケストレーション サーバーに BizTalk Server をインストールして構成する</span><span class="sxs-lookup"><span data-stu-id="2395b-114">Installing and Configuring BizTalk Server on the Orchestration Servers</span></span>](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-server-on-the-orchestration-servers.md)  
  
-   [<span data-ttu-id="2395b-115">オーケストレーション サーバーに BizTalk Accelerator for SWIFT をインストールして構成する</span><span class="sxs-lookup"><span data-stu-id="2395b-115">Installing and Configuring BizTalk Accelerator for SWIFT on Orchestration Servers</span></span>](../../adapters-and-accelerators/accelerator-swift/install-and-configure-biztalk-accelerator-for-swift-on-orchestration-servers.md)