---
title: PeopleSoft アダプターの送信アイテムの作成 |Microsoft Docs
description: 送信ポートを作成し、トランスポートのプロパティを送信し、PeopleSoft Enterprise アダプターを BizTalk server を使用して PeopleSoft にメッセージを送信する最大同時呼び出しを更新
ms.custom: ''
ms.date: 10/19/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ce67da59-26a6-44a2-929c-ed3acb21d407
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e4857bf6444f30da0162cf7ffbeb8572042ba762
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390433"
---
# <a name="create-peoplesoft-send-artifacts"></a>PeopleSoft 送信アイテムを作成します。
Microsoft BizTalk Adapter for PeopleSoft Enterprise は PeopleSoft にアクセスで使用可能なコンポーネントについて説明し、SOAP 要求を処理します。 このトピックでは、PeopleSoft アダプターを使用する BizTalk Server 管理コンソールで送信アイテムを作成する方法を示します。


## <a name="create-the-send-port"></a>送信ポートを作成します。

1.  BizTalk Server 管理コンソールで  **BizTalk グループ**、展開**アプリケーション**、し、目的のアプリケーションを展開します。  
  
2.  右クリックして**送信ポート**を選択します**新規**、し、**静的な送信請求-応答送信ポート**します。  
  
3.  **送信ポートのプロパティ**次の操作を行います。  
  
    1.  送信ポートの名前を入力します。 たとえば、`SSOSendToPeopleSoft` と入力します。  
  
    2.  **型**ドロップダウン リストで、 **PeopleSoft**します。  
  
    3.  **送信ハンドラー**ドロップダウン リストで、URI を選択します。  
  
    4.  送信パイプラインのドロップダウン リストから選択**Microsoft.BizTalk.DefaultPipelines.XMLTransmit**します。  
  
    5.  **受信パイプライン**ドロップダウン リストで、 **[microsoft.biztalk.defaultpiplelines.xmlreceive]** します。  
  
    6.  選択**構成**送信ポートを構成します。  
  
4.  **PeopleSoft トランスポートのプロパティ**次の操作を行います。  
  
    1.  展開**アダプターに必要なプロパティ**、入力と**アプリケーション サーバーのパス**、 **JAVA_HOME**、**ユーザー名**、 **パスワード**、および Peoplesoft システムに接続するための Jar ファイル。  
  
         ログオン情報を設定する必要はありません。  
  
    2.  一覧で、PeopleSoft システムを表すよう作成した SSO 関連アプリケーションを選択します。  
  
    3.  **SSO を使用**、**はい**します。  
  
    4.  **[OK]** を選択します。  
  
5.  **[OK]** を選択します。

## <a name="set-the-transport-properties"></a>トランスポートのプロパティを設定します。
PeopleSoft トランスポートのプロパティはデザインに使用し、実行時間。 **トランスポートのプロパティ**ダイアログ ボックスで、接続および資格情報パラメーターに固有の設定、サーバー システムとアクセスしようとしているオブジェクト。  
  
 ![](../core/media/peop-peoplesofttransportpropertiess.gif "Peop_PeopleSoftTransportPropertiess")  
  
1.  アダプターの必要なプロパティを展開し、PeopleSoft サーバーへの接続に必要なすべての情報を入力します。  
  
     Microsoft BizTalk Adapter for PeopleSoft Enterprise を PeopleSoft Enterprise に接続する構成パラメーターを設定する必要があります。 このデータは、大文字小文字を区別します。  
  
    |パラメーター|説明|  
    |---------------|-----------------|  
    |`Application Server Path`|ポートのロックを実行しているが、PeopleSoft Application Server がリッスンしているコンピューターを表す文字列。 PeopleSoft 8 Application への URL パスの構文は//< computer_name >:\<ポート\>します。 PeopleSoft 管理者に問い合わせて、\<ポート\>値。 \<ポート\>値は、JOLT プロトコル リスナー ポート、App Server ポートではありません。 既定の JOLT ポートは 9000 ですです。|  
    |`JAVA_HOME`|たとえば、JDK のインストール をポイントする JAVA_HOME 変数を設定します。**C:\j2sdk1.4.2_08**します。|  
    |`Password`|選択しなかった場合**使用 SSO**、BizTalk Adapter for PeopleSoft Enterprise サーバー システムにアクセスするための資格情報パラメーターを設定する必要があります。<br /><br /> PeopleSoft システムへのログオン ユーザーのパスワードを表す文字列。 文字は表示されませんが、アスタリスク (*) で表されます。|  
    |`PeopleSoft 8.x Jar Files`|コンポーネントを使用するには、インターフェイス (PeopleSoft 8 のみ)、クラスパスに含める、PeopleSoft コンポーネント インターフェイスを更新する必要があります jar ファイルを使用します。 例: **< PeopleSoft_Home > \web\PSJOA\psjoa.jar**します。|  
    |`User Name`|選択しなかった場合**使用 SSO**、BizTalk Adapter for PeopleSoft Enterprise サーバー システムにアクセスするための資格情報パラメーターを設定する必要があります。<br /><br /> PeopleSoft システムへのログオンに必要なユーザー名を表す文字列。|  
  
