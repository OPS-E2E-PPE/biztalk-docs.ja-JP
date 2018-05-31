---
title: TIBCO EMS の作成の成果物を受け取る |Microsoft ドキュメント
description: 受信ポートを作成し、BizTalk Server で、TIBCO Enterprise Message Service アダプタを使用するトランスポートのプロパティを設定
ms.custom: ''
ms.date: 10/23/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e1307e3c-0237-4f19-a642-58e694fe95d0
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf5810dc012c7aa5dcc2fbdfcecd9d59d066ced7
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
ms.locfileid: "24015377"
---
# <a name="create-tibco-ems-receive-artifacts"></a>TIBCO EMS の作成の成果物の受信

## <a name="overview"></a>概要
TIBCO Enterprise Message Service の受信元は、特定のキューまたはトピックを登録して関連メッセージを受信するリスナー サービスです。 BizTalk Adapter for TIBCO Enterprise Message Service は、新しいセッションを開いて、最初に TIBCO Enterprise Message Service を登録し、その後、メッセージを受信するためにポーリングを継続します。 このセクションでは、TIBCO Enterprise Message Service に接続するために受信ポートを設定する方法と、実行時に TIBCO EMS と対話するためにオーケストレーションに XML を含める方法について説明します。  

## <a name="create-a-receive-port"></a>受信ポートを作成する  
  
1.  BizTalk Server 管理コンソールで、展開**BizTalk グループ**、展開**アプリケーション**、し、アプリケーションを展開します。  
  
2.  右クリック**受信ポート****新規**、順にクリック**一方向受信ポート**です。  
  
3.  **受信ポートのプロパティ** ウィンドウで、**全般** ページで、次の操作します。  
  
    1.  **名前**フィールドに「`ReceiveFromTIBCOEMS`です。  
  
    2.  **認証**グループ ボックスで、認証の使用時のメッセージの処理方法を指定します。  
  
    3.  選択、**失敗したメッセージの有効化のルーティングを**チェック ボックスをオンします。  
  
4.  **受信場所** ページで、次の操作します。  
  
    1.  **[新規作成]** をクリックします。  
  
    2.  **受信場所**ウィンドウで、**全般** ページで、入力、**名前**受信場所のです。  
  
    3.  **型**ドロップダウン一覧で、トランスポートの種類を選択してから、**受信ハンドラー**ドロップダウン一覧で、トランスポート アドレスを選択します。  
  
    4.  **受信パイプライン**ドロップダウン リストで、受信パイプラインを選択します。  
  
    5.  **スケジュール**] ページで、[、**開始日**と**終了日**ドキュメントの受信を制限します。  
  
    6.  選択、**有効にするサービス時間帯**チェック ボックスをオンします。  
  
    7.  **[OK]** をクリックします。  
  
5.  **受信マップ**ページで、選択したポートでドキュメントを変換するための受信マップを選択します。  
  
6.  **追跡** ページで、必要なメッセージ本文の追跡と追跡メッセージのプロパティを選択します。  
  
7.  **[OK]** をクリックします。  

## <a name="set-the-receive-port-transport-properties"></a>受信ポートのトランスポート プロパティを設定します。
TIBCO Enterprise Message System (EMS) の受信場所を**URL**と**Target Namespace** TIBCO EMS システムには、必要な唯一の構成値。    
 
1.  展開して、**システム定義**し、TIBCO EMS サーバーに接続に必要なすべての情報を入力します。  
  
2.  展開**メッセージの処理**し必要なすべての情報を入力します。  
  
    |パラメーター|Description|  
    |---------------|-----------------|  
    |**メッセージ セレクター**|メッセージは、メッセージに関してこの文字列が True と評価された場合にのみ送信先で受信されます。<br /><br /> 受信ポートは、このフィールドに記述された式に一致するヘッダー プロパティを含むメッセージのみを受信できます。<br /><br /> メッセージ セレクターの構文は、SQL92 条件式構文のサブセットに基づいています。 構文については、TIBCO EMS のユーザー ガイドで詳しく説明されています。<br /><br /> たとえば、メッセージに NewsType という名前のヘッダー プロパティが含まれている場合、受信ポートでは、種類が Sports または Editorial のメッセージのみを取得できます。|  
    |**再試行の回数**|トランスポートの再試行の回数です。 既定値は 0 です。|  
    |**再試行の間隔**|アダプターが再試行を開始するまでに待機する時間です。 既定値は、5 分です。|  
  
3.  展開して、**サーバー接続の定義**し必要なすべての情報を入力します。  
  
    |パラメーター|Description|  
    |---------------|-----------------|  
    |**変換先**|必須の設定です。 送信先の名前と種類を定義します。 キューまたはトピックを Queue[queue.name] または Topic[topic.name] という形式で定義します。|  
    |**[ポート番号]**|TIBCO EMS サーバーがリッスンするポートです。|  
    |**[サーバー名]**|必須の設定です。 TIBCO EMS サーバーをホストしているシステムの名前です。|  
  
4.  シングル サインオン (SSO) を使用する資格情報を指定します。  
  
     TIBCO EMS システムへのアクセスには、2 つの方法を使用できます。 資格情報 (ユーザー名とパスワードのパラメーター) を使用するまたはシングル サインオンします。  
  
    -   選択**はい**で**SSO を使用する**でのシングル サインオンを使用します。  
  
    -   一覧で関連アプリケーションを選択します。  
  
         エンタープライズ シングル サインオン ツールで作成される関連アプリケーションは、TIBCO EMS などのアプリケーションを表します。 Microsoft BizTalk Adapter for TIBCO EMS は、アプリケーション ユーザーの資格情報を使用します。 これらの資格情報は、指定された関連アプリケーションのサーバー システムの SSO データベースから取得されます。  
  
         関連アプリケーションを作成する方法の詳細については、次を参照してください。[関連アプリケーションの作成](../core/creating-affiliate-applications5.md)です。  
  
5.  展開**ユーザーの資格情報**を入力し、**ユーザー名**と**パスワード**TIBCO EMS サーバーにアクセスします。  
  
    |パラメーター|Description|  
    |---------------|-----------------|  
    |`Password`|TIBCO EMS デーモンとの通信に使用するユーザーのパスワードです。<br /><br /> 選択しなかった場合**SSO を使用する**、BizTalk Adapter for TIBCO EMS デーモンと通信するために TIBCO EMS の資格情報パラメーターを設定する必要があります。|  
    |`User Name`|TIBCO EMS デーモンとの通信に使用するユーザーの名前です。<br /><br /> 選択しなかった場合**SSO を使用する**、BizTalk Adapter for TIBCO EMS デーモンと通信するために TIBCO EMS の資格情報パラメーターを設定する必要があります。|  
  
6.  をクリックして**適用**、順にクリック**OK**です。 

## <a name="next-steps"></a>次の手順
[TIBCO EMS メッセージ コンテキスト プロパティ](../core/message-context-properties-in-biztalk-server.md)