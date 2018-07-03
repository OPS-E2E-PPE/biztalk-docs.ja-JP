---
title: MSMQ アダプターを使用したトランザクション処理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MSMQ adapters, transaction handling
- transactions, MSMQ adapters
ms.assetid: 2e5dd0da-3852-48bf-9372-b019ecab23be
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e55494175029fd8edda1a457298af1d829be3087
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980923"
---
# <a name="transaction-handling-with-the-msmq-adapter"></a>MSMQ アダプターを使用したトランザクション処理
このセクションでは、送受信の際のトランザクションの機能について説明します。  
  
> [!NOTE]
>  MSMQ アダプターは、リモート キューを使用している場合でも、BizTalk メッセージ ボックス データベースからローカルのメッセージ キューのキューにトランザクションを拡張します。  
  
 MSMQ アダプターを使用した、送信と受信のいずれでも、トランザクションを使用できます。 トランザクションを使用した送信では、アダプターでバッチが完成するまでメッセージが蓄積されます。 その後バッチは、ローカルのメッセージ キュー サービスに単一のトランザクションとして送信されます。 送信に失敗した場合、バッチは再送信されます。 再送信も失敗した場合、セカンダリ トランスポートに移動されます。  
  
> [!NOTE]
>  アダプターはメッセージ キュー 4.0 以降を使用したリモート キューのトランザクション読み込みのみをサポートしています。 このシナリオでは、BizTalk Server とリモート メッセージ キュー サーバーの両方必要があります実行しているメッセージ キュー 4.0 またはそれ以降。  
  
 トランザクションを使用した受信では、アダプターは失敗したメッセージを、失わないように保留します。 受信の間、バッチが完成するまでメッセージがバッチに追加されます。 その後、バッチが送信されます。  
  
- 問題が発生せず、サーバーでメッセージを受信した場合、トランザクションはコミットされます。  
  
- 問題が発生した場合、新しいバッチが現在のトランザクションの一部として作成されます。 問題のあるメッセージは新しいバッチに移動されます。 その後、最初のバッチが再送信され、新しいバッチが保留中のメッセージとして送信されます。 この再送信で問題が発生しなかった場合、トランザクションはコミットされます。  
  
  クラスター化された BizTalk ホスト インスタンスで MSMQ アダプターの送信ハンドラーを実行している場合、トランザクションの一貫性を確保するために、MSMQ サービスを同一のクラスター グループにクラスター化してください。  
  
  DCOMCNFG ユーティリティで [ネットワーク DTC アクセス] が無効になっている場合、MSMQ トランザクション リモート受信操作は解読不明のエラー メッセージで失敗します。  MSMQ アダプターでトランザクション リモート受信を行うには、[ネットワーク DTC アクセス] を有効にする必要があります。 詳細をご覧[ http://go.microsoft.com/fwlink/?LinkId=124623](http://go.microsoft.com/fwlink/?LinkId=124623)します。  
  
  MSMQ はリモートのトランザクションの読み込みをサポートしていないので、クラスター化された BizTalk ホスト インスタンスで MSMQ アダプターの受信ハンドラーを実行している場合は、ローカルのトランザクションの読み込みをサポートするために、MSMQ サービスを同一のクラスター グループにクラスター化してください。 BizTalk ホストのクラスター化されたインスタンスで MSMQ アダプター ハンドラーの実行に関する詳細については、次を参照してください。[クラスター化ホストでアダプター ハンドラーの実行に関する考慮事項](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)します。  
  
## <a name="see-also"></a>参照  
 [MSMQ アダプターを使用した信頼できるメッセージ処理](../core/reliable-messaging-with-the-msmq-adapter.md)