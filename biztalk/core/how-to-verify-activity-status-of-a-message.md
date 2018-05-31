---
title: メッセージのアクティビティの状態を確認する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- activities, verifying status
- PeopleSoft Integration Broker
- verifying message status in PeopleSoft
- messages, verifying status
ms.assetid: b8cee6f9-0f65-4228-a87a-3f3aca6182bf
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 872c1a1fcfcc905caf926c8299f56d49178a8448
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22256546"
---
# <a name="how-to-verify-activity-status-of-a-message"></a>メッセージのアクティビティの状態を確認する方法
PeopleSoft HTTP ホストおよび PeopleSoft がイベントを送信ポートを作成するのにには、PeopleSoft Integration Broker を使用します。 メッセージがアクティブになっており、ルーティングされていることを確認するには、次の手順に従います。  
  
### <a name="to-verify-that-a-message-is-active-and-routed-correctly"></a>メッセージがアクティブで正しくルーティングされていることを確認するには  
  
1.  をクリックして**開始**、 をポイント**プログラム**、 をポイント**PeopleSoft Application Name**、し、**アプリケーション デザイナー**です。  
  
2.  **PeopleSoft sign-on**画面で、入力、**ユーザー ID**と**パスワード**、クリックして **[ok]** です。  
  
     ![](../core/media/psadapter-24-task-userpass.gif "PSAdapter_24_Task_UserPass")  
  
     ![](../core/media/psadapter-25-task-emptydesigner.gif "PSAdapter_25_Task_EmptyDesigner")  
  
3.  アプリケーション デザイナーでの**ファイル**] メニューのをポイント**開く**、し、[**メッセージ**です。  
  
     ![](../core/media/psadapter-26-task-filemessage.gif "PSAdapter_26_Task_FileMessage")  
  
4.  **定義を開く**画面で、**名前**フィールドに「 `LOCATION_SYNC`、順にクリック**開く**です。  
  
     ![](../core/media/psadapter-27-task-locationsync.gif "PSAdapter_27_Task_LocationSync")  
  
5.  **選択条件に一致する定義**セクションをダブルクリックして、 **LOCATION_SYNC**プロパティを表示するメッセージ。  
  
     ![](../core/media/psadapter-28-task-locationproperties.gif "PSAdapter_28_Task_LocationProperties")  
  
6.  アプリケーション デザイナーを右クリックして **[location_tbl]** を選択して**メッセージ プロパティ**です。  
  
     ![](../core/media/psadapter-29-task-loctionmenu.gif "PSAdapter_29_Task_LoctionMenu")  
  
7.  **メッセージ プロパティ**画面で、をクリックして、**使用**タブです。  
  
     次のようにを確認し、をクリックして**OK**です。  
  
    1.  **メッセージ:** Active  
  
    2.  **Message Channel:** ENTERPRISE_SETUP  
  
    3.  **既定のバージョン:** VERSION_1  
  
     ![](../core/media/psadapter-30-task-messageuse.gif "PSAdapter_30_Task_MessageUse")  
  
8.  アプリケーション デザイナーを終了します。  
  
     これにより、メッセージの状態がアクティブであること、VERSION_1 が使用されていること、および PeopleSoft の ENTERPRISE_SETUP チャネルにルーティングされていることが確認されました。  
  
9. PeopleSoft アプリケーションと通信するように Integration.Gateway.properties ファイルを構成します。  
  
     プロパティが次のように設定されていることを確認します。  
  
    -   **ig.isc.serverurl:** //server:9000  
  
    -   **ig.isc.userid::** PS の ID  
  
    -   **ig.isc.password::** PS のパスワード  
  
    -   **ig.isc.toolsrel::** 特定のリリース  
  
## <a name="see-also"></a>参照  
 [PeopleSoft HTTP ホストおよびポートを作成します。](../core/creating-a-peoplesoft-http-host-and-port.md)