---
title: "PeopleSoft アダプターの送信のアーティファクトを作成 |Microsoft ドキュメント"
description: "送信ポートを作成し、トランスポートのプロパティを送信し、BizTalk Server で PeopleSoft Enterprise アダプターを使用して PeopleSoft にメッセージを送信する最大同時呼び出しを更新"
ms.custom: 
ms.date: 10/19/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ce67da59-26a6-44a2-929c-ed3acb21d407
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2bc559f4e3c25560540a171b3f47ff25e6f34e89
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="create-peoplesoft-send-artifacts"></a>PeopleSoft 送信アイテムを作成します。
Microsoft BizTalk Adapter for PeopleSoft Enterprise は、PeopleSoft にアクセスして、使用できるコンポーネントを探索したり、SOAP 要求を処理したりします。 このトピックでは、PeopleSoft アダプターを使用する BizTalk Server 管理コンソールで、送信の成果物を作成する方法を示します。


## <a name="create-the-send-port"></a>送信ポートを作成します。

1.  BizTalk Server 管理コンソールで、展開**BizTalk グループ**、展開**アプリケーション**、し、目的のアプリケーションを展開します。  
  
2.  右クリック**送信ポート****新規**、し、**静的な送信請求-応答送信ポート**です。  
  
3.  **送信ポートのプロパティ**次の操作を行います。  
  
    1.  送信ポートの名前を入力します。 たとえば、入力`SSOSendToPeopleSoft`です。  
  
    2.  **型**ドロップダウン リストで、 **PeopleSoft**です。  
  
    3.  **送信ハンドラー**ドロップダウン リストで、URI を選択します。  
  
    4.  送信パイプラインのドロップダウン リストから選択**[microsoft.biztalk.defaultpipelines.xmltransmit]**です。  
  
    5.  **受信パイプライン**ドロップダウン リストで、 **[microsoft.biztalk.defaultpiplelines.xmlreceive]**です。  
  
    6.  選択**構成**送信ポートを構成します。  
  
4.  **PeopleSoft トランスポートのプロパティ**次の操作を行います。  
  
    1.  展開**アダプターに必要なプロパティ**、入力と**アプリケーション サーバーのパス**、 **JAVA_HOME**、**ユーザー名**、 **パスワード**、および Peoplesoft システムに接続するための Jar ファイルです。  
  
         ログオン情報を設定する必要はありません。  
  
    2.  一覧で、PeopleSoft システムを表すよう作成した SSO 関連アプリケーションを選択します。  
  
    3.  **SSO を使用する****はい**です。  
  
    4.  **[OK]** を選択します。  
  
5.  **[OK]** を選択します。

## <a name="set-the-transport-properties"></a>トランスポートのプロパティを設定します。
PeopleSoft トランスポートのプロパティは、設計時および実行時に使用されます。 **トランスポートのプロパティ**ダイアログ ボックスで、パラメーターを設定する接続と資格情報を特定サーバーのシステムおよびアクセスしようとしているオブジェクトにします。  
  
 ![](../core/media/peop-peoplesofttransportpropertiess.gif "Peop_PeopleSoftTransportPropertiess")  
  
1.  [アダプターに必要なプロパティ] を展開し、PeopleSoft サーバーへの接続に必要なすべての情報を入力します。  
  
     Microsoft BizTalk Adapter for PeopleSoft Enterprise を PeopleSoft Enterprise に接続するには、構成パラメーターを設定する必要があります。 このデータは、大文字と小文字が区別されます。  
  
    |パラメーター|Description|  
    |---------------|-----------------|  
    |`Application Server Path`|PeopleSoft Application Server が動作して受信を待ち受けているコンピューターおよびポートを表す文字列。 PeopleSoft 8 Application への URL パスの構文は//< computer_name >:\<ポート\>です。 PeopleSoft 管理者に問い合わせて、\<ポート\>値。 \<ポート\>値は、JOLT プロトコル リスナー ポート、App Server ポートではありません。 既定の JOLT ポートは 9000 です。|  
    |`JAVA_HOME`|たとえば、JDK インストールを指すように JAVA_HOME 変数を設定します。 **C:\j2sdk1.4.2_08**です。|  
    |`Password`|選択しなかった場合**SSO を使用する**、BizTalk Adapter for PeopleSoft Enterprise サーバー システムにアクセスするための資格情報パラメーターを設定する必要があります。<br /><br /> PeopleSoft システムへのログオンに使用するユーザーのパスワードを表す文字列です。 文字は表示されませんが、アスタリスク (*) で表されます。|  
    |`PeopleSoft 8.x Jar Files`|コンポーネント インターフェイス (PeopleSoft 8 のみ) を使用するには、PeopleSoft Component Interface の jar ファイルが含まれるように CLASSPATH を更新する必要があります 例: **< PeopleSoft_Home > \web\PSJOA\psjoa.jar**です。|  
    |`User Name`|選択しなかった場合**SSO を使用する**、BizTalk Adapter for PeopleSoft Enterprise サーバー システムにアクセスするための資格情報パラメーターを設定する必要があります。<br /><br /> PeopleSoft システムへのログオンに必要なユーザー名を表す文字列です。|  
  
