---
title: Windows SharePoint Services アダプターのパフォーマンス カウンター |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 41583fde-530a-4070-9647-f1ab6273aadf
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1af70299f5e308d1fc40fa6206f0ebfabff22a06
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25973288"
---
# <a name="windows-sharepoint-services-adapter-performance-counters"></a>Windows SharePoint Services アダプターのパフォーマンス カウンター
パフォーマンス カウンターを使用すると、サービスによってサイトまたはシステムで実行されている作業の具体的な側面を監視できます。 パフォーマンス カウンターは、サーバー パフォーマンスに関する問題を特定してトラブルシューティングする際に役立ちます。  
  
 次のパフォーマンス カウンターは各ホスト インスタンスにアクセスできる、 **BizTalk:Windows Sharepoint Services アダプター**パフォーマンス オブジェクト カテゴリ。  
  
|**カテゴリ**|**カウンター**|**Description**|  
|------------------|-----------------|---------------------|  
|BizTalk:Windows Sharepoint Services アダプター|% Receive Message Failures|受信エラーにより、BizTalk Server によって処理されなかった Windows SharePoint Services ファイルの比率。|  
||% Send Message Failures|BizTalk Server が Windows SharePoint Services に送信を試みたメッセージのうち、送信に失敗したメッセージの比率。|  
||% Web Service Call Failures|Windows SharePoint Services アダプター Web サービス呼び出しでエラーが発生した比率。|  
||Total Receive Commit Failures|SharePoint ドキュメントのステータス更新時に発生した Windows SharePoint Services エラーの総数。|  
||Total Receive Message Failures|受信した Windows SharePoint Services ファイルのうち、エラーにより、BizTalk Server によって処理されなかったファイルの総数。|  
||Total Received Messages|Windows SharePoint Services アダプターによって受信された Windows SharePoint Services ファイルの総数。処理に失敗したファイルも含まれます。|  
||Total Send Message Failures|BizTalk Server が Windows SharePoint Services に送信を試みたメッセージのうち、送信に失敗したメッセージの総数。|  
||Total Sent Messages|BizTalk Server が Windows SharePoint Services に送信したメッセージの総数。処理に失敗したファイルも含まれます。|  
||Total Web Service Call Failures|Windows SharePoint Services アダプター Web サービス呼び出しでエラーが発生した回数の合計。|  
||Web Service Calls per Second|Windows SharePoint Services アダプター Web サービス呼び出しでエラーが発生した 1 秒あたりの回数。|  
  
## <a name="to-access-performance-counters"></a>パフォーマンス カウンターにアクセスするには  
 パフォーマンス カウンターにアクセスするには、次の手順を実行します。  
  
#### <a name="if-you-are-using-windows-2008"></a>Windows 2008 を使用している場合  
  
1.  をクリックして**開始**、 をポイント**管理ツール**、順にクリック**パフォーマンス モニター**です。  
  
2.  **パフォーマンス モニター** ] ダイアログ ボックスで、展開**の監視ツールを**[**パフォーマンス モニター**、順にクリック**追加**です。  
  
3.  **カウンターの追加** ダイアログ ボックスから、**使用可能なカウンター**一覧で、展開、 **BizTalk:Windows Sharepoint Services アダプター**パフォーマンス カウンター オブジェクトを選択監視するカウンター  
  
4.  **インスタンスの選択したオブジェクト**一覧をクリックして、選択したカウンターを監視する特定のインスタンスを選択**追加**です。  使用可能なカウンターのすべてのインスタンスを選択するには、次のように選択します。 \<**すべてのインスタンス**\>です。  
  
5.  カウンターを追加すると、をクリックして**OK**です。  
  
     選択したパフォーマンス カウンターが表示されます、**パフォーマンス モニター**画面。