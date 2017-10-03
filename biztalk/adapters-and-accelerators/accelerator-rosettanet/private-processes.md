---
title: "プライベート プロセス |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- private processes, trading partners
- private processes, about private processes
- private processes, orchestrations
- private processes
- orchestrations, private-process orchestrations
- trading partners, private processes
- BTARN, private processes
- business processes, private processes
ms.assetid: 0c5895eb-22c1-431f-a769-ae6ca05d1e45
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b28bf49af1305220d96f129080b274b5391495eb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="private-processes"></a>プライベート プロセス
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]プライベート プロセスとして組織の内部には、ビジネス プロセスを実装します。 パブリック プロセスは、取引先との統合を伴うビジネス プロセスを処理します。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]service content 処理とバックエンド統合 (プライベート プロセス) から Framework RNIF (RosettaNet Implementation) 処理 (パブリック プロセス) を分離します。  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]長時間実行される BizTalk オーケストレーションとして、プライベート プロセスを実装します。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]開始側と応答側に 1 つの 1 つのプライベート プロセス オーケストレーションを使用します。 各プライベート プロセスは、着信または送信の Service Content メッセージ部を解釈して処理します。 プライベート プロセスは、パブリック プロセスとの間で Service Content の送受信を行います。 プライベート プロセスはヘッダーを処理しません。また、RNIF 処理も実行しません。 これらの処理は、パブリック プロセスが行います。  
  
 エンタープライズのシナリオでは、PIP メッセージ スキーマごとにプライベート プロセスが 1 つあるのが一般的です。 ただし、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK には、任意の PIP メッセージを処理できるプライベート プロセス オーケストレーションが 2 つあります。 1 つのオーケストレーションは、開始側プロセス (PrivateInitiator.odx を参照してください[PrivateInitiator サンプル &#91;RN3 &#93;](../../adapters-and-accelerators/accelerator-rosettanet/privateinitiator-sample.md)) その 1 つは応答側プロセス (PrivateResponder.odx を参照してください[PrivateResponder サンプル &#91;RN3 &#93;](../../adapters-and-accelerators/accelerator-rosettanet/privateresponder-sample.md)). [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] を特定のビジネス プロセスに適応させるためには、プライベート プロセスをカスタマイズする必要があります。  
  
 SDK には、ビジネス ルール PIP に固有のプライベート応答側プロセスを実装するプロセスも含まれています (PIP3A4PrivateResponder.odx を参照してください[3A4 プライベート応答側オーケストレーションを使用して、ビジネス ルール](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md))。  
  
 プライベート プロセスは、Service Content の書式をバックエンドの基幹業務 (LOB) 形式から XML 形式に変更します。 XML 形式に変更された Service Content は、すぐに [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] によって処理され、送信のためにパブリック プロセスによって RNIF 準拠のヘッダーが追加されます。  
  
 プライベート プロセスは、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]DATA [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] データベースの MessageToLOB テーブルと MessagesFromLOB テーブルを介して、バックエンドの基幹業務 (LOB) アプリケーションに接続します。 このデータベースは、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] と LOB アプリケーション間の通信を処理します。 LOB アプリケーションは、インターフェイスを使用して、データベース テーブルにアクセスします。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [開始側プライベート プロセス](../../adapters-and-accelerators/accelerator-rosettanet/initiator-private-process.md)  
  
-   [応答側プライベート プロセス](../../adapters-and-accelerators/accelerator-rosettanet/responder-private-process.md)