---
title: '手順 2: Contoso 3 a 2 Price and Availability クエリ応答のシナリオが BizTalk エクスプ ローラーのポートの作成 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- private process tutorial, creating ports
ms.assetid: e0b12a96-e799-47ac-8293-7de10662bdf0
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 64101a31b1d1ea9c7af00471c5d764a1d8cfe598
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22210146"
---
# <a name="step-2-creating-ports-for-the-contoso-3a2-price-and-availability-queryresponse-scenario"></a>手順 2: Contoso 3 a 2 Price and Availability クエリ/応答シナリオ用のポートの作成
この手順では、BizTalk Server によって提供される SQL アダプターを使用して送信ポートを作成します。 この SQL ポートを使用して、Contoso の ERP システムとの間で 3A2 Price and Availability 応答を送受信します。  
  
### <a name="to-configure-a-send-port-using-the-sql-adapter"></a>SQL アダプターを使用して送信ポートを構成するには  
  
1.  Visual Studio での**ビュー**  メニューのをクリックして**BizTalk エクスプ ローラー**です。  
  
2.  BizTalk エクスプ ローラーで右クリック**送信ポート**、クリックして**送信ポートの追加**です。  
  
3.  新しい送信ポートを作成 ダイアログ ボックスで、次のように選択します。**静的な送信請求-応答ポート**クリックしてドロップダウン リストから**OK**です。  
  
4.  静的な送信請求-応答送信ポートのプロパティ ダイアログ ボックスで、**名前**ボックスに、入力**3 a2sqlreqresponsesendport**です。  
  
5.  [プロパティ] ウィンドウで、**全般**選択見出し、 **SQL**として、**トランスポートの種類**です。  
  
6.  **アドレス URI**ボックスで、省略記号ボタンをクリックして (**.**).  
  
7.  SQL トランスポートのプロパティ ダイアログ ボックスで、省略記号ボタンをクリックします (**.**) の横に、**接続文字列**ボックス。  
  
8.  [データ リンク プロパティ] ダイアログ ボックスで、**を選択するか、サーバー名を入力**ボックスに、入力**localhost**です。  
  
9. 選択**Windows NT 統合セキュリティ**です。  
  
10. **サーバー上のデータベースを選択**ボックスで、選択**Contoso**、順にクリック**OK**です。  
  
11. SQL トランスポートのプロパティ ダイアログ ボックスで、**ドキュメント Target Namespace**ボックスに、入力**http://Contoso.com/Price**です。  
  
12. **応答ドキュメントのルート要素名**ボックスに、入力 **[rootpriceresponse]**、順にクリック**OK**です。  
  
13. 静的な送信請求-応答送信ポートのプロパティ ダイアログ ボックスの左側のウィンドウでをクリックして**送信**です。  
  
14. 静的な送信請求-応答送信ポートのプロパティ-構成-送信-全般 ダイアログ ボックスで、**送信パイプライン**ボックスで、 **microsoft.biztalk.defaultpipelines.xmltransmit**です。  
  
15. **受信パイプライン**ボックスで、 **Microsoft.BizTalk.DefaultPipelines.XMLReceive**、順にクリック**OK**です。  
  
16. BizTalk エクスプ ローラーで右クリック**3 a2sqlreqresponsesendport**、クリックして**Enlist**です。 もう一度右クリックし、をクリックして**開始**です。  
  
## <a name="see-also"></a>参照  
 [作成と Contoso のプライベート プロセスの変更](creating-and-modifying-the-private-process-for-contoso.md)