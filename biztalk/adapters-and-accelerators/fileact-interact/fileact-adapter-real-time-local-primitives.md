---
title: FileAct アダプターのリアルタイム ローカル プリミティブ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ef4da4f8-3de2-4d35-8f8a-1e12937e52a1
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ac26a598dad808908b6be1b9fe7ecff3ed1f9f6e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65367184"
---
# <a name="fileact-adapter-real-time-local-primitives"></a>FileAct アダプターのリアルタイム ローカル プリミティブ
ローカル プリミティブでは、2 つのメッセージ、各クライアント SWIFTNet リンク (SNL) とローカル FileAct サブシステム間で交換される必要があります。  
  
 FileAct ローカル プリミティブの図は、次のとおりです。  
  
 ![FileAct ローカル プリミティブ](../../adapters-and-accelerators/fileact-interact/media/67ca0c3b-3c81-401d-87cb-473c68cae63f.gif "67ca0c3b-3c81-401d-87cb-473c68cae63f")  
  
## <a name="get-status-for-a-single-transfer"></a>1 つの転送の状態を取得します。  
 Get Status がプリミティブでは、ローカル永続的なコンテキストから 1 つの転送に関するステータス情報を取得します。  
  
## <a name="subscribe-to-transfer-events"></a>イベントの転送を購読します。  
 イベントのサブスクライブ プリミティブを使用してでは、イベントごとのイベントごとにプログレッシブ転送状態情報を受信する可能性があります。 各ファイルの転送は、ネゴシエーション中にイベント エンドポイントと呼ばれる名前付きエンティティにリンクすることがあります。 イベントのサブスクライブ プリミティブを呼び出すイベント サーバーは、1 つのようなイベント エンドポイント自体にすべてのイベント レポートを指示します。  
  
 イベント、サーバーは、特性 (さまざまなレベルの詳細のほか、さまざまなイベントの種類) にサブスクライブできます。  
  
 イベント、サーバーは、イベントの複数のエンドポイントにサブスクライブするプリミティブ複数回を呼び出す可能性があります。 サーバーの 1 つのみのイベントは、特定の時点で任意のエンドポイントの特定のイベントを定期受信できます。 さらに、イベントのサーバーを呼び出すことができます、プリミティブ型の特性を変更するため、同じイベント エンドポイントを複数回。  
  
## <a name="receive-transfer-events"></a>転送イベントを受信します。  
 受信イベントの転送が進行中の転送に関するイベントの状態情報を処理するプリミティブ。 設定されているイベントのサブスクライブがプリミティブ サブスクリプションの条件に応答します。 このプリミティブは、転送の送信または受信側に実装できます。  
  
## <a name="abort-transfer"></a>転送を中止します。  
 ユーザー アプリケーションは、転送の実行中の中止のプリミティブを使用してを中止可能性があります。 中止プリミティブは、プリミティブを送信側または進行中の転送の受信側のいずれかから実行することがあります。 開始するか、転送を受け入れ、それぞれの側によって独自の側からその転送を保護するアクセス キーとして使用される転送キーを確立するオプションがあります。 進行中の転送の転送キーを確立している場合に停止できません側から中止プリミティブの演習では、転送のキー値を指定せずします。  
  
## <a name="see-also"></a>参照  
 [FileAct アダプターのアーキテクチャ](../../adapters-and-accelerators/fileact-interact/fileact-adapter-architecture.md)   
 [FileAct アダプターのリアルタイム エンド ツー エンド プリミティブ](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-end-to-end-primitives.md)   
 [FileAct アダプターのストア アンド フォワード](../../adapters-and-accelerators/fileact-interact/fileact-adapter-store-and-forward.md)   
 [FileAct アダプターのセキュリティ アーキテクチャ](../../adapters-and-accelerators/fileact-interact/fileact-adapter-security-architecture.md)   
 [FileAct アダプター ファイルおよび転送 Id](../../adapters-and-accelerators/fileact-interact/fileact-adapter-file-and-transfer-identification.md)   
 [FileAct アダプターのサポート情報の転送](../../adapters-and-accelerators/fileact-interact/fileact-adapter-supporting-information-transfer.md)   
 [FileAct アダプターの配信通知](../../adapters-and-accelerators/fileact-interact/fileact-adapter-delivery-notification.md)   
 [FileAct アダプターの状態監視](../../adapters-and-accelerators/fileact-interact/fileact-adapter-status-monitoring.md)