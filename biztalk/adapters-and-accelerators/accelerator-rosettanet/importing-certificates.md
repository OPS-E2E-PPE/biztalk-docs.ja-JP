---
title: 証明書のインポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- importing certificates
- certificates, importing
ms.assetid: c2576f89-b5de-4250-9c54-74c8a218bb39
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 96dd45cb6a4f973b98a0a7a4a0c32c2d8452c0a0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65283653"
---
# <a name="importing-certificates"></a><span data-ttu-id="69877-102">証明書のインポート</span><span class="sxs-lookup"><span data-stu-id="69877-102">Importing Certificates</span></span>
<span data-ttu-id="69877-103">このセクションは、証明書をインポートする方法を説明しますからそれらをインポートする場所、それを格納する場所を使用してそれらをインポートするどのようなツールなど。</span><span class="sxs-lookup"><span data-stu-id="69877-103">This section describes how to import certificates, including where to import them from, where to store them, and what tools to use to import them.</span></span>  
  
 <span data-ttu-id="69877-104">証明書をインポートする 2 つの方法はあります。</span><span class="sxs-lookup"><span data-stu-id="69877-104">There are two ways to import certificates.</span></span> <span data-ttu-id="69877-105">Microsoft 管理コンソール (MMC) を CertWizard ツールまたは証明書スナップインに使用することができます。</span><span class="sxs-lookup"><span data-stu-id="69877-105">You can use the CertWizard tool or the Certificates snap-in for Microsoft Management Console (MMC).</span></span>  
  
- <span data-ttu-id="69877-106">CertWizard は、スイッチの設定に基づく証明書の使用を構成するステップ バイ ステップのコマンド ライン ウィザードです。</span><span class="sxs-lookup"><span data-stu-id="69877-106">CertWizard is a step-by-step command-line wizard that configures the use of the certificate based on the settings of switches.</span></span> <span data-ttu-id="69877-107">このツールは、Microsoft で使用できる[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]SDK フォルダー。</span><span class="sxs-lookup"><span data-stu-id="69877-107">This tool is available in the Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] SDK folder.</span></span>  
  
- <span data-ttu-id="69877-108">証明書スナップイン MMC で、証明書ストアに証明書をインポートできます。</span><span class="sxs-lookup"><span data-stu-id="69877-108">With the Certificates snap-in in MMC, you can import a certificate into the certificate store.</span></span> <span data-ttu-id="69877-109">ただし、この手動プロセスでは、証明書の使用を個別に構成することが必要です。</span><span class="sxs-lookup"><span data-stu-id="69877-109">However, this manual process requires that you configure the use of the certificate separately.</span></span>  
  
  > [!IMPORTANT]
  >  <span data-ttu-id="69877-110">インポートまたは MMC のプライベート証明書の使用、ログオンしているユーザーは、BizTalk ホストのユーザー id が必要です。</span><span class="sxs-lookup"><span data-stu-id="69877-110">To import or work with private certificates in MMC, the user who is logged on must have the user identity of the BizTalk Hosts.</span></span> <span data-ttu-id="69877-111">そうでないを実行する必要がある場合、 **runas**コマンドと、ユーザー スイッチとホスト サービス アカウントは、証明書 MMC の起動を**runas/user:hostsvc mmc**します。</span><span class="sxs-lookup"><span data-stu-id="69877-111">If not, you must run the **runas** command with the user switch and the host service account to start the Certificates MMC, for example, **runas /user:hostsvc mmc**.</span></span> <span data-ttu-id="69877-112">このコマンドを実行すると、BizTalk ホスト (BizTalkServerApplication および BizTalkServerIsolatedHost) のユーザー id を想定します。</span><span class="sxs-lookup"><span data-stu-id="69877-112">By running this command, you assume the user identity of the BizTalk Hosts (BizTalkServerApplication and BizTalkServerIsolatedHost).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="69877-113">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="69877-113">In This Section</span></span>  
  
-   [<span data-ttu-id="69877-114">証明書のインポート元と証明書ストア</span><span class="sxs-lookup"><span data-stu-id="69877-114">Certificate Sources and Stores</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/certificate-sources-and-stores.md)  
  
-   [<span data-ttu-id="69877-115">CertWizard ユーティリティを使用した証明書のインポート</span><span class="sxs-lookup"><span data-stu-id="69877-115">Importing Certificates Using the CertWizard Utility</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/importing-certificates-using-the-certwizard-utility.md)  
  
-   [<span data-ttu-id="69877-116">MMC を使用した証明書のインポート</span><span class="sxs-lookup"><span data-stu-id="69877-116">Importing Certificates Using MMC</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/importing-certificates-using-mmc.md)