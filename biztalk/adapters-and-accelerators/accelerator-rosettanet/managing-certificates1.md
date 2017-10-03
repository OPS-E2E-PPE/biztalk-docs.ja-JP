---
title: "Certificates1 を管理する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing certificates
- certificates, managing
ms.assetid: ffa60e2b-c131-4a49-ad1e-6c8a7271b05c
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c3d74342d15d65082b6d94f252023c3df1d601dd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="managing-certificates"></a><span data-ttu-id="98eab-102">証明書の管理</span><span class="sxs-lookup"><span data-stu-id="98eab-102">Managing Certificates</span></span>
<span data-ttu-id="98eab-103">RosettaNet で通信をセキュリティで保護するには、証明書を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="98eab-103">Secure communications in RosettaNet require using certificates.</span></span> [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="98eab-104">® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] では、証明書を使用して、送信メッセージの暗号化、送信メッセージへの署名、着信メッセージの暗号化の解除、着信メッセージに記された署名の確認を行います。</span><span class="sxs-lookup"><span data-stu-id="98eab-104">® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] uses certificates to encrypt outgoing messages, sign outgoing messages, decrypt incoming messages, and verify the signature in incoming messages.</span></span>  
  
 <span data-ttu-id="98eab-105">証明書を使用するには、次の手順の一部またはすべてを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="98eab-105">To use certificates, you must perform some or all of the following steps:</span></span>  
  
-   <span data-ttu-id="98eab-106">証明書をサーバーの証明書ストアにインポートします。</span><span class="sxs-lookup"><span data-stu-id="98eab-106">Import certificates into the certificates store for the server</span></span>  
  
-   <span data-ttu-id="98eab-107">メッセージに証明書の使用法を構成します。</span><span class="sxs-lookup"><span data-stu-id="98eab-107">Configure the use of certificates in messages</span></span>  
  
-   <span data-ttu-id="98eab-108">証明書をパートナーにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="98eab-108">Export certificates to partners</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="98eab-109">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="98eab-109">In This Section</span></span>  
  
-   [<span data-ttu-id="98eab-110">証明書のインポート</span><span class="sxs-lookup"><span data-stu-id="98eab-110">Importing Certificates</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/importing-certificates.md)  
  
-   [<span data-ttu-id="98eab-111">証明書のエクスポート</span><span class="sxs-lookup"><span data-stu-id="98eab-111">Exporting Certificates</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/exporting-certificates.md)