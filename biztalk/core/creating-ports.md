---
title: ポートの作成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ports, creating
- receive ports
- creating, send ports
- creating, ports
- Configuration database [BizTalk Server], connecting
- receive ports, creating
- send ports
- send ports, creating
ms.assetid: 4f99f884-5b84-4f9f-8cec-dd5da259ba7f
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4f9370442e6f24222a361aa2a6c9901dca0772f9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65353630"
---
# <a name="creating-ports"></a>ポートの作成
次の手順を使用して作成する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]送信および受信ポートをシングル サインオンします。  
  
## <a name="creating-a-send-port"></a>送信ポートの作成  
  
#### <a name="to-create-a-send-port"></a>送信ポートを作成するには  
  
1.  BizTalk Server 管理コンソールで  **BizTalk Server 管理**、展開**BizTalk グループ**、展開**アプリケーション**、必要な展開アプリケーション。  
  
2.  右クリック**送信ポート**、 をポイント**新規**、 をクリックし、**静的な送信請求-応答送信ポート**します。  
  
3.  **送信ポートのプロパティ** ダイアログ ボックスで、次の操作を行います。  
  
    1.  たとえば、送信ポートの名前を入力`SSOSendToPeopleSoft`します。  
  
    2.  **型**ドロップダウン リストで、 **PeopleSoft**します。  
  
    3.  **送信ハンドラー**ドロップダウン リストで、URI を選択します。  
  
    4.  送信パイプラインのドロップダウン リストから選択**Microsoft.BizTalk.DefaultPipelines.XMLTransmit**します。  
  
    5.  **受信パイプライン**ドロップダウン リストで、 **[microsoft.biztalk.defaultpiplelines.xmlreceive]** します。  
  
    6.  クリックして**構成**送信ポートを構成します。  
  
4.  **PeopleSoft トランスポートのプロパティ** ダイアログ ボックスで、次の操作を行います。  
  
    1.  展開**アダプターに必要なプロパティ**、入力と**アプリケーション サーバーのパス**、 **JAVA_HOME**、**ユーザー名**、 **パスワード**、および Peoplesoft システムに接続するための Jar ファイル。  
  
         ログオン情報を設定する必要はありません。  
  
    2.  一覧で、PeopleSoft システムを表すよう作成した SSO 関連アプリケーションを選択します。  
  
    3.  **SSO を使用**、**はい**します。  
  
    4.  **[OK]** をクリックします。  
  
5.  **[OK]** をクリックします。  
  
## <a name="creating-a-receive-port"></a>作成、受信ポート  
  
#### <a name="to-create-a-receive-port"></a>受信ポートを作成するには  
  
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
  
## <a name="see-also"></a>参照  
 [アダプターのセキュリティ保護](../core/security-in-biztalk-adapter-for-peoplesoft-enterprise.md)