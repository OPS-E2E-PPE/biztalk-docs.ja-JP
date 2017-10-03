---
title: "JD Edwards OneWorld トランスポートのプロパティを設定する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- setting transport properties
- transport properties, setting
ms.assetid: 6d38088b-a496-414e-aae6-d28c5d6398b6
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7abac3b468b8c76b8214e400366144b39f1e2741
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-set-jd-edwards-oneworld-transport-properties"></a>JD Edwards OneWorld トランスポートのプロパティを設定する方法
JD Edwards OneWorld の "トランスポート プロパティ" システム定義は、デザイン時および実行時のログオンに使用されます。 この資格情報を設定するのは、デザイン時に JD Edwards OneWorld ビジネス関数を参照するためと、実行時に呼び出しを行うためです。  
  
 JD Edwards OneWorld への接続が作成されるときに、接続オブジェクトにパラメーターが渡されます (ユーザー、パスワード、環境)。 JD Edwards OneWorld Application ビジネス関数のインスタンスが返されます。 資格情報には、さらにエンタープライズ サーバー/アプリケーション サーバーの名前、およびサービスがリッスンする定義済みの TCP/IP ポートが含まれます。  
  
 エンタープライズ サーバーの名前とポートは、jdeinterop.ini というファイルから読み取られます。 これらの値は、システム定義での設定値と同一でなければなりません。  
  
> [!NOTE]
>  入力値はすべて、大文字と小文字が区別されます。  
  
## <a name="setting-properties"></a>プロパティの設定  
 **トランスポートのプロパティ**ダイアログ ボックスで、サーバーのシステムおよびアクセスしようとしているオブジェクトに固有の接続および資格情報パラメーターを設定します。  
  
 このプロセスの手順は次のとおりです。  
  
#### <a name="to-set-transport-properties"></a>トランスポートのプロパティを設定するには  
  
1.  資格情報を指定します。  
  
     JD Edwards OneWorld システムにアクセスするには、次の方法があります。  
  
    -   ログオン資格情報 (パスワード、ユーザー名): このメソッドを使用する場合は、手順 5. に進みます。  
  
    -   シングル サインオン  
  
2.  シングル サインオン (SSO) を使用するのには、選択**はい**で、 **SSO を使用する**です。  
  
     SSO を設定する方法の詳細については、次を参照してください。[シングル サインオンを使用して](../core/using-single-sign-on3.md)です。  
  
3.  一覧で関連アプリケーションを選択します。  
  
     エンタープライズ シングル サインオンのツールによって作成される関連アプリケーションはそれぞれ、JD Edwards OneWorld などの特定のアプリケーションを表します。 Microsoft BizTalk Adapter for JD Edwards OneWorld では、アプリケーション ユーザーの資格情報が使用されます。 この資格情報は、指定された関連アプリケーションのサーバー システムの SSO 資格情報データベースから取得されます。 取得される資格情報は、BizTalk Server プロジェクトを起動したアプリケーション ユーザーの資格情報です。  
  
     詳細については、次を参照してください。[関連アプリケーションの作成](../core/creating-affiliate-applications3.md)です。  
  
4.  展開して、 **JD Edwards OneWorld システム**ノードと JD Edwards OneWorld サーバーに接続に必要なすべての情報を入力します。  
  
     ![](../core/media/jdedadapter-02-jdesystem.gif "JDEdAdapter_02_JDESystem")  
  
     接続パラメーターの設定が完了すると、JD Edwards OneWorld システムの内容を参照できるようになります。 詳細については、次を参照してください。[を BizTalk Server プロジェクトに JD Edwards OneWorld スキーマをインポートする](../core/importing-jd-edwards-oneworld-schemas-into-biztalk-server-projects.md)です。  
  
5.  呼び出し、たとえば 200 の数を示す値を入力**Max Concurrent Calls**必要がある場合。  
  
     `Max Concurrent Calls`パラメーターを使用して、構成を最適化することができます。 スループットがバックエンドの処理能力を上回る場合に、このパラメーターを使用してメッセージ オーバーロード保護をアクティブにします。 既定値は -1 で、これは呼び出しの数が無制限であることを示します。  
  
     BizTalk Server が送信アダプターにメッセージを送信するときに、BizTalk Server は最初にアダプターからバッチを 1 つ受け取ります。 `TransmitMessage` をそのバッチに対して起動して、各メッセージを送信します。 この処理が完了すると、BizTalk Server はバッチで `Done` を呼び出し、アダプタがバックエンドに対するメッセージ送信を開始します。 BizTalk Server が複数のバッチを受け取ってから `Done` を呼び出しても、メッセージは送信されません。 バッチ内に含めるメッセージの最大数を設定することで、バックエンドに送信するメッセージを制御できます。  
  
     このパラメーターの変更が反映されるまで最大 1 分程度かかります。BizTalk Server は、SQL データベースに保存されたアダプター構成に対する変更を取得する必要があるからです。  
  
6.  選択**はい**の**エージェントの更新**runtimeagent.exe および browsingagent.exe の処理を必要時に自動的に再起動を強制します。  
  
     たとえば、サーバーとの接続が失われた場合や、サーバーに追加したものが Microsoft アダプター ウィザードに表示されない場合に、処理を自動的に再起動することができます。  
  
    > [!NOTE]
    >  browsingagent.exe が最新の状態に更新されるのは、ユーザーが現在の参照セッションを終了したときです。 たとえば、終了する必要があります、**項目の生成された追加**参照セッションとを browsingagent.exe を更新します。  
  
7.  必要なすべての情報を提供すると、をクリックして**適用**、クリックして**[ok]**の接続情報を受け入れます。  
  
     JD Edwards OneWorld にアクセスするには、BizTalk Adapter for JD Edwards OneWorld の接続パラメーターを設定する必要があります。  
  
### <a name="adapter-required-properties"></a>アダプターに必要なプロパティ  
 コントロール パネルでグローバル環境変数を設定しなかった場合は、このセクションで設定できます。  
  
|パラメーター|Description|  
|---------------|-----------------|  
|`Host`|ホスト サーバーのコンピューター名の名前を入力 (たとえば、 `actsvr1`); またはコンピューターの IP アドレス (たとえば、 `123.456.0.789`)。|  
|JAVA_HOME|JDK インストール ディレクトリの完全パスを入力します。|  
|JD Edwards 環境|たとえば、JD Edwards OneWorld の環境の名前を入力`DV7333`です。<br /><br /> DV7333 は開発環境の一般名、PY7333 はプロトタイプ環境の一般名、PD7333 は実稼働環境の一般名です。|  
|JDEdwards JAR ファイル|各 JAR ファイルの完全なパスとファイル名を入力します。<br /><br /> -Connector.jar<br />-Kernel.jar<br />-JDEJAccess.jar<br />-JDEActionalInterop.jar<br /><br /> jar ファイルの区切りにはセミコロン (;) を使用し、スペースは入れません。 例:<br /><br /> `<drive>\Connector.jar;<drive>\Kernel.jar;`|  
|Password|指定されたユーザーのパスワードを入力します。|  
|ポート|データを交換するポート番号を入力 (たとえば、 `6009`)。|  
|[ユーザー名]|JD Edwards OneWorld システムへのログオンに使用する JD Edwards OneWorld ユーザー名を入力します。|  
  
## <a name="see-also"></a>参照  
 [JD Edwards OneWorld 送信ハンドラーの作成](../core/creating-jd-edwards-oneworld-send-handlers.md)