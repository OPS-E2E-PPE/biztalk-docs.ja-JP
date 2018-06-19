---
title: サポートする安全な Sockets Layer (SSL) |Microsoft ドキュメント
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
ms.openlocfilehash: 086ec1715d76a25649cb2285b31b3df790b0fe3e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214162"
---
# <a name="supporting-secure-sockets-layer-ssl"></a><span data-ttu-id="2e2ef-102">Secure Sockets Layer (SSL) をサポートします。</span><span class="sxs-lookup"><span data-stu-id="2e2ef-102">Supporting Secure Sockets Layer (SSL)</span></span>
<span data-ttu-id="2e2ef-103">を、展開、クライアント コンピューターと MRSR サーバー間で Secure Sockets Layer (SSL) プロトコルを実装するのには、要求を、インターネット インフォメーション サービス (IIS) サーバーで「サーバー認証」の証明書を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e2ef-103">To implement the Secure Sockets Layer (SSL) protocol in your deployment between the client computers and the MRSR servers, you need to request and configure a "Server Authentication" certificate on your Internet Information Services (IIS) servers.</span></span>  
  
 <span data-ttu-id="2e2ef-104">ネットワーク負荷分散 (NLB) クラスター内のすべてのサーバーの 1 つの証明書を使用してください。</span><span class="sxs-lookup"><span data-stu-id="2e2ef-104">One certificate should be used for all the servers in your Network Load Balancing (NLB) cluster.</span></span> <span data-ttu-id="2e2ef-105">証明書の要求で使用される名前が、仮想ホスト名である個々 のサーバー名の代わりに行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e2ef-105">You should ensure that the name used in the certificate request is the virtual host name instead of an individual server name.</span></span>