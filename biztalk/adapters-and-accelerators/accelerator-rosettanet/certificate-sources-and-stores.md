---
title: 証明書のソースとストア |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- certificates, certificate storage
- importing certificates
- certificates, certificate sources
- certificates, importing
ms.assetid: 3e98fb56-4368-46f3-9329-c44fed11f4fb
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f3ade897bb51850b4ef9dd6b530f5fc04c6b2601
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2018
ms.locfileid: "22210234"
---
# <a name="certificate-sources-and-stores"></a><span data-ttu-id="812a0-102">証明書のソースおよびストア</span><span class="sxs-lookup"><span data-stu-id="812a0-102">Certificate Sources and Stores</span></span>
<span data-ttu-id="812a0-103">ここでは、証明書のインポート元および証明書の格納先について説明します。</span><span class="sxs-lookup"><span data-stu-id="812a0-103">This topic describes where to import certificates from, and where to store certificates.</span></span>  
  
## <a name="certificate-sources"></a><span data-ttu-id="812a0-104">証明書のソース</span><span class="sxs-lookup"><span data-stu-id="812a0-104">Certificate Sources</span></span>  
 <span data-ttu-id="812a0-105">各種証明書のインポート元は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="812a0-105">You import certificates from the following files:</span></span>  
  
-   <span data-ttu-id="812a0-106">プライベート証明書.pfx ファイルまたは .p12 ファイルからインポートします。</span><span class="sxs-lookup"><span data-stu-id="812a0-106">Private certificates from .pfx or .p12 files.</span></span> <span data-ttu-id="812a0-107">証明書をインポートしたら、これらのファイルを安全に格納します。</span><span class="sxs-lookup"><span data-stu-id="812a0-107">After importing the certificates, store these files securely.</span></span> <span data-ttu-id="812a0-108">CertWizard ユーティリティを使用してプライベート証明書をインポートする場合は、設定、 **/exportable**に切り替える`False`、これが既定の設定、ファイルにストアからプライベート証明書をエクスポートできないようにします。</span><span class="sxs-lookup"><span data-stu-id="812a0-108">If you import the private certificates using the CertWizard utility, you can set the **/Exportable** switch to `False`, which is the default setting, so that the private certificates cannot be exported from the store into a file.</span></span> <span data-ttu-id="812a0-109">設定した場合、 **/exportable**に切り替える`True`、これらの証明書をファイルにエクスポートするには、証明書から[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]管理コンソール (MMC) です。</span><span class="sxs-lookup"><span data-stu-id="812a0-109">If you set the **/Exportable** switch to `True`, you can export these certificates to a file from the Certificates [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Management Console (MMC).</span></span>  
  
-   <span data-ttu-id="812a0-110">パブリック証明書.cer ファイルまたは .der ファイルからインポートします。</span><span class="sxs-lookup"><span data-stu-id="812a0-110">Public certificates from .cer or .der files.</span></span> <span data-ttu-id="812a0-111">パートナーは、これらのファイルを使用して証明書を送信します。</span><span class="sxs-lookup"><span data-stu-id="812a0-111">Partners send their certificates to you in these files.</span></span>  
  
-   <span data-ttu-id="812a0-112">ルート証明書.cer ファイルまたは .der ファイルからインポートします。</span><span class="sxs-lookup"><span data-stu-id="812a0-112">Root certificates from .cer or .der files.</span></span> <span data-ttu-id="812a0-113">証明機関は、これらのファイルを使用してルート証明書を送信します。</span><span class="sxs-lookup"><span data-stu-id="812a0-113">Certification authorities send their root certificates to you in these files.</span></span>  
  
## <a name="certificate-storage"></a><span data-ttu-id="812a0-114">証明書記憶域</span><span class="sxs-lookup"><span data-stu-id="812a0-114">Certificate Storage</span></span>  
 <span data-ttu-id="812a0-115">証明書は、ローカル コンピューター上に 2 つある証明書ストアのいずれか 1 つにインポートします。</span><span class="sxs-lookup"><span data-stu-id="812a0-115">You import certificates into one of two Certificates stores on the local computer.</span></span> <span data-ttu-id="812a0-116">パブリック証明書を格納する、**証明書 (ローカル コンピューター)** を格納します。</span><span class="sxs-lookup"><span data-stu-id="812a0-116">You store public certificates in the **Certificates (Local Computer)** store.</span></span> <span data-ttu-id="812a0-117">このストアのノードを開くことによって開くことができます、**証明書 (ローカル コンピューター)** 内のノード、 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)] ([!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]) 管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="812a0-117">You can open the nodes of this store by opening the **Certificates (Local Computer)** node in the [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)] ([!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]) Management Console.</span></span> <span data-ttu-id="812a0-118">アクセスすることができます、**証明書 (ローカル コンピューター)** コンピューターで管理者権限がある場合は、保存します。</span><span class="sxs-lookup"><span data-stu-id="812a0-118">You can access the **Certificates (Local Computer)** store if you have administrative permissions on the computer.</span></span> <span data-ttu-id="812a0-119">各種パブリック証明書の格納先は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="812a0-119">Store public certificates in the following folders:</span></span>  
  
