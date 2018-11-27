---
title: TIBCO EMS 送信アイテムの作成 |Microsoft Docs
description: 送信ポートを作成し、TIBCO Enterprise Message Service アダプターを BizTalk Server で使用するトランスポートのプロパティを構成します。
ms.custom: ''
ms.date: 10/23/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8f82609c-1847-4796-a24c-28cb350ec739
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 98bc13b59826c7f5e938d4749776adb742f70133
ms.sourcegitcommit: a124b58c1ff73c201d17993c3a5f07f41836b0a3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2018
ms.locfileid: "24014185"
---
# <a name="creating--tibco-enterprise-message-service-send-handlers"></a>TIBCO Enterprise Message Service 送信ハンドラーの作成
ここでは、送信ポートを設定して TIBCO Enterprise Message Service (EMS) に接続する方法、およびオーケストレーションに XML を入れ実行時に TIBCO EMS と連携する方法を説明します。  


## <a name="create-a-send-port"></a>送信ポートを作成します。  
  
1.  BizTalk Server 管理コンソールで  **BizTalk グループ**、展開**アプリケーション**、アプリケーションを展開します。  
  
2.  右クリックして**送信ポート**を選択します**新規**、し、**静的な送信請求-応答送信ポート**します。  
  
3.  **送信ポートのプロパティ**次の操作を行います。  
  
    1.  たとえば、送信ポートの名前を入力`SendToTIBCOEMS`します。  
  
    2.  **型**ドロップダウン リストで、 **TIBCO EMS**します。  
  
    3.  **送信ハンドラー**ドロップダウン リストで、URI を選択します。  
  
    4.  **送信パイプライン**ドロップダウン リストで、 **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**します。 **受信パイプライン**ドロップダウン リストで、 **[microsoft.biztalk.defaultpiplelines.xmlreceive]** します。  

        > [!NOTE]
        > BizTalk Adapter for TIBCO Enterprise Message Service では、受信、送信、および [xmlreceive] の [xmltransmit] を選択することが必要です。  
  
    6.  選択**構成**送信ポートを構成します。  
  
4.  **TIBCO EMS トランスポートのプロパティ** ダイアログ ボックスで、次の操作を行います。  
  
    1.  入力**メッセージの処理**、**サーバー接続の定義**、**トランザクションのサポート**、 **Username**、および**パスワード**します。  
  
         ログオン情報を設定する必要はありません。  
  
    2.  一覧で、TIBCO EMS システムを表すよう作成した関連アプリケーションを選択します。  
  
    3.  **SSO を使用**、**はい**します。  
  
    4.  **[OK]** を選択します。  
  
5.  **[OK]** を選択します。 

## <a name="set-send-port-transport-properties"></a>送信ポート トランスポートのプロパティを設定
TIBCO Enterprise Message Service トランスポート プロパティは、デザイン時に構成して実行時に使用します。 **トランスポートのプロパティ**、接続および資格情報パラメーターに固有の設定、サーバー システムとアクセスしようとしているオブジェクト。  
  
 ![](../core/media/tib-tibcoemssendtransportpropertiess.gif "TIB_TIBCOEMSSendTransportPropertiess")  
  
  
1.  **トランスポートのプロパティ**、展開**システム定義**、し、TIBCO EMS サーバーへの接続に必要なすべての情報を入力します。  
  
     Microsoft BizTalk Adapter for TIBCO Enterprise Message Service を TIBCO EMS に接続するための構成パラメーターを設定する必要があります。 **このデータは、大文字小文字を区別します。**  
  
2.  展開**メッセージの処理**、必要なすべての情報を入力します。  
  
    |パラメーター|説明|  
    |---------------|-----------------|  
    |`Message Expiration Time`|メッセージがキューまたはトピックにとどまる時間の長さを表す整数。この時間が経過すると、メッセージは TIBCO EMS サーバーによって削除されます。<br /><br /> EMS.Expiration メッセージ プロパティ ヘッダーと同義です。 オーケストレーションによってオーバーライドされることがあります。<br /><br /> 既定値は 0 ミリ秒であり、メッセージが送信先で期限切れにならないことを指定します。|  
    |`Message is Persistent`|メッセージは、受信確認の前に、TIBCO EMS サーバーによってディスクに書き込まれます。<br /><br /> これは TibcoEMS.DeliveryMode ヘッダー プロパティです。 アダプターに対するメッセージ受信確認の前に、送信されたメッセージがサーバーによってキューに保存されるように指示します。<br /><br /> 既定値は **True**です。|  
    |`Message Priority`|メッセージの優先度を定義する 0 ～ 9 の数値によるランク付け。値が大きいほど優先度が高くなります。<br /><br /> プロパティは、サーバーがメッセージをコンシューマーに配信する順序に影響します (値が大きいほど順番が早くなります)。<br /><br /> JMS 仕様では、0 (最低の優先度) から 9 (最高の優先度) まで 10 レベルの優先度値が定義されています。 この仕様では、クライアントが 0 ～ 4 を通常の優先度の段階と想定し、5 ～ 9 を高優先度の段階と想定するように推奨されています。<br /><br /> 既定値は**4**します。|  
  
