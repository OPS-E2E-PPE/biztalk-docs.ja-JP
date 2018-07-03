---
title: プライベート プロセス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3ff99f03b3a38ff9d8c1c33ec16b108e5bd58ca7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967489"
---
# <a name="private-processes"></a>プライベート プロセス
Microsoft[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]プライベート プロセスとして、組織の内部ビジネス プロセスを実装します。 パブリック プロセスは、取引先との統合に関係するビジネス プロセスを処理します。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] service content 処理とバックエンド統合 (プライベート プロセス) 内から Framework RNIF (RosettaNet Implementation) (パブリック プロセス) 内の処理を分離します。  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] プライベート プロセスは、長時間実行される BizTalk オーケストレーションとして実装します。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 発信側と応答側のいずれかで 1 つのプライベート プロセス オーケストレーションを使用します。 各プライベート プロセスは、着信または送信の Service Content メッセージ部を解釈して処理します。 プライベート プロセスは、パブリック プロセスとの間で Service Content の送受信を行います。 プライベート プロセスはヘッダーを処理しません。また、RNIF 処理も実行しません。 これらの処理は、パブリック プロセスが行います。  
  
 エンタープライズのシナリオでは、PIP メッセージ スキーマごとにプライベート プロセスが 1 つあるのが一般的です。 ただし、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK には、任意の PIP メッセージを処理できるプライベート プロセス オーケストレーションが 2 つあります。 1 つのオーケストレーションは、開始側プロセス (PrivateInitiator.odx を参照してください[PrivateInitiator サンプル&#91;RN3&#93;](../../adapters-and-accelerators/accelerator-rosettanet/privateinitiator-sample.md)) と 1 つは、応答側プロセス (PrivateResponder.odx を参照してください[PrivateResponderサンプル&#91;RN3&#93;](../../adapters-and-accelerators/accelerator-rosettanet/privateresponder-sample.md))。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] を特定のビジネス プロセスに適応させるためには、プライベート プロセスをカスタマイズする必要があります。  
  
 SDK には、ビジネス ルール PIP 固有の応答側プライベート プロセスを実装するプロセスも含まれています (PIP3A4PrivateResponder.odx を参照してください[3A4 プライベート レスポンダー オーケストレーションを使用してビジネス ルール](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md))。  
  
 プライベート プロセスは、Service Content の書式をバックエンドの基幹業務 (LOB) 形式から XML 形式に変更します。 XML 形式に変更された Service Content は、すぐに [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] によって処理され、送信のためにパブリック プロセスによって RNIF 準拠のヘッダーが追加されます。  
  
 プライベート プロセスは、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]DATA [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] データベースの MessageToLOB テーブルと MessagesFromLOB テーブルを介して、バックエンドの基幹業務 (LOB) アプリケーションに接続します。 このデータベースは、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] と LOB アプリケーション間の通信を処理します。 LOB アプリケーションは、インターフェイスを使用して、データベース テーブルにアクセスします。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [イニシエーター プライベート プロセス](../../adapters-and-accelerators/accelerator-rosettanet/initiator-private-process.md)  
  
-   [レスポンダー プライベート プロセス](../../adapters-and-accelerators/accelerator-rosettanet/responder-private-process.md)