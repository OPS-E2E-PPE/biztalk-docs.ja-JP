---
title: POP3 アダプターのパフォーマンス カウンター |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f799175e-e9e7-4937-93bd-aaec1c43b75a
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 87aaff170c75395b96b8d8d36d6efec6693e38ba
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394920"
---
# <a name="pop3-adapter-performance-counters"></a>POP3 アダプターのパフォーマンス カウンター
パフォーマンス カウンターを使用して、サービスによってサイトまたはシステムで実行される作業の具体的な側面を監視できます。 パフォーマンス カウンターは、サーバー パフォーマンスに関する問題を特定してトラブルシューティングする際に役立ちます。  
  
 次のパフォーマンス カウンターは各ホスト インスタンスにアクセスできますが、 **BizTalk:POP3 Receive Adapter**パフォーマンス オブジェクト カテゴリ。  
  
|**カテゴリ**|**カウンター**|**[説明]**|  
|------------------|-----------------|---------------------|  
|BizTalk:POP3 受信アダプター|Active sessions|同時に、POP3 アダプターを管理しています。 開いている POP3 接続の数。|  
||受信したバイト数|POP3 アダプターがメール サーバーからダウンロードしたバイトの合計数。|  
||バイトの受信/秒|POP3 アダプターが 1 秒あたりのメール サーバーからダウンロードしたバイト数。|  
||受信したメッセージ|POP3 アダプターがメール サーバーからダウンロードした電子メール メッセージの合計数。|  
||メッセージの受信/秒|POP3 アダプターが 1 秒あたりにメール サーバーからダウンロードした電子メール メッセージの数。|  
  
## <a name="to-access-performance-counters"></a>パフォーマンス カウンターにアクセスするには  
 POP3 アダプターのパフォーマンス カウンターにアクセスする次の手順に従います。  
  
#### <a name="if-you-are-using-windows-2008"></a>Windows 2008 を使用している場合  
  
1.  クリックして**開始**、 をポイント**管理ツール**、順にクリックします**パフォーマンス モニター**します。  
  
2.  **パフォーマンス モニター**  ダイアログ ボックスで、展開**監視ツール**を選択します**パフォーマンス モニター**、 をクリックし、**追加**。  
  
3.  **カウンターの追加**] ダイアログ ボックスから、**使用可能なカウンター**一覧で、展開、 **[BizTalk:POP3 Receive Adapter**パフォーマンス カウンター オブジェクトとカウンターを選択します監視  
  
4.  **インスタンスの選択したオブジェクト**一覧をクリックして、選択したカウンターを監視する特定のインスタンスを選択**追加**します。  使用可能なカウンターのインスタンスすべてを選択する\<**すべてのインスタンス**\>します。  
  
5.  カウンターを追加すると、次のようにクリックします。 **OK**します。  
  
     選択したパフォーマンス カウンターが表示される、**パフォーマンス モニター**画面。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server の監視](../core/monitoring-biztalk-server.md)  
 [POP3 アダプターでのマルチパート メッセージの処理](../core/processing-multi-part-messages-with-the-pop3-adapter.md)   
 [クラスター化されたホストでのアダプター ハンドラーの実行に関する注意点](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)