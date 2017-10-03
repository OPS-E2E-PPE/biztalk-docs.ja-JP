---
title: "証明書のインストール |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- certificates, installing
- installing, certificates
ms.assetid: 7525f771-623c-420f-99ca-c834e819829d
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f5ded26548303dfe9c9a095c24396b4e2683ca4a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="installing-certificates"></a><span data-ttu-id="abc6c-102">証明書のインストール</span><span class="sxs-lookup"><span data-stu-id="abc6c-102">Installing Certificates</span></span>
<span data-ttu-id="abc6c-103">送信、修復、またはメッセージを送信するには、インストールされている適切な証明書が必要です。</span><span class="sxs-lookup"><span data-stu-id="abc6c-103">To send, repair, or submit messages, you must have the proper certificates installed.</span></span> <span data-ttu-id="abc6c-104">このトピックでは、証明書を追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="abc6c-104">This topic describes how to add certificates.</span></span> <span data-ttu-id="abc6c-105">運用環境では、IT 部門の証明書を参照してください。</span><span class="sxs-lookup"><span data-stu-id="abc6c-105">In a production environment, see your IT department for certificates.</span></span>  
  
 <span data-ttu-id="abc6c-106">**概要**</span><span class="sxs-lookup"><span data-stu-id="abc6c-106">**Summary**</span></span>  
  
 <span data-ttu-id="abc6c-107">このセクションでは、作成し、次の証明書を格納する方法の手順を示します。</span><span class="sxs-lookup"><span data-stu-id="abc6c-107">This section provides instructions on how to create and store the following certificates:</span></span>  
  
-   <span data-ttu-id="abc6c-108">Message Repair and New Submission ロール証明書 - 現在のユーザーの個人用フォルダー内の各証明書は、各クライアント コンピューターに保存します。</span><span class="sxs-lookup"><span data-stu-id="abc6c-108">Certificates for each of the Message Repair and New Submission roles in the Personal folder of the Certificates - Current User store on each client computer</span></span>  
  
-   <span data-ttu-id="abc6c-109">Message Repair and New Submission ロール証明書 (ローカル コンピューター) の [その他の人] フォルダー内の各証明書を各 BizTalk オーケストレーション サーバー コンピューターに保存します。</span><span class="sxs-lookup"><span data-stu-id="abc6c-109">Certificates for each of the Message Repair and New Submission roles in the Other People folder of the Certificates (Local Computer) store on each BizTalk orchestration server computer</span></span>  
  
-   <span data-ttu-id="abc6c-110">各クライアント コンピューター上の (ローカル コンピューター) の証明書ストアの信頼されたルート証明機関 フォルダーに証明機関の証明書</span><span class="sxs-lookup"><span data-stu-id="abc6c-110">Certification Authority's certificate into the Trusted Root Certification Authorities folder in the Certificates (Local Computer) store on each client computer</span></span>  
  
 <span data-ttu-id="abc6c-111">展開した場合[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]1 台のコンピューターの管理パスから、証明書サーバーを除外する必要があります、同じコンピューターにインストールされている証明書サーバーもされて[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]SharePoint サーバー。</span><span class="sxs-lookup"><span data-stu-id="abc6c-111">If you have deployed [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] on a single computer, and also have a certificate server installed on the same computer, you need to exclude the certificate server from the managed paths for [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] SharePoint Server.</span></span>  
  
 <span data-ttu-id="abc6c-112">このセクションには、次のトピックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="abc6c-112">This section contains:</span></span>  
  
-   [<span data-ttu-id="abc6c-113">クライアントの証明書ストアに証明書を追加します。</span><span class="sxs-lookup"><span data-stu-id="abc6c-113">Adding Certificates to the Certificates Store on the Client</span></span>](../../adapters-and-accelerators/accelerator-swift/adding-certificates-to-the-certificates-store-on-the-client.md)  
  
-   [<span data-ttu-id="abc6c-114">サーバー上の証明書ストアに証明書を追加します。</span><span class="sxs-lookup"><span data-stu-id="abc6c-114">Adding Certificates to the Certificates Store on the Server</span></span>](../../adapters-and-accelerators/accelerator-swift/adding-certificates-to-the-certificates-store-on-the-server.md)  
  
-   [<span data-ttu-id="abc6c-115">1 台のコンピューター展開の管理パスから CertSrv の除外</span><span class="sxs-lookup"><span data-stu-id="abc6c-115">Excluding CertSrv from Managed Paths on a Single-Computer Deployment</span></span>](../../adapters-and-accelerators/accelerator-swift/excluding-certsrv-from-managed-paths-on-a-single-computer-deployment.md)