2.  入力、**追加パラメーター**値の日付をキーとして使用する場合に、別の形式があります。 YYYY-MM-DD では、既定の形式を示します。  
  
3.  入力、**同時実行制御**で呼び出し、たとえば 200 の数を表す値**最大同時呼び出し数**必要な場合。  
  
     **最大同時呼び出し数**パラメーターは、バック エンド サーバーは、データの量を処理できない場合に、オーバー ロードの保護をアクティブにします。 同時呼び出しは、対象のアダプターはまだありません返信要求です。 設定**最大同時呼び出し数**スループットがバックエンド処理機能を上回るインスタンスでします。  
  
     既定値のこのフィールドが-1 の場合に発生します保護れないことを意味します。  
  
     BizTalk Server 送信アダプターでは、要求を送信して、同時実行の数が呼び出しまたはの設定値を超える場合**最大同時呼び出し数**、同時呼び出しの数まで、要求が保存された送信スレッド設定値を下回るまで減少します。  

## <a name="update-max-concurrent-calls"></a>最大同時呼び出しを更新します。

`Max Concurrent Calls`パラメーターは、機能、構成を最適化することができます。 スループットがバックエンド処理機能を上回るインスタンスでは、このパラメーターを使用します。 パラメーターを追加するには、アダプターに、**送信ポートのトランスポート プロパティ**メッセージ オーバー ロードの保護をアクティブにする ダイアログ ボックス。 既定値は -1 です。これは呼び出しが制限されないことを意味します。  
  
BizTalk Server では、送信アダプターにメッセージを送信するときに最初にアダプターからバッチを受信し、呼び出します`TransmitMessage()`で各メッセージを送信するバッチ。 この処理が完了すると、BizTalk Server はバッチで `Done()` を呼び出し、アダプタがバックエンドに対するメッセージ送信を開始します。 BizTalk Server は、前に複数のバッチを取得した場合`Done`が呼び出される、`Done`コマンドが発生することはありません。 バッチ内に含めるメッセージの最大数を設定することで、バックエンドに送信するメッセージを制御できます。 このパラメーターを変更するには、1 分で有効です。 BizTalk Server では、SQL database に保存されているアダプター構成に対する変更を取得する必要があります。  
  
### <a name="change-the-max-concurrent-calls-parameter"></a>Max Concurrent Calls パラメーターを変更します。  
  
1.  **送信ポートのトランスポート プロパティ** ダイアログ ボックスに、入力、**接続**値。  
  
     既定値は、40 セッションです。 小さい値を使用する場合は、実行時のパフォーマンスの低下があります。 逆の場合も同様です。大きい値には、実行時エラーの結果、サーバーの機能を超える可能性があります。  
  
2.  選択**はい**の**エージェントの更新**runtimeagent.exe および browsingagent.exe の処理を必要な場合に自動的に再起動を強制します。  
  
     たとえば、サーバーとの接続が失われた場合や、サーバーに追加したものが Microsoft アダプター ウィザードに表示されない場合に、処理を自動的に再起動することができます。  
  
     **エージェントの更新**両方参照エージェントとランタイム エージェント パラメーターを更新します。 または次の 1 つ分の遅延の後、runtimeagent.exe 更新プログラムは、呼び出しを送信します。  
  
3.  PeopleSoft システムにアクセスする資格情報を提供します。  
  
     2 つのメソッドを使用するには、システムにアクセスします。  
  
    -   ログイン資格情報 (Transport Properties Login パラメーター)  
  
    -   シングル サインオン  
  
4.  選択**はい**の**を使用して SSO**でシングル サインオンを使用します。  
  
    > [!NOTE]
    >  詳細については、次を参照してください。[アダプターのセキュリティ保護](../core/security-in-biztalk-adapter-for-peoplesoft-enterprise.md)します。 
  
5.  一覧で関連アプリケーションを選択します。  
  
     エンタープライズ シングル サインオン ツールによって作成される関連アプリケーションは、PeopleSoft などのアプリケーションを表します。 Microsoft BizTalk Adapter for PeopleSoft Enterprise では、アプリケーション ユーザーの資格情報を使用します。 これらの資格情報は、指定された関連アプリケーションのサーバー システムの SSO データベースから取得されます。 資格情報では、BizTalk プロジェクトを起動したユーザー (アプリケーション ユーザー) のものです。  
  
    > [!NOTE]
    >  関連アプリケーションを作成する方法の詳細については、次を参照してください。[関連アプリケーションを作成する](../core/creating-affiliate-applications2.md)、または Microsoft BizTalk Server のオンライン ヘルプ。  
  
6.  接続情報を受け入れるように必要なすべての情報を提供するには、後に次のようにクリックします。**適用**、順にクリックします**OK**します。  
  
     BizTalk Adapter for PeopleSoft Enterprise PeopleSoft へのアクセスの接続パラメーターを設定する必要があります。  
  

## <a name="next"></a>Next
  
[PeopleSoft スキーマを BizTalk Server プロジェクトにインポートします。](../core/importing-peoplesoft-schemas-into-biztalk-server-projects.md)  
[PeopleSoft からの受信](../core/receiving-from-peoplesoft.md)