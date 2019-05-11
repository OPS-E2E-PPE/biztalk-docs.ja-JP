---
title: Windows SharePoint Services アダプターのパフォーマンス カウンター |Microsoft Docs
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
ms.openlocfilehash: 1346bc558bd9881d9eb925856f79277a831c2665
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65240365"
---
# <a name="windows-sharepoint-services-adapter-performance-counters"></a>Windows SharePoint Services アダプターのパフォーマンス カウンター
パフォーマンス カウンターを使用して、サービスによってサイトまたはシステムで実行される作業の具体的な側面を監視できます。 パフォーマンス カウンターは、サーバー パフォーマンスに関する問題を特定してトラブルシューティングする際に役立ちます。  
  
 次のパフォーマンス カウンターは各ホスト インスタンスにアクセスできますが、 **BizTalk:Windows Sharepoint Services アダプター**パフォーマンス オブジェクト カテゴリ。  
  
|**カテゴリ**|**カウンター**|**[説明]**|  
|------------------|-----------------|---------------------|  
|BizTalk:Windows Sharepoint Services アダプター|% は、メッセージのエラーを受け取ります。|受信エラーにより、BizTalk Server で処理されていない Windows SharePoint Services ファイルの割合。|  
||送信メッセージのエラー %|BizTalk Server-が Windows SharePoint Services に送信しようとした失敗したメッセージの割合。|  
||%Web サービスの呼び出しエラー|失敗した Windows SharePoint Services アダプター Web サービス呼び出しの割合。|  
||合計は、コミット エラーが表示されます。|SharePoint のドキュメントの状態を更新するときに発生した Windows SharePoint Services エラーの合計数。|  
||合計受信メッセージのエラー|エラーにより BizTalk Server で処理されていない Windows SharePoint Services ファイルの合計数を受信します。|  
||受信したメッセージの総数|処理に失敗したファイルを含む、Windows SharePoint Services アダプターによって受信された Windows SharePoint Services ファイルの合計数。|  
||メッセージの合計送信エラー|BizTalk Server が、Windows SharePoint Services に送信しようとしています。 失敗したメッセージの合計数。|  
||送信されたメッセージの合計|BizTalk Server が処理に失敗したファイルを含む、Windows SharePoint Services に送信されるメッセージの合計数。|  
||合計の Web サービスの呼び出しエラー|失敗した Windows SharePoint Services アダプター Web サービス呼び出しの合計数。|  
||1 秒あたりの web サービス呼び出し|1 秒あたりの呼び出しを Windows SharePoint Services アダプター Web サービスの数。|  
  
## <a name="to-access-performance-counters"></a>パフォーマンス カウンターにアクセスするには  
 パフォーマンス カウンターにアクセスするのにには、次の手順を使用します。  
  
#### <a name="if-you-are-using-windows-2008"></a>Windows 2008 を使用している場合  
  
1.  クリックして**開始**、 をポイント**管理ツール**、順にクリックします**パフォーマンス モニター**します。  
  
2.  **パフォーマンス モニター**  ダイアログ ボックスで、展開**監視ツール**を選択します**パフォーマンス モニター**、 をクリックし、**追加**。  
  
3.  **カウンターの追加** ダイアログ ボックスから、**使用可能なカウンター**一覧で、展開、 **BizTalk:Windows Sharepoint Services アダプター**パフォーマンス カウンター オブジェクトを選択監視するカウンター  
  
4.  **インスタンスの選択したオブジェクト**一覧をクリックして、選択したカウンターを監視する特定のインスタンスを選択**追加**します。  使用可能なカウンターのインスタンスすべてを選択する\<**すべてのインスタンス**\>します。  
  
5.  カウンターを追加すると、次のようにクリックします。 **OK**します。  
  
     選択したパフォーマンス カウンターが表示される、**パフォーマンス モニター**画面。