---
title: "証明書のインポート |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- importing certificates
- certificates, importing
ms.assetid: c2576f89-b5de-4250-9c54-74c8a218bb39
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c78773d6eb1fc7e51ca80afadfd282d54def80b2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="importing-certificates"></a><span data-ttu-id="d7531-102">証明書のインポート</span><span class="sxs-lookup"><span data-stu-id="d7531-102">Importing Certificates</span></span>
<span data-ttu-id="d7531-103">ここでは、インポート先、格納先、インポートに使用するツールなど、証明書のインポート方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d7531-103">This section describes how to import certificates, including where to import them from, where to store them, and what tools to use to import them.</span></span>  
  
 <span data-ttu-id="d7531-104">証明書をインポートする方法は 2 つあります。</span><span class="sxs-lookup"><span data-stu-id="d7531-104">There are two ways to import certificates.</span></span> <span data-ttu-id="d7531-105">CertWizard ツールを使用する方法と、[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] 管理コンソール (MMC) の証明書スナップインを使用する方法です。</span><span class="sxs-lookup"><span data-stu-id="d7531-105">You can use the CertWizard tool or the Certificates snap-in for [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Management Console (MMC).</span></span>  
  
-   <span data-ttu-id="d7531-106">CertWizard は、スイッチの設定に基づいて証明書の使用法を構成する段階的なコマンド ライン ウィザードです。</span><span class="sxs-lookup"><span data-stu-id="d7531-106">CertWizard is a step-by-step command-line wizard that configures the use of the certificate based on the settings of switches.</span></span> <span data-ttu-id="d7531-107">このツールで使用できる、 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] SDK のフォルダーです。</span><span class="sxs-lookup"><span data-stu-id="d7531-107">This tool is available in the [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] SDK folder.</span></span>  
  
-   <span data-ttu-id="d7531-108">MMC の証明書スナップインを使用しても、証明書を証明書ストアにインポートできます。</span><span class="sxs-lookup"><span data-stu-id="d7531-108">With the Certificates snap-in in MMC, you can import a certificate into the certificate store.</span></span> <span data-ttu-id="d7531-109">ただし、この手動プロセスを使用した場合は、証明書の使用法を個別に構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d7531-109">However, this manual process requires that you configure the use of the certificate separately.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="d7531-110">MMC のプライベート証明書をインポートまたは使用するには、ログオンしているユーザーが BizTalk ホストのユーザー ID を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d7531-110">To import or work with private certificates in MMC, the user who is logged on must have the user identity of the BizTalk Hosts.</span></span> <span data-ttu-id="d7531-111">Not を実行する場合、 **runas**コマンド、ユーザー スイッチと証明書 MMC を起動するホスト サービス アカウントと**runas/user:hostsvc mmc**です。</span><span class="sxs-lookup"><span data-stu-id="d7531-111">If not, you must run the **runas** command with the user switch and the host service account to start the Certificates MMC, for example, **runas /user:hostsvc mmc**.</span></span> <span data-ttu-id="d7531-112">このコマンドを実行することにより、BizTalk ホスト (BizTalkServerApplication および BizTalkServerIsolatedHost) のユーザー ID を想定します。</span><span class="sxs-lookup"><span data-stu-id="d7531-112">By running this command, you assume the user identity of the BizTalk Hosts (BizTalkServerApplication and BizTalkServerIsolatedHost).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d7531-113">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="d7531-113">In This Section</span></span>  
  
-   [<span data-ttu-id="d7531-114">証明書のソースおよびストア</span><span class="sxs-lookup"><span data-stu-id="d7531-114">Certificate Sources and Stores</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/certificate-sources-and-stores.md)  
  
-   [<span data-ttu-id="d7531-115">CertWizard ユーティリティを使用して証明書のインポート</span><span class="sxs-lookup"><span data-stu-id="d7531-115">Importing Certificates Using the CertWizard Utility</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/importing-certificates-using-the-certwizard-utility.md)  
  
-   [<span data-ttu-id="d7531-116">MMC を使用して証明書のインポート</span><span class="sxs-lookup"><span data-stu-id="d7531-116">Importing Certificates Using MMC</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/importing-certificates-using-mmc.md)