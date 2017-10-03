---
title: "手順 5: メッセージング サーバー BizTalk の構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuring, BizTalk Messaging servers
- BizTalk Messaging servers, configuring
ms.assetid: 598d336d-b006-4d02-9249-e9d6d9b6b7b5
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9e1aea1187417b77071f0821547869a5b84549c7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-5-configuring-the-biztalk-messaging-servers"></a><span data-ttu-id="bebbc-102">手順 5: 構成の BizTalk メッセージング サーバー</span><span class="sxs-lookup"><span data-stu-id="bebbc-102">Step 5: Configuring the BizTalk Messaging Servers</span></span>
<span data-ttu-id="bebbc-103">このセクションでは、BizTalk メッセージングのサーバーの構成のガイドラインを示します。</span><span class="sxs-lookup"><span data-stu-id="bebbc-103">This section provides guidelines on configuring the BizTalk Messaging servers.</span></span>  
  
### <a name="to-configure-the-biztalk-messaging-servers"></a><span data-ttu-id="bebbc-104">BizTalk メッセージング サーバーを構成するには</span><span class="sxs-lookup"><span data-stu-id="bebbc-104">To configure the BizTalk Messaging servers</span></span>  
  
1.  <span data-ttu-id="bebbc-105">追加/削除 から選択して、ネットワーク分散トランザクション コーディネーター (DTC) アクセスを有効にする[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]アプリケーション サーバー カテゴリの下にあるコンポーネント。</span><span class="sxs-lookup"><span data-stu-id="bebbc-105">Enable Network Distributed Transaction Coordinator (DTC) access by selecting it from the Add/Remove [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Components under the Application Server category.</span></span> <span data-ttu-id="bebbc-106">ネットワーク DTC クライアント アクセスが有効で、[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]前の手順でコンピューター。</span><span class="sxs-lookup"><span data-stu-id="bebbc-106">Network DTC client access was enabled on the [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] computer in an earlier step.</span></span> <span data-ttu-id="bebbc-107">次のサポート技術情報記事を参照してください、 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] DTC の問題のトラブルシューティングについては、ヘルプとサポート Web サイト。</span><span class="sxs-lookup"><span data-stu-id="bebbc-107">See the following Knowledge Base articles on the [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Help and Support Web site for information about troubleshooting DTC issues:</span></span>  
  
    -   <span data-ttu-id="bebbc-108">MS DTC ファイアウォールの問題のトラブルシューティングにあるどの[http://go.microsoft.com/fwlink/?linkid=48870](http://go.microsoft.com/fwlink/?linkid=48870)です。</span><span class="sxs-lookup"><span data-stu-id="bebbc-108">How To Troubleshoot MS DTC Firewall Issues, located at [http://go.microsoft.com/fwlink/?linkid=48870](http://go.microsoft.com/fwlink/?linkid=48870).</span></span>  
  
    -   <span data-ttu-id="bebbc-109">DTCTester ツールの使用にあるどの[http://go.microsoft.com/fwlink/?linkid=48871](http://go.microsoft.com/fwlink/?linkid=48871)です。</span><span class="sxs-lookup"><span data-stu-id="bebbc-109">How To Use DTCTester Tool, located at [http://go.microsoft.com/fwlink/?linkid=48871](http://go.microsoft.com/fwlink/?linkid=48871).</span></span>  
  
    -   <span data-ttu-id="bebbc-110">DTC が、ファイアウォールの内側にある場合を参照してください"構成[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]ファイアウォール経由で動作する分散トランザクション コーディネーター (DTC)"に配置されている[http://go.microsoft.com/fwlink/?linkid=48872](http://go.microsoft.com/fwlink/?linkid=48872)です。</span><span class="sxs-lookup"><span data-stu-id="bebbc-110">If DTC is behind a firewall, see "Configuring [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Distributed Transaction Coordinator (DTC) to Work Through a Firewall", located at [http://go.microsoft.com/fwlink/?linkid=48872](http://go.microsoft.com/fwlink/?linkid=48872).</span></span>  
  
2.  <span data-ttu-id="bebbc-111">構成し、BizTalk のネットワーク負荷分散の確認」の説明に従って、サーバーを受信[手順 2: サーバー上の NLB の構成](../../adapters-and-accelerators/accelerator-swift/step-2-configuring-nlb-on-the-servers.md)です。</span><span class="sxs-lookup"><span data-stu-id="bebbc-111">Configure and verify Network Load Balancing on the BizTalk receive servers as described in [Step 2: Configuring NLB on the Servers](../../adapters-and-accelerators/accelerator-swift/step-2-configuring-nlb-on-the-servers.md).</span></span>  
  
3.  <span data-ttu-id="bebbc-112">インストールし、構成[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]」の説明に従って[のインストールと BizTalk Accelerator for SWIFT メッセージング サーバー上を構成する](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-accelerator-for-swift-on-messaging-servers.md)です。</span><span class="sxs-lookup"><span data-stu-id="bebbc-112">Install and configure [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] as described in [Installing and Configuring BizTalk Accelerator for SWIFT on Messaging Servers](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-accelerator-for-swift-on-messaging-servers.md).</span></span>  
  
 <span data-ttu-id="bebbc-113">このセクションには、次のトピックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="bebbc-113">This section contains:</span></span>  
  
-   [<span data-ttu-id="bebbc-114">インストールして、メッセージング サーバー上の BizTalk Server の構成</span><span class="sxs-lookup"><span data-stu-id="bebbc-114">Installing and Configuring BizTalk Server on the Messaging Server</span></span>](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-server-on-the-messaging-server.md)  
  
-   [<span data-ttu-id="bebbc-115">インストールと構成 BizTalk Accelerator for SWIFT のメッセージング サーバー</span><span class="sxs-lookup"><span data-stu-id="bebbc-115">Installing and Configuring BizTalk Accelerator for SWIFT on Messaging Servers</span></span>](../../adapters-and-accelerators/accelerator-swift/installing-and-configuring-biztalk-accelerator-for-swift-on-messaging-servers.md)