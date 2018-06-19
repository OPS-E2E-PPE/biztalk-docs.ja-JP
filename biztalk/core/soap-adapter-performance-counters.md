---
title: SOAP アダプターのパフォーマンス カウンター |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 40b54d4e-0a2e-483f-982a-97ab9fb59202
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 543c982a68d2a940b4800711d757f4fb159611de
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25974520"
---
# <a name="soap-adapter-performance-counters"></a>SOAP アダプターのパフォーマンス カウンター
パフォーマンス カウンターを使用すると、サービスによってサイトまたはシステムで実行されている作業の具体的な側面を監視できます。 パフォーマンス カウンターは、サーバー パフォーマンスに関する問題を特定してトラブルシューティングする際に役立ちます。  
  
 次のパフォーマンス カウンターは各ホスト インスタンスにアクセスできる、 **BizTalk:SOAP 受信アダプター**と**BizTalk:SOAP 送信アダプター**パフォーマンス オブジェクト カテゴリ。  
  
|**カテゴリ**|**カウンター**|**Description**|  
|------------------|-----------------|---------------------|  
|BizTalk:SOAP 受信アダプター|Messages received|SOAP 受信アダプターが受信したメッセージの総数。 このカウンターは、アダプターが SOAP クライアントから要求メッセージを完全に読み取った後で増やされます。|  
||Messages received/Sec|SOAP 受信アダプターが 1 秒あたりに受信したメッセージ数。 このカウンターの対象となるのは、アダプターが SOAP クライアントから完全に読み取った要求メッセージだけです。|  
|BizTalk:SOAP 送信アダプター|Messages sent|SOAP 送信アダプターによって送信されたメッセージの総数。 カウンターは、メッセージが送信先 URL に到達した場合にのみ増やされます。|  
||Messages Sent/sec|SOAP 送信アダプターによって送信された 1 秒あたりのメッセージ数。 送信先 URL に到達したメッセージのみが対象となります。|  
  
## <a name="to-access-performance-counters"></a>パフォーマンス カウンターにアクセスするには  
 パフォーマンス カウンターにアクセスするには、次の手順を実行します。  
  
#### <a name="if-you-are-using-windows-server-2008"></a>Windows Server 2008 を使用している場合  
  
1.  をクリックして**開始**、 をポイント**管理ツール**、順にクリック**パフォーマンス モニター**です。  
  
2.  **パフォーマンス モニター** ] ダイアログ ボックスで、展開**の監視ツールを**[**パフォーマンス モニター**、順にクリック**追加**です。  
  
3.  **カウンターの追加** ダイアログ ボックスから、**使用可能なカウンター**一覧で、展開、 **BizTalk:SOAP**パフォーマンス カウンター オブジェクトおよび監視するカウンターの選択  
  
4.  **インスタンスの選択したオブジェクト**一覧をクリックして、選択したカウンターを監視する特定のインスタンスを選択**追加**です。 使用可能なカウンターのすべてのインスタンスを選択するには、次のように選択します。 \<**すべてのインスタンス**\>です。  
  
5.  カウンターを追加すると、をクリックして**OK**です。  
  
     選択したパフォーマンス カウンターが表示されます、**パフォーマンス モニター**画面。