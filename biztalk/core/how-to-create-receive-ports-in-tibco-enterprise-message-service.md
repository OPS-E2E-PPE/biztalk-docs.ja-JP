---
redirect_url: /biztalk/core/creating-tibco-enterprise-message-service-receive-handlers/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 4f579df64543ad21d923c37f6d97251d7655f552
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385456"
---
# <a name="how-to-create-receive-ports-in-tibco-enterprise-message-service"></a>TIBCO Enterprise Message Service での受信ポートの作成方法
受信ポートを作成する次の手順に従います。  
  
### <a name="to-create-a-receive-port"></a>受信ポートを作成するには  
  
1.  BizTalk Server 管理コンソールで  **BizTalk Server 管理**、展開**BizTalk グループ**、展開**アプリケーション**、必要な展開アプリケーション。  
  
2.  右クリック**受信ポート**、 をポイント**新規**、 をクリックし、**一方向受信ポート**します。  
  
3.  **受信ポートのプロパティ**ウィンドウの**全般**ページで、次の操作を行います。  
  
    1.  **名前**フィールドに「`ReceiveFromTIBCOEMS`します。  
  
    2.  **認証**グループ ボックスで、認証の使用時にメッセージを処理する方法を指定します。  
  
    3.  選択、**失敗したメッセージのルーティングを有効にする**チェック ボックスをオンします。  
  
4.  **受信場所**ページで、次の操作を行います。  
  
    1.  **[新規]** をクリックします。  
  
    2.  **受信場所**ウィンドウで、**全般**ページで、入力、**名前**受信場所の。  
  
    3.  **型**ドロップダウン リストで、トランスポートの種類の選択との間、**受信ハンドラー**ドロップダウン一覧でトランスポート アドレスを選択します。  
  
    4.  **受信パイプライン**ドロップダウン リストで、受信パイプラインを選択します。  
  
    5.  **スケジュール**] ページで、[、**開始日**と**終了日**ドキュメントの受信を制限します。  
  
    6.  選択、**有効にするサービス時間帯**チェック ボックスをオンします。  
  
    7.  **[OK]** をクリックします。  
  
5.  **受信マップ**ページで、選択したポートでドキュメントを変換するための受信マップを選択します。  
  
6.  **追跡** ページで、必要なメッセージ本文を追跡および追跡メッセージのプロパティを選択します。  
  
7.  **[OK]** をクリックします。  
  
