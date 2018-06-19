---
title: Certificates2 を管理する |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0e3bc75f-1a58-49d8-8a1d-6936b1a4105b
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 50b9542a6199b065a9c6d65f4adda9f8b52306ba
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26008515"
---
# <a name="managing-certificates"></a><span data-ttu-id="4c982-102">証明書の管理</span><span class="sxs-lookup"><span data-stu-id="4c982-102">Managing Certificates</span></span>
<span data-ttu-id="4c982-103">このセクションでは、BizTalk Server で使用されるデジタル証明書を管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4c982-103">This section describes how to manage digital certificates used with BizTalk Server.</span></span> <span data-ttu-id="4c982-104">その証明書をインストールする方法 (と説明にそれらをインストールするには、どのフォルダー)、および構成する方法[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]の MIME/SMIME と AS2、および BizTalk アダプターで使用するために、証明書を使用します。</span><span class="sxs-lookup"><span data-stu-id="4c982-104">Its topics describe how to install certificates (and which folder to install them into), and how to configure [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to use the certificate for MIME/SMIME and AS2, and for use with BizTalk adapters.</span></span> <span data-ttu-id="4c982-105">Microsoft BizTalk Server には、ドキュメントの暗号化および復号化のために公開キー基盤 (PKI) デジタル証明書を使用して、ドキュメントの署名と検証 (否認不可)、およびパーティの解決を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="4c982-105">Microsoft BizTalk Server can make use of public key infrastructure (PKI) digital certificates for purposes of document encryption and decryption, document signing and verification (non-repudiation), and party resolution.</span></span>  
  
 <span data-ttu-id="4c982-106">証明書をインストールする手順のチェックリストについては、次を参照してください。[チェックリスト: インストールと構成証明書](~/technical-guides/checklist-installing-and-configuring-certificates.md)です。</span><span class="sxs-lookup"><span data-stu-id="4c982-106">For a checklist of steps to install the certificates, see [Checklist: Installing and Configuring Certificates](~/technical-guides/checklist-installing-and-configuring-certificates.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4c982-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="4c982-107">In This Section</span></span>  
  
-   [<span data-ttu-id="4c982-108">Certificates2 を管理するためのベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="4c982-108">Best Practices for Managing Certificates2</span></span>](../technical-guides/best-practices-for-managing-certificates2.md)  
  
-   [<span data-ttu-id="4c982-109">BizTalk Server の証明書に関する既知の問題</span><span class="sxs-lookup"><span data-stu-id="4c982-109">Known Issues with Certificates in BizTalk Server</span></span>](../technical-guides/known-issues-with-certificates-in-biztalk-server.md)  
  
-   [<span data-ttu-id="4c982-110">デジタル証明書のインストールと構成</span><span class="sxs-lookup"><span data-stu-id="4c982-110">Installing and Configuring Digital Certificates</span></span>](~/technical-guides/installing-and-configuring-digital-certificates.md)