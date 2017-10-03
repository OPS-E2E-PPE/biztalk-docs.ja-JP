---
title: "サポートする安全な Sockets Layer (SSL) |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: SSL
ms.assetid: 012a5be0-bab8-4a60-9d63-b9684b91e4a7
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 086ec1715d76a25649cb2285b31b3df790b0fe3e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="supporting-secure-sockets-layer-ssl"></a>Secure Sockets Layer (SSL) をサポートします。
を、展開、クライアント コンピューターと MRSR サーバー間で Secure Sockets Layer (SSL) プロトコルを実装するのには、要求を、インターネット インフォメーション サービス (IIS) サーバーで「サーバー認証」の証明書を構成する必要があります。  
  
 ネットワーク負荷分散 (NLB) クラスター内のすべてのサーバーの 1 つの証明書を使用してください。 証明書の要求で使用される名前が、仮想ホスト名である個々 のサーバー名の代わりに行う必要があります。