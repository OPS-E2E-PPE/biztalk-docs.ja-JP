---
title: "POP3 アダプターのパフォーマンス カウンター |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f799175e-e9e7-4937-93bd-aaec1c43b75a
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b0f48879fcc00041ce0fa1cf842a066c6da59804
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="pop3-adapter-performance-counters"></a>POP3 アダプターのパフォーマンス カウンター
パフォーマンス カウンターを使用すると、サービスによってサイトまたはシステムで実行されている作業の具体的な側面を監視できます。 パフォーマンス カウンターは、サーバー パフォーマンスに関する問題を特定してトラブルシューティングする際に役立ちます。  
  
 次のパフォーマンス カウンターは各ホスト インスタンスにアクセスできる、 **BizTalk:POP3 Receive Adapter**パフォーマンス オブジェクト カテゴリ。  
  
|**カテゴリ**|**カウンター**|**Description**|  
|------------------|-----------------|---------------------|  
|BizTalk:POP3 Receive Adapter|Active sessions|POP3 アダプターが同時に管理している確立済みの POP3 接続数。|  
||Bytes received|POP3 アダプターがメール サーバーからダウンロードした合計バイト数。|  
||Bytes receive/Sec|POP3 アダプターがメール サーバーからダウンロードした 1 秒あたりのバイト数。|  
||Messages received|POP3 アダプターがメール サーバーからダウンロードした電子メール メッセージの総数。|  
||Messages received/Sec|POP3 アダプターがメール サーバーからダウンロードした 1 秒あたりの電子メール メッセージ数。|  
  
## <a name="to-access-performance-counters"></a>パフォーマンス カウンターにアクセスするには  
 POP3 アダプターのパフォーマンス カウンターにアクセスするには、次の手順を実行します。  
  
#### <a name="if-you-are-using-windows-2008"></a>Windows 2008 を使用している場合  
  
1.  をクリックして**開始**、 をポイント**管理ツール**、順にクリック**パフォーマンス モニター**です。  
  
2.  **パフォーマンス モニター** ] ダイアログ ボックスで、展開**の監視ツールを**[**パフォーマンス モニター**、順にクリック**追加**です。  
  
3.  **カウンターの追加**] ダイアログ ボックスから、**使用可能なカウンター**一覧で、展開、 **[BizTalk:POP3 Receive Adapter**パフォーマンス カウンター オブジェクトとカウンターを選択します。監視  
  
4.  **インスタンスの選択したオブジェクト**一覧をクリックして、選択したカウンターを監視する特定のインスタンスを選択**追加**です。  使用可能なカウンターのすべてのインスタンスを選択するには、次のように選択します。 \<**すべてのインスタンス**>。  
  
5.  カウンターを追加すると、をクリックして**OK**です。  
  
     選択したパフォーマンス カウンターが表示されます、**パフォーマンス モニター**画面。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server の監視](../core/monitoring-biztalk-server.md)  
 [POP3 アダプタでのマルチパート メッセージの処理](../core/processing-multi-part-messages-with-the-pop3-adapter.md)   
 [クラスター化されたホストでアダプター ハンドラーの実行に関する考慮事項](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)