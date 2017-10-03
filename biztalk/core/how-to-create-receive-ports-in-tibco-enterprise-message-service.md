---
title: "作成する方法には、TIBCO Enterprise Message Service 受信ポートを |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- receive ports, creating
- creating receive ports
ms.assetid: ca623c81-3dd3-4824-a586-28055d01fe9f
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a85fad9dc0936baa0c3f584581d5483a30fedf6f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-receive-ports-in-tibco-enterprise-message-service"></a>TIBCO Enterprise Message Service での受信ポートの作成方法
受信ポートを作成するには、次の手順を実行します。  
  
### <a name="to-create-a-receive-port"></a>受信ポートを作成するには  
  
1.  BizTalk Server 管理コンソールで、展開**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**アプリケーション**、し、必要な展開アプリケーション。  
  
2.  右クリック**受信ポート**、 をポイント**新規**、クリックして**一方向受信ポート**です。  
  
3.  **受信ポートのプロパティ** ウィンドウで、**全般** ページで、次の操作します。  
  
    1.  **名前**フィールドに「`ReceiveFromTIBCOEMS`です。  
  
    2.  **認証**グループ ボックスで、認証の使用時のメッセージの処理方法を指定します。  
  
    3.  選択、**失敗したメッセージの有効化のルーティングを**チェック ボックスをオンします。  
  
4.  **受信場所** ページで、次の操作します。  
  
    1.  **[新規作成]**をクリックします。  
  
    2.  **受信場所**ウィンドウで、**全般** ページで、入力、**名前**受信場所のです。  
  
    3.  **型**ドロップダウン一覧で、トランスポートの種類を選択してから、**受信ハンドラー**ドロップダウン一覧で、トランスポート アドレスを選択します。  
  
    4.  **受信パイプライン**ドロップダウン リストで、受信パイプラインを選択します。  
  
    5.  **スケジュール**] ページで、[、**開始日**と**終了日**ドキュメントの受信を制限します。  
  
    6.  選択、**有効にするサービス時間帯**チェック ボックスをオンします。  
  
    7.  **[OK]**をクリックします。  
  
5.  **受信マップ**ページで、選択したポートでドキュメントを変換するための受信マップを選択します。  
  
6.  **追跡** ページで、必要なメッセージ本文の追跡と追跡メッセージのプロパティを選択します。  
  
7.  **[OK]**をクリックします。  
  
## <a name="see-also"></a>参照  
 [TIBCO Enterprise Message Service トランスポート プロパティの設定、受信ポート](../core/set-tibco-enterprise-message-service-transport-properties-for-the-receive-port.md)