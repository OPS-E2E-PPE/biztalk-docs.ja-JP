---
title: MSMQ アダプターのパフォーマンス カウンター |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ab8b0342-c6c2-4113-ae54-359df28e5d30
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: be7580ae6551fca18ee0a3b9b14b194006efd62e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25971848"
---
# <a name="msmq-adapter-performance-counters"></a>MSMQ アダプターのパフォーマンス カウンター
パフォーマンス カウンターを使用すると、サービスによってサイトまたはシステムで実行されている作業の具体的な側面を監視できます。 パフォーマンス カウンターは、サーバー パフォーマンスに関する問題を特定してトラブルシューティングする際に役立ちます。  
  
 次のパフォーマンス カウンターは各ホスト インスタンスにアクセスできる、 **BizTalk:MSMQ Receive Adapter**と**BizTalk:MSMQ Send Adapter**パフォーマンス オブジェクト カテゴリ。  
  
|**カテゴリ**|**カウンター**|**Description**|  
|------------------|-----------------|---------------------|  
|BizTalk:MSMQ Receive Adapter|Bytes received|MSMQ 受信アダプターによって受信された合計バイト数。 このカウンターは、MSMQ 受信アダプターが送信元のキューからメッセージを完全に読み取った後で増やされます。|  
||Bytes received/Sec|MSMQ 受信アダプターが 1 秒あたりに受信したバイト数。 このカウンターの対象となるのは、MSMQ 受信アダプターが送信元のキューから完全に読み取ったメッセージだけです。|  
||Messages received|MSMQ 受信アダプターが受信したメッセージの総数。 このカウンターは、MSMQ 受信アダプターが送信元のキューからメッセージを完全に読み取った後で増やされます。|  
||Messages received/Sec|MSMQ 受信アダプターが 1 秒あたりに受信したメッセージ数。 このカウンターの対象となるのは、MSMQ 受信アダプターが送信元のキューから完全に読み取ったメッセージだけです。|  
|BizTalk:MSMQ Send Adapter|Bytes sent|MSMQ 送信アダプターによって送信された合計バイト数。 カウンターは、メッセージが送信先キューに到達した場合にのみ増やされます。|  
||Bytes sent/Sec|MSMQ 送信アダプターによって送信された 1 秒あたりのバイト数。 このカウンターの対象となるのは、送信先キューに到達したメッセージだけです。|  
||Messages sent|MSMQ 送信アダプターによって送信されたメッセージの総数。 カウンターは、メッセージが送信先キューに到達した場合にのみ増やされます。|  
||Messages Sent/sec|MSMQ 送信アダプターによって送信された 1 秒あたりのメッセージ数。 このカウンターの対象となるのは、送信先キューに到達したメッセージだけです。|  
  
## <a name="to-access-performance-counters"></a>パフォーマンス カウンターにアクセスするには  
 パフォーマンス カウンターにアクセスするには、次の手順を実行します。  
  
#### <a name="if-you-are-using-windows-2008"></a>Windows 2008 を使用している場合  
  
1.  をクリックして**開始**、 をポイント**管理ツール**、順にクリック**パフォーマンス モニター**です。  
  
2.  **パフォーマンス モニター** ] ダイアログ ボックスで、展開**の監視ツールを**[**パフォーマンス モニター**、順にクリック**追加**です。  
  
3.  **カウンターの追加** ダイアログ ボックスから、**使用可能なカウンター**一覧で、展開、 **biztalk:msmq**パフォーマンス カウンター オブジェクトおよび監視するカウンターの選択  
  
4.  **インスタンスの選択したオブジェクト**一覧をクリックして、選択したカウンターを監視する特定のインスタンスを選択**追加**です。  使用可能なカウンターのすべてのインスタンスを選択するには、次のように選択します。 \<**すべてのインスタンス**\>です。  
  
5.  カウンターを追加すると、をクリックして**OK**です。  
  
     選択したパフォーマンス カウンターが表示されます、**パフォーマンス モニター**画面。  
  
## <a name="see-also"></a>参照  
 [MSMQ での LoadGen 2007 の使用](../core/using-loadgen-2007-with-msmq.md)   
 [MSMQ アダプターのパフォーマンスの最適化](../core/optimizing-performance-of-the-msmq-adapter.md)