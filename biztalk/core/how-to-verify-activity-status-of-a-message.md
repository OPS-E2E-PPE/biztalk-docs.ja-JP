---
title: メッセージのアクティビティの状態を確認する方法 |Microsoft Docs
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
ms.openlocfilehash: 8af3a77b9bb169e394571444c7eb7e3984f7f7c3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013043"
---
# <a name="how-to-verify-activity-status-of-a-message"></a>メッセージのアクティビティの状態を確認する方法
PeopleSoft Integration Broker を使用して、PeopleSoft HTTP ホストおよび PeopleSoft がイベントを送信ポートを作成します。 メッセージがアクティブになっており、ルーティングされていることを確認するには、次の手順に従います。  
  
### <a name="to-verify-that-a-message-is-active-and-routed-correctly"></a>メッセージがアクティブで正しくルーティングされていることを確認するには  
  
1. をクリックして**開始**、 をポイント**プログラム**、 をポイント**PeopleSoft Application Name**、し、**アプリケーション デザイナー**します。  
  
2. **PeopleSoft sign-on**画面で、入力、**ユーザー ID**と**パスワード**、順にクリックします**OK**。  
  
    ![](../core/media/psadapter-24-task-userpass.gif "PSAdapter_24_Task_UserPass")  
  
    ![](../core/media/psadapter-25-task-emptydesigner.gif "PSAdapter_25_Task_EmptyDesigner")  
  
3. アプリケーション デザイナーでの**ファイル**メニューで、**オープン**、し、**メッセージ**します。  
  
    ![](../core/media/psadapter-26-task-filemessage.gif "PSAdapter_26_Task_FileMessage")  
  
4. **定義を開く**画面で、**名**フィールドに、入力`LOCATION_SYNC`、順にクリックします**オープン**します。  
  
    ![](../core/media/psadapter-27-task-locationsync.gif "PSAdapter_27_Task_LocationSync")  
  
5. **定義の選択条件に一致する**セクションで、ダブルクリックして、 **LOCATION_SYNC**プロパティを表示するメッセージ。  
  
    ![](../core/media/psadapter-28-task-locationproperties.gif "PSAdapter_28_Task_LocationProperties")  
  
6. アプリケーション デザイナーで右クリックして **[location_tbl]**、選択と**メッセージ プロパティ**します。  
  
    ![](../core/media/psadapter-29-task-loctionmenu.gif "PSAdapter_29_Task_LoctionMenu")  
  
7. **メッセージ プロパティ**画面で、、**使用**タブ。  
  
    クリックして、次のことを確認**OK**します。  
  
   1. **メッセージ:** Active  
  
   2. **Message Channel:** ENTERPRISE_SETUP  
  
   3. **既定のバージョン:** VERSION_1  
  
      ![](../core/media/psadapter-30-task-messageuse.gif "PSAdapter_30_Task_MessageUse")  
  
8. アプリケーション デザイナーを終了します。  
  
    これにより、メッセージの状態がアクティブであること、VERSION_1 が使用されていること、および PeopleSoft の ENTERPRISE_SETUP チャネルにルーティングされていることが確認されました。  
  
9. PeopleSoft アプリケーションと通信するように Integration.Gateway.properties ファイルを構成します。  
  
     プロパティが次のように設定されていることを確認します。  
  
    -   **ig.isc.serverurl:** //server:9000  
  
    -   **ig.isc.userid::** PS の ID  
  
    -   **ig.isc.password::** PS のパスワード  
  
    -   **ig.isc.toolsrel::** 特定のリリース  
  
## <a name="see-also"></a>参照  
 [PeopleSoft の HTTP ホストとポートを作成する](../core/creating-a-peoplesoft-http-host-and-port.md)