---
title: "BizTalk adapter for JD Edwards OneWorld のフロー制御 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- connection pooling
- control flows
- apartment threading
- apartment threading, business functions
ms.assetid: 1ec865d0-2257-453b-9230-1f3787ebac38
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0fc5a8be6516b61c4049242952967ce939513e9c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="control-flow-in-biztalk-adapter-for-jd-edwards-oneworld"></a>BizTalk Adapter for JD Edwards OneWorld の制御フロー
このトピックでは、Microsoft BizTalk Adapter for JD Edwards OneWorld のデザイン時および実行時の制御フローについて説明します。  
  
## <a name="design-time-flow"></a>デザイン時のフロー  
 ([トランスポートのプロパティ] ダイアログ ボックスの資格情報およびシステム情報を使用して) アダプターが開くときに、JD Edwards OneWorld アプリケーションのビジネス関数のインスタンスが 1 つ以上作成およびプールされます。 アダプター ウィザードで名前空間を参照すると、ビジネス関数の一覧が表示されます。 ビジネス関数をクリックすると、論理メソッドがメソッドの署名と共に表示されます。  
  
## <a name="run-time-flow"></a>実行時のフロー  
 JD Edwards OneWorld のビジネス関数のインスタンスが、各スレッドに対して作成およびプールされます。 メソッドの呼び出しがビジネス サービスに対して送信されると、JD Edwards OneWorld アプリケーションのビジネス関数を使用して、そのメソッドのメタデータが読み出されます。ただし、そのメソッドのメタデータが既にキャッシュされている場合、ビジネス関数はキャッシュされた情報を使用し、適切なメソッドを呼び出します。 実行時には、JD Edwards OneWorld インターフェイス レイヤーが動的に作成されます。 BizTalk Adapter for JD Edwards OneWorld は、インターフェイス レイヤーを通じて呼び出しとデータ変換をサポートします。  
  
 BizTalk Adapter for JD Edwards OneWorld は、JD Edwards OneWorld アプリケーションのメソッド シグネチャにおけるインターフェイスの説明をマップし、BizTalk Server がこれらのインターフェイスの説明と対話できるようにします。  
  
 アダプターは、次の 1 つ以上の形式でアプリケーションの機能を拡張することにより、社内のアプリケーションが JD Edwards OneWorld アプリケーションと対話できるようにします。  
  
-   ネイティブなデータ形式  
  
-   手順  
  
-   メソッド  
  
-   メッセージ  
  
-   [プロパティ]  
  
-   アプリケーション インターフェイス  
  
 BizTalk Adapter for JD Edwards OneWorld は、実行時に、JD Edwards OneWorld と対話するクライアント アプリケーションのアプリケーション インターフェイスの説明を作成します。 アダプターは、必要に応じてビジネス オブジェクトを作成、削除、および呼び出し、アプリケーションで計算を実行して直接メソッドを呼び出すことができます。 JD Edwards OneWorld へのすべての呼び出しは同期呼び出しです。 アダプターは、BizTalk Server から XML メッセージを受信し、SOAP エンベロープにメッセージを埋め込み、SOAP メッセージから呼び出しのデータを Java タイプに変換します。  
  
 この返信は、次のような同様の処理に従って送信されます。  
  
1.  Java タイプが SOAP メッセージに変換されます。  
  
2.  SOAP メッセージが XML メッセージに変換されます。  
  
3.  XML メッセージが BizTalk Server に送信され、さらに処理されます。  
  
### <a name="apartment-threading-of-business-functions"></a>ビジネス関数のアパートメント スレッド  
 JD Edwards OneWorld のビジネス関数と任意のインスタンスは、その作成元または取得元のスレッドのみで使用できます。 これは呼ば*アパートメント スレッド*です。 BizTalk Adapter for JD Edwards OneWorld の接続プール フレームワークは、使用できる接続のプールを管理します。  
  
### <a name="connection-pooling"></a>接続のプール  
 接続プールは、サーバー システムへの接続を開いたままにし、呼び出し後に毎回閉じるのではなく再利用することにより、呼び出しのパフォーマンスを向上させます。 BizTalk Adapter for JD Edwards OneWorld を使用すると、特定のログオン ID 内で接続をプールする一方で、すべてのプールにわたる合計接続数の厳密な制御を維持できます。  
  
 新しいビジネス関数のインスタンスは作成元のスレッドを使用します。また、インスタンスは操作後に毎回破棄されます。 JD Edwards OneWorld のビジネス関数の呼び出しは、すべてステートレスです。ただし、アダプターにより、操作中は正しいスレッドでビジネス関数が使用されます。  
  
## <a name="see-also"></a>参照  
 [アプリケーションの開発](../core/developing-applications3.md)   
 [計画とアーキテクチャ](../core/planning-and-architecture17.md)