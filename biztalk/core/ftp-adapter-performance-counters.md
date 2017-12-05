---
title: "FTP アダプターのパフォーマンス カウンター |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ca5cbe67-9aa3-4194-816e-fab4eb551c07
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5dad67f24f37f661e26f4cb56895c6bcad6b0782
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="ftp-adapter-performance-counters"></a>FTP アダプターのパフォーマンス カウンター
パフォーマンス カウンターを使用すると、サービスによってサイトまたはシステムで実行されている作業の具体的な側面を監視できます。 パフォーマンス カウンターは、サーバー パフォーマンスに関する問題を特定してトラブルシューティングする際に役立ちます。  
  
 次のパフォーマンス カウンターは各ホスト インスタンスにアクセスできる、 **BizTalk:FTP Receive Adapter**と**BizTalk:FTP Send Adapter**パフォーマンス オブジェクト カテゴリ。  
  
|**カテゴリ**|**カウンター**|**Description**|  
|------------------|-----------------|---------------------|  
|BizTalk:FTP Receive Adapter|Bytes received|FTP 受信アダプターによって受信された合計バイト数。 このカウンターは、FTP 受信アダプターが FTP サーバーからメッセージを完全に読み取った後で増やされます。|  
||Bytes received/Sec|FTP 受信アダプターが 1 秒あたりに受信したバイト数。 このカウンターの対象となるのは、FTP 受信アダプターが FTP サーバーから完全に読み取ったメッセージだけです。|  
||Messages received|FTP 受信アダプターによって受信された合計メッセージ数。 このカウンターは、FTP 受信アダプターが FTP サーバーからメッセージを完全に読み取った後で増やされます。|  
||Messages received/Sec|FTP 受信アダプターが 1 秒あたりに受信したメッセージ数。 このカウンターの対象となるのは、FTP 受信アダプターが FTP サーバーから完全に読み取ったメッセージだけです。|  
|BizTalk:FTP Send Adapter|Bytes sent|FTP 送信アダプターによって送信された合計バイト数。 カウンターは、メッセージが出力先 FTP サーバーに書き込まれた場合にのみ増やされます。|  
||Bytes sent/Sec|FTP 送信アダプターによって送信された 1 秒あたりのバイト数。 カウンターは、送信先 FTP サーバーに書き込まれたメッセージにのみ適用されます。|  
||Messages sent|FTP 送信アダプターによって送信されたメッセージの総数。 カウンターは、メッセージが出力先 FTP サーバーに書き込まれた場合にのみ増やされます。|  
||Messages Sent/sec|FTP 送信アダプターによって送信された 1 秒あたりのメッセージ数。 このカウンターの対象となるのは、出力先 FTP サーバーに書き込まれたメッセージだけです。|  
  
## <a name="to-access-performance-counters"></a>パフォーマンス カウンターにアクセスするには  
 パフォーマンス カウンターにアクセスするには、次の手順を実行します。  
  
#### <a name="if-you-are-using-windows-2008"></a>Windows 2008 を使用している場合  
  
1.  をクリックして**開始**、 をポイント**管理ツール**、順にクリック**パフォーマンス モニター**です。  
  
2.  **パフォーマンス モニター** ] ダイアログ ボックスで、展開**の監視ツールを**[**パフォーマンス モニター**、順にクリック**追加**です。  
  
3.  **カウンターの追加** ダイアログ ボックスから、**使用可能なカウンター**一覧で、展開、 **biztalk:ftp**パフォーマンス カウンター オブジェクトおよび監視するカウンターの選択  
  
4.  **インスタンスの選択したオブジェクト**一覧をクリックして、選択したカウンターを監視する特定のインスタンスを選択**追加**です。  使用可能なカウンターのすべてのインスタンスを選択するには、次のように選択します。 \<**すべてのインスタンス**\>です。  
  
5.  カウンターを追加すると、をクリックして**OK**です。  
  
     選択したパフォーマンス カウンターが表示されます、**パフォーマンス モニター**画面。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server の監視](../core/monitoring-biztalk-server.md)[クラスター化されたホストでアダプター ハンドラーの実行に関する考慮事項](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)