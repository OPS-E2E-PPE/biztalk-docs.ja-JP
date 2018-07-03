---
title: 証明書のインストール |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- certificates, installing
- installing, certificates
ms.assetid: 7525f771-623c-420f-99ca-c834e819829d
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 111bd267bc7d0bc12d582c3b74846b8874ed8b4d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012547"
---
# <a name="installing-certificates"></a><span data-ttu-id="c5763-102">証明書のインストール</span><span class="sxs-lookup"><span data-stu-id="c5763-102">Installing Certificates</span></span>
<span data-ttu-id="c5763-103">送信、修復、またはメッセージの送信するには、インストールされている適切な証明書が必要です。</span><span class="sxs-lookup"><span data-stu-id="c5763-103">To send, repair, or submit messages, you must have the proper certificates installed.</span></span> <span data-ttu-id="c5763-104">このトピックでは、証明書を追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c5763-104">This topic describes how to add certificates.</span></span> <span data-ttu-id="c5763-105">運用環境では、証明書用に IT 部門を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c5763-105">In a production environment, see your IT department for certificates.</span></span>  

 <span data-ttu-id="c5763-106">**概要**</span><span class="sxs-lookup"><span data-stu-id="c5763-106">**Summary**</span></span>  

 <span data-ttu-id="c5763-107">ここでは、作成し、次の証明書を格納する方法の手順を示します。</span><span class="sxs-lookup"><span data-stu-id="c5763-107">This section provides instructions on how to create and store the following certificates:</span></span>  

- <span data-ttu-id="c5763-108">Message Repair and New Submission ロール証明書 - 現在のユーザーの個人用フォルダー内の各証明書は、各クライアント コンピューターに保存します。</span><span class="sxs-lookup"><span data-stu-id="c5763-108">Certificates for each of the Message Repair and New Submission roles in the Personal folder of the Certificates - Current User store on each client computer</span></span>  

- <span data-ttu-id="c5763-109">Message Repair and New Submission ロール証明書 (ローカル コンピューター) の他のユーザー フォルダー内の各証明書を BizTalk オーケストレーション サーバーの各コンピューターで保存します。</span><span class="sxs-lookup"><span data-stu-id="c5763-109">Certificates for each of the Message Repair and New Submission roles in the Other People folder of the Certificates (Local Computer) store on each BizTalk orchestration server computer</span></span>  

- <span data-ttu-id="c5763-110">各クライアント コンピューター (ローカル コンピューター) の証明書ストアの信頼されたルート証明機関のフォルダーに証明機関の証明書</span><span class="sxs-lookup"><span data-stu-id="c5763-110">Certification Authority's certificate into the Trusted Root Certification Authorities folder in the Certificates (Local Computer) store on each client computer</span></span>  

  <span data-ttu-id="c5763-111">デプロイした場合[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]1 台のコンピューターにも、同じコンピューターにインストールされている証明書サーバーがあるとは、Microsoft SharePoint Server の管理パスから証明書サーバーを除外する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c5763-111">If you have deployed [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] on a single computer, and also have a certificate server installed on the same computer, you need to exclude the certificate server from the managed paths for Microsoft SharePoint Server.</span></span>  

  <span data-ttu-id="c5763-112">このセクションには、次のトピックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="c5763-112">This section contains:</span></span>  

- [<span data-ttu-id="c5763-113">クライアント上の証明書ストアに証明書を追加する</span><span class="sxs-lookup"><span data-stu-id="c5763-113">Adding Certificates to the Certificates Store on the Client</span></span>](../../adapters-and-accelerators/accelerator-swift/adding-certificates-to-the-certificates-store-on-the-client.md)  

- [<span data-ttu-id="c5763-114">サーバー上の証明書ストアに証明書を追加する</span><span class="sxs-lookup"><span data-stu-id="c5763-114">Adding Certificates to the Certificates Store on the Server</span></span>](../../adapters-and-accelerators/accelerator-swift/adding-certificates-to-the-certificates-store-on-the-server.md)  

- <span data-ttu-id="c5763-115">
  [1 台のコンピューターの展開の管理パスから CertSrv を除外する](../../adapters-and-accelerators/accelerator-swift/excluding-certsrv-from-managed-paths-on-a-single-computer-deployment.md)</span><span class="sxs-lookup"><span data-stu-id="c5763-115">[Excluding CertSrv from Managed Paths on a Single-Computer Deployment](../../adapters-and-accelerators/accelerator-swift/excluding-certsrv-from-managed-paths-on-a-single-computer-deployment.md)</span></span>
