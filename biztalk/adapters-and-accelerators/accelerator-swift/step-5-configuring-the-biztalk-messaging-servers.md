---
title: 手順 5:BizTalk メッセージング サーバーの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring, BizTalk Messaging servers
- BizTalk Messaging servers, configuring
ms.assetid: 598d336d-b006-4d02-9249-e9d6d9b6b7b5
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 72211a5570d40e1eaae7ad3974496937ca9aed2a
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530081"
---
# <a name="step-5-configuring-the-biztalk-messaging-servers"></a><span data-ttu-id="9a10e-102">手順 5:BizTalk メッセージング サーバーを構成します。</span><span class="sxs-lookup"><span data-stu-id="9a10e-102">Step 5: Configuring the BizTalk Messaging Servers</span></span>
<span data-ttu-id="9a10e-103">このセクションでは、BizTalk メッセージング サーバーの構成のガイドラインを示します。</span><span class="sxs-lookup"><span data-stu-id="9a10e-103">This section provides guidelines on configuring the BizTalk Messaging servers.</span></span>  
  
### <a name="to-configure-the-biztalk-messaging-servers"></a><span data-ttu-id="9a10e-104">BizTalk メッセージング サーバーを構成するには</span><span class="sxs-lookup"><span data-stu-id="9a10e-104">To configure the BizTalk Messaging servers</span></span>  
  
1. <span data-ttu-id="9a10e-105">追加/削除 から選択して、ネットワーク分散トランザクション コーディネーター (DTC) アクセスを有効にする[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]アプリケーション サーバーのカテゴリの下にあるコンポーネント。</span><span class="sxs-lookup"><span data-stu-id="9a10e-105">Enable Network Distributed Transaction Coordinator (DTC) access by selecting it from the Add/Remove [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Components under the Application Server category.</span></span> <span data-ttu-id="9a10e-106">ネットワーク DTC クライアント アクセスが有効で、[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]前の手順でコンピューター。</span><span class="sxs-lookup"><span data-stu-id="9a10e-106">Network DTC client access was enabled on the [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] computer in an earlier step.</span></span> <span data-ttu-id="9a10e-107">DTC の問題のトラブルシューティングについては、Microsoft ヘルプとサポート Web サイトでは、次のサポート技術情報の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9a10e-107">See the following Knowledge Base articles on the Microsoft Help and Support Web site for information about troubleshooting DTC issues:</span></span>  
  
   - <span data-ttu-id="9a10e-108">MS DTC ファイアウォールの問題のトラブルシューティングにあるどの[ http://go.microsoft.com/fwlink/?linkid=48870](http://go.microsoft.com/fwlink/?linkid=48870)します。</span><span class="sxs-lookup"><span data-stu-id="9a10e-108">How To Troubleshoot MS DTC Firewall Issues, located at [http://go.microsoft.com/fwlink/?linkid=48870](http://go.microsoft.com/fwlink/?linkid=48870).</span></span>  
  
   - <span data-ttu-id="9a10e-109">使用 DTCTester ツールには、ある[ http://go.microsoft.com/fwlink/?linkid=48871](http://go.microsoft.com/fwlink/?linkid=48871)します。</span><span class="sxs-lookup"><span data-stu-id="9a10e-109">How To Use DTCTester Tool, located at [http://go.microsoft.com/fwlink/?linkid=48871](http://go.microsoft.com/fwlink/?linkid=48871).</span></span>  
  
   - <span data-ttu-id="9a10e-110">DTC をファイアウォールの背後にある場合は、「を構成する Microsoft 分散トランザクション コーディネーター (DTC) をファイアウォール経由で動作」にあるを参照してください。 [ http://go.microsoft.com/fwlink/?linkid=48872](http://go.microsoft.com/fwlink/?linkid=48872)します。</span><span class="sxs-lookup"><span data-stu-id="9a10e-110">If DTC is behind a firewall, see "Configuring Microsoft Distributed Transaction Coordinator (DTC) to Work Through a Firewall", located at [http://go.microsoft.com/fwlink/?linkid=48872](http://go.microsoft.com/fwlink/?linkid=48872).</span></span>  
  
2. <span data-ttu-id="9a10e-111">構成し、BizTalk のネットワーク負荷分散の確認」の説明に従ってサーバーが表示される[手順 2。サーバーに NLB を構成する](../../adapters-and-accelerators/accelerator-swift/step-2-configuring-nlb-on-the-servers.md)します。</span><span class="sxs-lookup"><span data-stu-id="9a10e-111">Configure and verify Network Load Balancing on the BizTalk receive servers as described in [Step 2: Configuring NLB on the Servers](../../adapters-and-accelerators/accelerator-swift/step-2-configuring-nlb-on-the-servers.md).</span></span>  
  
3. <span data-ttu-id="9a10e-112">インストールし、構成[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]」の説明に従って[BizTalk Accelerator for SWIFT のメッセージング サーバーに構成をインストールおよび](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-accelerator-for-swift-on-messaging-servers.md)します。</span><span class="sxs-lookup"><span data-stu-id="9a10e-112">Install and configure [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] as described in [Installing and Configuring BizTalk Accelerator for SWIFT on Messaging Servers](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-accelerator-for-swift-on-messaging-servers.md).</span></span>  
  
   <span data-ttu-id="9a10e-113">このセクションには、次のトピックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="9a10e-113">This section contains:</span></span>  
  
-   [<span data-ttu-id="9a10e-114">メッセージング サーバーに BizTalk Server をインストールして構成する</span><span class="sxs-lookup"><span data-stu-id="9a10e-114">Installing and Configuring BizTalk Server on the Messaging Server</span></span>](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-server-on-the-messaging-server.md)  
  
-   [<span data-ttu-id="9a10e-115">メッセージング サーバーに BizTalk Accelerator for SWIFT をインストールして構成する</span><span class="sxs-lookup"><span data-stu-id="9a10e-115">Installing and Configuring BizTalk Accelerator for SWIFT on Messaging Servers</span></span>](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-accelerator-for-swift-on-messaging-servers.md)