2.  入力、**追加パラメーター**日付がキーとして使用するときの値とは別の形式です。 既定の形式は YYYY-MM-DD です。  
  
3.  入力、**同時実行制御**で呼び出し、たとえば 200 の数を表す値**Max Concurrent Calls**必要がある場合。  
  
     **Max Concurrent Calls**パラメーターは、バック エンド サーバーがデータの量を処理できない場合に、オーバー ロードの保護をアクティブにします。 同時呼び出しとは、アダプターがまだ返信を受信していない要求のことです。 設定**Max Concurrent Calls**場合、スループットがバックエンドの処理能力を超えています。  
  
     このフィールドの既定値は -1 です。保護は発生しません。  
  
     BizTalk Server が送信アダプターに要求を送信し、同時実行の数が呼び出しまたはに設定された値を超えて 場合**Max Concurrent Calls**、同時呼び出しの数まで、要求を保存送信スレッド設定された値以下に低下します。  

## <a name="update-max-concurrent-calls"></a>最大同時呼び出しを更新します。

`Max Concurrent Calls` パラメーターは、構成を最適化することができる機能です。 このパラメータは、スループットがバックエンドの処理機能を上回るインスタンスで使用します。 パラメーターを追加するには、アダプターに、**送信ポートのトランスポート プロパティ**メッセージ オーバー ロードの保護を有効にする ダイアログ ボックス。 既定値は -1 です。これは呼び出しが制限されないことを意味します。  
  
BizTalk Server は、送信アダプタに対してメッセージを送信するとき、まず、アダプタからバッチを受け取り、バッチで `TransmitMessage()` を呼び出して各メッセージを転送します。 この処理が完了すると、BizTalk Server はバッチで `Done()` を呼び出し、アダプタがバックエンドに対するメッセージ送信を開始します。 BizTalk Server が `Done` を呼び出す前に複数のバッチを取得した場合、`Done` コマンドは発行されないことがあります。 バッチ内に含めるメッセージの最大数を設定することで、バックエンドに送信するメッセージを制御できます。 このパラメータに加えた変更は、すぐに有効になります。 BizTalk Server は、SQL データベースに保存されているアダプター構成に対する変更を取得する必要があります。  
  
### <a name="change-the-max-concurrent-calls-parameter"></a>Max Concurrent Calls パラメーターを変更します。  
  
1.  **送信ポートのトランスポート プロパティ** ダイアログ ボックスで、入力、**接続**値。  
  
     既定値は 40 セッションです。 これより小さい値を使用すると、実行時のパフォーマンスが低下することがあります。 逆の場合も同様に、より大きい値を使用するとサーバーの許容量を超え、実行時エラーが発生することがあります。  
  
2.  選択**はい**の**エージェントの更新**runtimeagent.exe および browsingagent.exe の処理を必要時に自動的に再起動を強制します。  
  
     たとえば、サーバーとの接続が失われた場合や、サーバーに追加したものが Microsoft アダプター ウィザードに表示されない場合に、処理を自動的に再起動することができます。  
  
     **エージェントの更新**パラメーターの参照とランタイム エージェントの両方を更新します。 runtimeagent.exe は、1 分間の遅延後または次の send 呼び出し時に更新されます。  
  
3.  PeopleSoft システムにアクセスするための資格情報を設定します。  
  
     システムへのアクセスには、2 つの方法を使用できます。  
  
    -   ログイン資格情報 (Transport Properties Login パラメーター)  
  
    -   シングル サインオン  
  
4.  選択**はい**の**SSO を使用する**でのシングル サインオンを使用します。  
  
    > [!NOTE]
    >  詳細については、次を参照してください。[アダプターをセキュリティで保護された](../core/security-in-biztalk-adapter-for-peoplesoft-enterprise.md)です。 
  
5.  一覧で関連アプリケーションを選択します。  
  
     エンタープライズ シングル サインオン ツールで作成される関連アプリケーションは、PeopleSoft などのアプリケーションを表します。 BizTalk Adapter for PeopleSoft Enterprise は、アプリケーション ユーザーの資格情報を使用します。 これらの資格情報は、指定された関連アプリケーションのサーバー システムの SSO データベースから取得されます。 取得される資格情報は、BizTalk プロジェクトを起動したユーザー (アプリケーション ユーザー) の資格情報です。  
  
    > [!NOTE]
    >  関連アプリケーションを作成する方法の詳細については、次を参照してください。[関連アプリケーションの作成](../core/creating-affiliate-applications2.md)、または Microsoft BizTalk Server のオンライン ヘルプ。  
  
6.  接続情報を受け入れるように必要なすべての情報を提供すると、をクリックして**適用**、順にクリック**OK**です。  
  
     PeopleSoft にアクセスするには、BizTalk Adapter for PeopleSoft Enterprise に接続パラメーターを設定する必要があります。  
  

## <a name="next"></a>Next
  
[PeopleSoft スキーマを BizTalk Server プロジェクトにインポートします。](../core/importing-peoplesoft-schemas-into-biztalk-server-projects.md)  
[PeopleSoft からの受信](../core/receiving-from-peoplesoft.md)