3.  展開**サーバー接続の定義**必要なすべての情報を入力します。  
  
    |パラメーター|説明|  
    |---------------|-----------------|  
    |`Destination`|必須の設定です。 送信先の名前と種類を定義します。 例: staticqueue [Q1]。<br /><br /> キューまたはトピックは、次の形式を定義します。 {static} {dynamic] Queue [queuename] または {static} {dynamic] Topic [topicname]。 **注:** 存在しない宛先にメッセージを送信することができます。 このような場合は、TIBCO Enterprise Message Service は送信先; を作成します呼ばれる、*動的送信先*します。 これはプロデューサーによって作成され、メッセージが消費されてプロデューサーが切断された時点で削除されます。 A*静的送信先*がのみ作成できる送信先をして、TIBCO Enterprise Message Service 管理者です。 送信先との接続を開いている状態で動的ポートに接続することはできません。BizTalk Adapter for TIBCO Enterprise Message Service はサーバー上の名前の参照メカニズムを利用するからです。 名前の参照を使用するときは、静的ポートのみが表示されます。 動的ポートに接続するときに静的送信先を使用できます。ただし、その名前の送信先が存在しない場合は、送信先が作成されます。 Destination では、ポートを定義するときに、使用する送信先の種類を明示的に指定できます。 宛先の構文が大文字小文字が区別: staticqueue [queue_name]、statictopic [topic_name]、dynamicqueue [queue_name];dynamictopic [topic_name]。|  
    |`Port Number`|TIBCO EMS サーバーがリッスンするポートです。|  
    |`Server Name`|必須の設定です。 TIBCO EMS サーバーをホストしているシステムの名前です。|  
  
4.  シングル サインオン (SSO) を使用する資格情報を指定します。  
  
     TIBCO EMS システムにアクセスするには 2 つの方法を使用できます。 1 つは資格情報 ([ユーザー名] パラメーターと [パスワード] パラメーター) を使用する方法で、もう 1 つはシングル サインオン (SSO) を使用する方法です。  
  
    -   選択**はい**で、**を使用して SSO**でシングル サインオンを使用します。  
  
    -   一覧から関連アプリケーションを選択します。  
  
         エンタープライズ シングル サインオン ツールで作成される関連アプリケーションは、TIBCO EMS などのアプリケーションを表します。 BizTalk Adapter for TIBCO EMS は、アプリケーション ユーザーの資格情報を使用します。 これらの資格情報は、指定された関連アプリケーションのサーバー システムの SSO データベースから取得されます。  
  
         関連アプリケーションを作成する方法の詳細については、次を参照してください。[関連アプリケーションを作成する](../core/creating-affiliate-applications5.md)します。  
  
5.  **トランザクションをサポートして**を選択します**はい**場合、この送信ポートがトランザクションをサポートします。  
  
     ポートのトランザクションのサポートを有効にする場合、このポートを使用するすべてのオーケストレーションがトランザクション対応である必要があります。そうでない場合、すべての呼び出しはロールバックされます (コミットされないなど)。 オーケストレーションに追加したスコープ オブジェクトによって、トランザクションのライフサイクルが制御されます。  
  
6.  展開**ユーザーの資格情報**を入力し、**ユーザー名**と**パスワード**TIBCO EMS サーバーにアクセスします。  
  
    |パラメーター|説明|  
    |---------------|-----------------|  
    |`Password`|TIBCO EMS デーモンとの通信に使用されるユーザーのパスワード。<br /><br /> 選択しなかった場合**使用 SSO**、BizTalk Adapter for TIBCO EMS デーモンとの通信に TIBCO EMS の資格情報パラメーターを設定する必要があります。|  
    |`User Name`|TIBCO EMS デーモンとの通信に使用されるユーザー名。<br /><br /> 選択しなかった場合**使用 SSO**、BizTalk Adapter for TIBCO EMS デーモンとの通信に TIBCO EMS の資格情報パラメーターを設定する必要があります。|  
  
7.  クリックして**適用**、順にクリックします**OK**します。  

   
## <a name="next-steps"></a>次の手順
[受信アイテムの作成](../core/creating-tibco-enterprise-message-service-receive-handlers.md)  
[TIBCO EMS メッセージ コンテキスト プロパティ](../core/message-context-properties-in-biztalk-server.md)