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
# <a name="installing-certificates"></a>証明書のインストール
送信、修復、またはメッセージを送信するには、インストールされている適切な証明書が必要です。 このトピックでは、証明書を追加する方法について説明します。 運用環境では、IT 部門の証明書を参照してください。  
  
 **概要**  
  
 このセクションでは、作成し、次の証明書を格納する方法の手順を示します。  
  
-   Message Repair and New Submission ロール証明書 - 現在のユーザーの個人用フォルダー内の各証明書は、各クライアント コンピューターに保存します。  
  
-   Message Repair and New Submission ロール証明書 (ローカル コンピューター) の [その他の人] フォルダー内の各証明書を各 BizTalk オーケストレーション サーバー コンピューターに保存します。  
  
-   各クライアント コンピューター上の (ローカル コンピューター) の証明書ストアの信頼されたルート証明機関 フォルダーに証明機関の証明書  
  
 展開した場合[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]1 台のコンピューターの管理パスから、証明書サーバーを除外する必要があります、同じコンピューターにインストールされている証明書サーバーもされて[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]SharePoint サーバー。  
  
 このセクションには、次のトピックが含まれています。  
  
-   [クライアントの証明書ストアに証明書を追加します。](../../adapters-and-accelerators/accelerator-swift/adding-certificates-to-the-certificates-store-on-the-client.md)  
  
-   [サーバー上の証明書ストアに証明書を追加します。](../../adapters-and-accelerators/accelerator-swift/adding-certificates-to-the-certificates-store-on-the-server.md)  
  
-   [1 台のコンピューター展開の管理パスから CertSrv の除外](../../adapters-and-accelerators/accelerator-swift/excluding-certsrv-from-managed-paths-on-a-single-computer-deployment.md)