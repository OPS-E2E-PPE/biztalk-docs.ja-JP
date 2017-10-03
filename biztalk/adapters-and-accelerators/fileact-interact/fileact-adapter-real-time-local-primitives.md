---
title: "FileAct アダプターのリアルタイム ローカル プリミティブ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ef4da4f8-3de2-4d35-8f8a-1e12937e52a1
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bcc0f1d093d56b8cd4580ef068007d02aab6346f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="fileact-adapter-real-time-local-primitives"></a>FileAct アダプターのリアルタイム ローカル プリミティブ
ローカル プリミティブには、2 つのメッセージ、各クライアント SWIFTNet リンク (SNL) とローカル FileAct サブシステム間で交換されるが含まれます。  
  
 FileAct ローカル プリミティブを次の図に示します。  
  
 ![FileAct ローカル プリミティブ](../../adapters-and-accelerators/fileact-interact/media/67ca0c3b-3c81-401d-87cb-473c68cae63f.gif "67ca0c3b-3c81-401d-87cb-473c68cae63f")  
  
## <a name="get-status-for-a-single-transfer"></a>1 つの転送状態を取得します。  
 プリミティブの取得状態は、ローカルの永続的なコンテキストから 1 つの転送に関する状態情報を取得します。  
  
## <a name="subscribe-to-transfer-events"></a>サブスクライブするイベントを転送するには  
 イベントのサブスクライブ プリミティブを使用して、イベントごとにプログレッシブ転送状態情報を受信する可能性があります。 各ファイルの転送は、ネゴシエーション中にイベント エンドポイントと呼ばれる名前付きエンティティにリンクすることがあります。 プリミティブをサブスクライブするイベントを起動するイベント サーバーは、1 つそのようなイベント エンドポイントに対して自体へのすべてのイベント レポートを出力します。  
  
 イベント サーバーは、特性 (詳細、および別のイベントの種類にはさまざまなレベル) にサブスクライブできます。  
  
 イベント サーバーは、イベントの複数のエンドポイントをサブスクライブするプリミティブを複数回を呼び出す可能性があります。 1 つのみのイベントのサーバーは、特定の時点で任意の特定のイベントのエンドポイントにサブスクライブ可能性があります。 さらに、イベント server 呼び出すことができます、プリミティブ特性を変更するため、同じイベント エンドポイントを複数回です。  
  
## <a name="receive-transfer-events"></a>転送イベントを受け取る  
 受信転送イベントが転送中の関連イベントのステータス情報を処理するプリミティブ型。 この設定は、サブスクライブ イベント プリミティブ、サブスクリプションの条件に応答します。 このプリミティブは、転送の送信側または受信側で実装できます。  
  
## <a name="abort-transfer"></a>転送を中止します。  
 ユーザーのアプリケーションは、転送の実行中の中止プリミティブを使用してを中止可能性があります。 中止プリミティブは、送信側または進行中の転送の受信側のいずれかからを実行することがありますプリミティブです。 開始するか、転送を受け入れ、独自の側からその転送を保護するアクセス キーとして機能する転送キーを確立するためのオプションが含まれています。 進行中の転送の転送キーが確立されると場合に、停止できませんされた側から中止プリミティブの演習で転送キーの値を指定せずします。  
  
## <a name="see-also"></a>参照  
 [FileAct アダプターのアーキテクチャ](../../adapters-and-accelerators/fileact-interact/fileact-adapter-architecture.md)   
 [FileAct アダプター リアルタイム エンド ツー エンド プリミティブ](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-end-to-end-primitives.md)   
 [FileAct アダプター ストア アンド フォワード](../../adapters-and-accelerators/fileact-interact/fileact-adapter-store-and-forward.md)   
 [FileAct アダプターのセキュリティ アーキテクチャ](../../adapters-and-accelerators/fileact-interact/fileact-adapter-security-architecture.md)   
 [FileAct アダプター ファイルおよび転送の識別](../../adapters-and-accelerators/fileact-interact/fileact-adapter-file-and-transfer-identification.md)   
 [FileAct アダプターをサポートする情報の転送](../../adapters-and-accelerators/fileact-interact/fileact-adapter-supporting-information-transfer.md)   
 [FileAct アダプター配信通知](../../adapters-and-accelerators/fileact-interact/fileact-adapter-delivery-notification.md)   
 [FileAct アダプター状態の監視](../../adapters-and-accelerators/fileact-interact/fileact-adapter-status-monitoring.md)