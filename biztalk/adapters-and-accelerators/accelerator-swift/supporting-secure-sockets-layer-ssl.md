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
# <a name="supporting-secure-sockets-layer-ssl"></a>Secure Sockets Layer (SSL) をサポートしています。
を、展開、クライアント コンピューターと MRSR サーバー間で Secure Sockets Layer (SSL) プロトコルを実装するには、要求を、インターネット インフォメーション サービス (IIS) サーバーを「サーバー認証」の証明書を構成する必要があります。  
  
 ネットワーク負荷分散 (NLB) クラスター内のすべてのサーバーの 1 つの証明書を使用する必要があります。 証明書の要求で使用される名前が、個々 のサーバー名の代わりに、仮想ホスト名を確認してください。