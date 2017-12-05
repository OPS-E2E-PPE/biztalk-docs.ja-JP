---
title: "HTTP アダプターのパフォーマンス カウンター |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d85473f1-1d67-4990-8d2f-fc7fe0e80108
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ff9fcc2530484abd7c5bdbf1997e3d294afdb3dc
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="http-adapter-performance-counters"></a>HTTP アダプターのパフォーマンス カウンター
パフォーマンス カウンターを使用すると、サービスによってサイトまたはシステムで実行されている作業の具体的な側面を監視できます。 パフォーマンス カウンターは、サーバー パフォーマンスに関する問題を特定してトラブルシューティングする際に役立ちます。  
  
 次のパフォーマンス カウンターは各ホスト インスタンスにアクセスできる、 **BizTalk:HTTP Receive Adapter**と**BizTalk:HTTP Send Adapter**パフォーマンス オブジェクト カテゴリ。  
  
|**カテゴリ**|**カウンター**|**Description**|  
|------------------|-----------------|---------------------|  
|BizTalk:HTTP Receive Adapter|Memory queue size|HTTP 受信アダプターの内部メモリ キューにある着信メッセージの数。|  
||Message received|HTTP 受信アダプターが受信した HTTP 要求の総数。 このカウンターは、HTTP 受信アダプターが HTTP クライアントから要求メッセージを完全に読み取った後で増やされます。|  
||Messages received/Sec|HTTP 受信アダプターが 1 秒あたりに受信した HTTP 要求の数。 このカウンターの対象となるのは、HTTP 受信アダプターが HTTP クライアントから完全に読み取った要求メッセージだけです。|  
||Messages sent|HTTP 受信アダプターによって送信された HTTP 応答の総数。 カウンターは、応答メッセージが HTTP クライアントに正常に送信された場合にのみ増やされます。|  
||Messages Sent/sec|HTTP 受信アダプターが 1 秒あたりに送信した HTTP 応答の数。 このカウンターの対象となるのは、HTTP クライアントに正常に送信された応答メッセージだけです。|  
||Time to add message to batch|メッセージが IIS により HTTP 受信アダプターに渡されてから、バッチに追加されるまでの平均時間。|  
||Time to build batch|HTTP 受信アダプターがメッセージ バッチの作成に要した平均時間。|  
|BizTalk:HTTP Send Adapter|Memory queue size|HTTP 送信アダプターの内部メモリ キューにある送信メッセージの数。|  
||Messages received|HTTP 送信アダプターが受信した HTTP 応答メッセージの総数。 カウンターは、HTTP 送信アダプターが HTTP サーバーから応答メッセージを完全に読み取った後で増やされます。|  
||Message received/Sec|HTTP 送信アダプターが 1 秒あたりに受信した HTTP 応答の数。 このカウンターの対象となるのは、HTTP 送信アダプターが HTTP サーバーから完全に読み取った応答メッセージだけです。|  
||Messages sent|HTTP 送信アダプターによって送信された HTTP 要求の総数。 カウンターは、要求メッセージが送信先 URL に到達した場合にのみ増やされます。|  
||Messages Sent/sec|HTTP 送信アダプターが 1 秒あたりに送信した HTTP 要求の数。 このカウンターの対象となるのは、送信先 URL に到達した要求だけです。|  
  
## <a name="to-access-performance-counters"></a>パフォーマンス カウンターにアクセスするには  
 パフォーマンス カウンターにアクセスするには、次の手順を実行します。  
  
#### <a name="if-you-are-using-windows-2008"></a>Windows 2008 を使用している場合  
  
1.  をクリックして**開始**、 をポイント**管理ツール**、順にクリック**パフォーマンス モニター**です。  
  
2.  **パフォーマンス モニター** ] ダイアログ ボックスで、展開**の監視ツールを**[**パフォーマンス モニター**、順にクリック**追加**です。  
  
3.  **カウンターの追加** ダイアログ ボックスから、**使用可能なカウンター**一覧で、展開、 **biztalk:http**パフォーマンス カウンター オブジェクトおよび監視するカウンターの選択  
  
4.  **インスタンスの選択したオブジェクト**一覧をクリックして、選択したカウンターを監視する特定のインスタンスを選択**追加**です。  使用可能なカウンターのすべてのインスタンスを選択するには、次のように選択します。 \<**すべてのインスタンス**\>です。  
  
5.  カウンターを追加すると、をクリックして**OK**です。  
  
     選択したパフォーマンス カウンターが表示されます、**パフォーマンス モニター**画面。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server の監視](../core/monitoring-biztalk-server.md)   
 [HTTP アダプタの構成およびチューニング パラメータ](../core/http-adapter-configuration-and-tuning-parameters.md)   
 [クラスター化されたホストでのアダプター ハンドラーの実行に関する注意点](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)