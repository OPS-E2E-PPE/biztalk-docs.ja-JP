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
ms.openlocfilehash: 549c7cd01472345ab8449b35d2de6b5ef32ca0e7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65282592"
---
# <a name="private-processes"></a>プライベート プロセス
Microsoft[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]プライベート プロセスとして、組織の内部ビジネス プロセスを実装します。 パブリック プロセスは、取引先との統合に関係するビジネス プロセスを処理します。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] service content 処理とバックエンド統合 (プライベート プロセス) 内から Framework RNIF (RosettaNet Implementation) (パブリック プロセス) 内の処理を分離します。  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] プライベート プロセスは、長時間実行される BizTalk オーケストレーションとして実装します。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 発信側と応答側のいずれかで 1 つのプライベート プロセス オーケストレーションを使用します。 各プライベート プロセスは、解釈し、受信または送信のいずれかに、service content のメッセージ部分を処理します。 プライベート プロセスでは、service content を送信またはパブリック プロセスから受信します。 プライベート プロセスは、ヘッダーを処理しませんし、RNIF 処理は行われません。 パブリック プロセスが行います。  
  
 エンタープライズのシナリオで通常は 1 つのプライベート プロセスの各 PIP メッセージ スキーマ。 ただし、 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK には、任意の PIP メッセージを処理する 2 つのプライベート プロセス オーケストレーションが含まれています。 1 つのオーケストレーションは、開始側プロセス (PrivateInitiator.odx を参照してください[PrivateInitiator サンプル&#91;RN3&#93;](../../adapters-and-accelerators/accelerator-rosettanet/privateinitiator-sample.md)) と 1 つは、応答側プロセス (PrivateResponder.odx を参照してください[PrivateResponderサンプル&#91;RN3&#93;](../../adapters-and-accelerators/accelerator-rosettanet/privateresponder-sample.md))。 対応するプライベート プロセスをカスタマイズする必要があります[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]特定のビジネス プロセスにします。  
  
 SDK には、ビジネス ルール PIP 固有の応答側プライベート プロセスを実装するプロセスも含まれています (PIP3A4PrivateResponder.odx を参照してください[3A4 プライベート レスポンダー オーケストレーションを使用してビジネス ルール](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md))。  
  
 プライベート プロセスは、バックエンド基幹業務 (LOB) 形式から XML をサービス内容の書式を変更します。 XML 形式ではすぐ[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]、service content を処理し、パブリック プロセスは、サービスのコンテンツを転送する RNIF 準拠のヘッダーを追加します。  
  
 プライベート プロセスで MessageToLOB と MessagesFromLOB テーブルを介してバックエンドの基幹業務アプリケーションに接続する、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]データ[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]データベース。 このデータベースの間の通信を処理する[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]と LOB アプリケーション。 LOB アプリケーションでは、インターフェイスを使用して、データベース テーブルにアクセスできます。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [イニシエーター プライベート プロセス](../../adapters-and-accelerators/accelerator-rosettanet/initiator-private-process.md)  
  
-   [レスポンダー プライベート プロセス](../../adapters-and-accelerators/accelerator-rosettanet/responder-private-process.md)