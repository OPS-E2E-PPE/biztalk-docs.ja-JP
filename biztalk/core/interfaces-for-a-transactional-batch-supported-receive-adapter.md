---
title: 受信アダプターのバッチでサポートされているトランザクション パブリケーション用のインターフェイス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5289e8b8-4447-4196-9f7c-5e60c6598d8d
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f46c7662fac5010c4f1effe56016fe2f5c5d5e8f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65331556"
---
# <a name="interfaces-for-a-transactional-batch-supported-receive-adapter"></a>バッチ処理に対応したトランザクション受信アダプター用のインターフェイス
受信アダプターは、作成し、メッセージのトランザクション送信が必要な場合は、トランザクションを制御します。  
  
 トランザクション受信アダプターは、作成し、Microsoft 分散トランザクション コーディネーター (MSDTC) トランザクションへのポインターを渡します、**完了**のメソッド、 **IBTTransportBatch**インターフェイス。 これにより、すべてのバッチ操作は、その特定のトランザクション オブジェクトのスコープ内で実行されます。 バッチ送信が完了したら、アダプターのコールバック メソッドがコミットまたはトランザクションをロールバックします。 トランスポート プロキシから返されたかかるアクション、状態によって異なります、可能性がある他のトランザクション関連の作業時に、アダプターは表示されませんをトランスポート プロキシ。 アダプターは、トランザクションが失敗または成功したかどうかを判断します。 アダプター (コミットまたはロールバック) トランザクションの結果に報告、トランスポート プロキシを使用して、 **DTCCommitConfirm**のメソッド、**IBTDTCCommitConfirm**インターフェイス。 渡します`true`成功したトランザクションのまたは`false`エラー。  
  
 次の図は、受信アダプターのバッチでサポートされているトランザクションの作成に関連するオブジェクトの相互作用を示しています。  
  
 ![](../core/media/ebiz-sdk-devadapter2.gif "ebiz_sdk_devadapter2")  
DTC トランザクションを使用してメッセージのバッチを送信する受信アダプターのワークフロー  
  
## <a name="see-also"></a>参照  
 [アダプター変数](../core/adapter-variables.md)   
 [開発、受信アダプター](../core/developing-a-receive-adapter.md)   
 [インスタンス化と初期化、アダプターの受信](../core/instantiating-and-initializing-a-receive-adapter.md)   
 [受信アダプターをインプロセスで用のインターフェイス](../core/interfaces-for-an-in-process-receive-adapter.md)   
 [インターフェイスの分離受信アダプター](../core/interfaces-for-an-isolated-receive-adapter.md)   
 [受信アダプターのバッチ サポート用のインターフェイス](../core/interfaces-for-a-batch-supported-receive-adapter.md)   
 [要求 - 応答の同期受信アダプター用のインターフェイス](../core/interfaces-for-a-synchronous-request-response-receive-adapter.md)