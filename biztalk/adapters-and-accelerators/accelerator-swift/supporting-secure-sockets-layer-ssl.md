---
title: セキュリティで保護をサポートしている Sockets Layer (SSL) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SSL
ms.assetid: 012a5be0-bab8-4a60-9d63-b9684b91e4a7
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cb8d38a6d381069d6e240187f2ca956f09b774f5
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529818"
---
# <a name="supporting-secure-sockets-layer-ssl"></a><span data-ttu-id="29ce4-102">Secure Sockets Layer (SSL) をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="29ce4-102">Supporting Secure Sockets Layer (SSL)</span></span>
<span data-ttu-id="29ce4-103">を、展開、クライアント コンピューターと MRSR サーバー間で Secure Sockets Layer (SSL) プロトコルを実装するには、要求を、インターネット インフォメーション サービス (IIS) サーバーを「サーバー認証」の証明書を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="29ce4-103">To implement the Secure Sockets Layer (SSL) protocol in your deployment between the client computers and the MRSR servers, you need to request and configure a "Server Authentication" certificate on your Internet Information Services (IIS) servers.</span></span>  
  
 <span data-ttu-id="29ce4-104">ネットワーク負荷分散 (NLB) クラスター内のすべてのサーバーの 1 つの証明書を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="29ce4-104">One certificate should be used for all the servers in your Network Load Balancing (NLB) cluster.</span></span> <span data-ttu-id="29ce4-105">証明書の要求で使用される名前が、個々 のサーバー名の代わりに、仮想ホスト名を確認してください。</span><span class="sxs-lookup"><span data-stu-id="29ce4-105">You should ensure that the name used in the certificate request is the virtual host name instead of an individual server name.</span></span>