-   <span data-ttu-id="812a0-120">ホーム パブリック証明書個人用フォルダーに、**証明書 (ローカル コンピューター)** 格納</span><span class="sxs-lookup"><span data-stu-id="812a0-120">Home public certificates in the Personal folder in the **Certificates (Local Computer)** store</span></span>  
  
-   <span data-ttu-id="812a0-121">パートナー パブリック証明書の [その他の人] フォルダーで、**証明書 (ローカル コンピューター)** 格納</span><span class="sxs-lookup"><span data-stu-id="812a0-121">Partner public certificates in the Other People folder of the **Certificates (Local Computer)** store</span></span>  
  
-   <span data-ttu-id="812a0-122">信頼されたルート証明機関 フォルダーに証明機関から証明書、**証明書 (ローカル コンピューター)** 格納</span><span class="sxs-lookup"><span data-stu-id="812a0-122">Certificates from certification authorities in the Trusted Root Certification Authority folder of the **Certificates (Local Computer)** store</span></span>  
  
 <span data-ttu-id="812a0-123">プライベート証明書を格納する、**証明書 - 現在のユーザー**を格納します。</span><span class="sxs-lookup"><span data-stu-id="812a0-123">You store private certificates in the **Certificates - Current User** store.</span></span> <span data-ttu-id="812a0-124">管理コンソールを使用して、開くことによって、このストアのノードを開くことができます、 **runas**コマンド ホスト サービス アカウントのユーザーにします。</span><span class="sxs-lookup"><span data-stu-id="812a0-124">You can open the nodes of this store by opening the Management Console using the **runas** command with the host service account user.</span></span> <span data-ttu-id="812a0-125">詳細については、次を参照してください。[証明書のインポート](../../adapters-and-accelerators/accelerator-rosettanet/importing-certificates.md)です。</span><span class="sxs-lookup"><span data-stu-id="812a0-125">For more information, see [Importing Certificates](../../adapters-and-accelerators/accelerator-rosettanet/importing-certificates.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="812a0-126">参照</span><span class="sxs-lookup"><span data-stu-id="812a0-126">See Also</span></span>  
 <span data-ttu-id="812a0-127">[CertWizard ユーティリティを使用して証明書のインポート](../../adapters-and-accelerators/accelerator-rosettanet/importing-certificates-using-the-certwizard-utility.md) </span><span class="sxs-lookup"><span data-stu-id="812a0-127">[Importing Certificates Using the CertWizard Utility](../../adapters-and-accelerators/accelerator-rosettanet/importing-certificates-using-the-certwizard-utility.md) </span></span>  
 <span data-ttu-id="812a0-128">[MMC を使用して証明書のインポート](../../adapters-and-accelerators/accelerator-rosettanet/importing-certificates-using-mmc.md) </span><span class="sxs-lookup"><span data-stu-id="812a0-128">[Importing Certificates Using MMC](../../adapters-and-accelerators/accelerator-rosettanet/importing-certificates-using-mmc.md) </span></span>  
 [<span data-ttu-id="812a0-129">証明書のインポート&#91;RN3&#93;</span><span class="sxs-lookup"><span data-stu-id="812a0-129">Importing Certificates &#91;RN3&#93;</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/certificate-sources-and-stores.md)