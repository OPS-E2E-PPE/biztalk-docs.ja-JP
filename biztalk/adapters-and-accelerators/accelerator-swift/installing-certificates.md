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
# <a name="installing-certificates"></a>証明書のインストール
送信、修復、またはメッセージの送信するには、インストールされている適切な証明書が必要です。 このトピックでは、証明書を追加する方法について説明します。 運用環境では、証明書用に IT 部門を参照してください。  

 **概要**  

 ここでは、作成し、次の証明書を格納する方法の手順を示します。  

- Message Repair and New Submission ロール証明書 - 現在のユーザーの個人用フォルダー内の各証明書は、各クライアント コンピューターに保存します。  

- Message Repair and New Submission ロール証明書 (ローカル コンピューター) の他のユーザー フォルダー内の各証明書を BizTalk オーケストレーション サーバーの各コンピューターで保存します。  

- 各クライアント コンピューター (ローカル コンピューター) の証明書ストアの信頼されたルート証明機関のフォルダーに証明機関の証明書  

  デプロイした場合[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]1 台のコンピューターにも、同じコンピューターにインストールされている証明書サーバーがあるとは、Microsoft SharePoint Server の管理パスから証明書サーバーを除外する必要があります。  

  このセクションには、次のトピックが含まれています。  

- [クライアント上の証明書ストアに証明書を追加する](../../adapters-and-accelerators/accelerator-swift/adding-certificates-to-the-certificates-store-on-the-client.md)  

- [サーバー上の証明書ストアに証明書を追加する](../../adapters-and-accelerators/accelerator-swift/adding-certificates-to-the-certificates-store-on-the-server.md)  

- 
  [1 台のコンピューターの展開の管理パスから CertSrv を除外する](../../adapters-and-accelerators/accelerator-swift/excluding-certsrv-from-managed-paths-on-a-single-computer-deployment.md)
