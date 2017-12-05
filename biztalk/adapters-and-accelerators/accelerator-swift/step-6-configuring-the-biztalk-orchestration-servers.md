---
title: "手順 6: オーケストレーションの BizTalk Server の構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestration server, configuring
- configuring, orchestration servers
ms.assetid: 1eb38fac-264d-4730-b16b-572dbb6fabd9
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0e495be91cc80e072f58a1e8149feb64773f1e51
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="step-6-configuring-the-biztalk-orchestration-servers"></a><span data-ttu-id="92d07-102">手順 6: オーケストレーションの BizTalk Server を構成します。</span><span class="sxs-lookup"><span data-stu-id="92d07-102">Step 6: Configuring the BizTalk Orchestration Servers</span></span>
<span data-ttu-id="92d07-103">このセクションでは、BizTalk オーケストレーション サーバーの構成のガイドラインを示します。</span><span class="sxs-lookup"><span data-stu-id="92d07-103">This section provides guidelines on configuring the BizTalk Orchestration servers.</span></span>  
  
### <a name="to-configure-the-biztalk-orchestration-servers"></a><span data-ttu-id="92d07-104">BizTalk オーケストレーション サーバーを構成するには</span><span class="sxs-lookup"><span data-stu-id="92d07-104">To configure the BizTalk Orchestration servers</span></span>  
  
1.  <span data-ttu-id="92d07-105">追加/削除 から選択して、ネットワーク分散トランザクション コーディネーター (DTC) アクセスを有効にする[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]アプリケーション サーバー カテゴリの下にあるコンポーネント。</span><span class="sxs-lookup"><span data-stu-id="92d07-105">Enable Network Distributed Transaction Coordinator (DTC) access by selecting it from the Add/Remove [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Components under the Application Server category.</span></span> <span data-ttu-id="92d07-106">ネットワーク DTC クライアント アクセスが有効で、[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]前の手順でコンピューター。</span><span class="sxs-lookup"><span data-stu-id="92d07-106">Network DTC client access was enabled on the [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] computer in an earlier step.</span></span> <span data-ttu-id="92d07-107">次のサポート技術情報記事を参照してください、 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] DTC の問題のトラブルシューティングについては、ヘルプとサポート Web サイト。</span><span class="sxs-lookup"><span data-stu-id="92d07-107">See the following Knowledge Base articles on the [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Help and Support Web site for information about troubleshooting DTC issues:</span></span>  
  
    -   <span data-ttu-id="92d07-108">MS DTC ファイアウォールの問題のトラブルシューティングにあるどの[http://go.microsoft.com/fwlink/?linkid=48870](http://go.microsoft.com/fwlink/?linkid=48870)です。</span><span class="sxs-lookup"><span data-stu-id="92d07-108">How To Troubleshoot MS DTC Firewall Issues, located at [http://go.microsoft.com/fwlink/?linkid=48870](http://go.microsoft.com/fwlink/?linkid=48870).</span></span>  
  
    -   <span data-ttu-id="92d07-109">DTCTester ツールの使用にあるどの[http://go.microsoft.com/fwlink/?linkid=48871](http://go.microsoft.com/fwlink/?linkid=48871)です。</span><span class="sxs-lookup"><span data-stu-id="92d07-109">How To Use DTCTester Tool, located at [http://go.microsoft.com/fwlink/?linkid=48871](http://go.microsoft.com/fwlink/?linkid=48871).</span></span>  
  
    -   <span data-ttu-id="92d07-110">DTC が、ファイアウォールの内側にある場合は、構成を参照してください。[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]分散トランザクション コーディネーター (DTC) に「ファイアウォール経由の作業がある[http://go.microsoft.com/fwlink/?linkid=48872](http://go.microsoft.com/fwlink/?linkid=48872)です。</span><span class="sxs-lookup"><span data-stu-id="92d07-110">If DTC is behind a firewall, see Configuring [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Distributed Transaction Coordinator (DTC) to Work Through a Firewall, located at [http://go.microsoft.com/fwlink/?linkid=48872](http://go.microsoft.com/fwlink/?linkid=48872).</span></span>  
  
2.  <span data-ttu-id="92d07-111">BizTalk Server の追加のソフトウェアの前提条件のインストール、インストールして」の説明に従って、BizTalk Server を構成する[オーケストレーション サーバー上の BizTalk Server の構成をインストールおよび](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-server-on-the-orchestration-servers.md)です。</span><span class="sxs-lookup"><span data-stu-id="92d07-111">Install additional software prerequisites for BizTalk Server, and install and configure BizTalk Server, as described in [Installing and Configuring BizTalk Server on the Orchestration Servers](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-server-on-the-orchestration-servers.md).</span></span>  
  
3.  <span data-ttu-id="92d07-112">インストールし、構成[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]インストール」の説明に従って、[のインストールと BizTalk Accelerator for SWIFT メッセージング サーバー上を構成する](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-accelerator-for-swift-on-messaging-servers.md)です。</span><span class="sxs-lookup"><span data-stu-id="92d07-112">Install and configure [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] as described in Installing and [Installing and Configuring BizTalk Accelerator for SWIFT on Messaging Servers](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-accelerator-for-swift-on-messaging-servers.md).</span></span>  
  
 <span data-ttu-id="92d07-113">このセクションには、次のトピックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="92d07-113">This section contains:</span></span>  
  
-   [<span data-ttu-id="92d07-114">オーケストレーション サーバーに BizTalk Server をインストールして構成する</span><span class="sxs-lookup"><span data-stu-id="92d07-114">Installing and Configuring BizTalk Server on the Orchestration Servers</span></span>](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-server-on-the-orchestration-servers.md)  
  
-   [<span data-ttu-id="92d07-115">オーケストレーション サーバーに BizTalk Accelerator for SWIFT をインストールして構成する</span><span class="sxs-lookup"><span data-stu-id="92d07-115">Installing and Configuring BizTalk Accelerator for SWIFT on Orchestration Servers</span></span>](../../adapters-and-accelerators/accelerator-swift/install-and-configure-biztalk-accelerator-for-swift-on-orchestration-servers.md)