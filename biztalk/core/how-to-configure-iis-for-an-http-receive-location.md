---
title: "HTTP の受信場所の IIS を構成する |Microsoft ドキュメント"
description: "IIS では、BTS HTTP 受信アプリケーションを作成し、BizTalk Server でのアプリケーション プールの設定のテスト"
ms.custom: 
ms.date: 10/10/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1c420f46-01f1-4c9c-9144-d8d2acc8b0c4
caps.latest.revision: "26"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e09768d6616a33a4900995f3dd3225fa34318b3c
ms.sourcegitcommit: 75d35f6f230f0846c29a4b146c6d5b074e60b13c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/11/2017
---
# <a name="configure-iis-for-an-http-receive-location"></a>HTTP の受信場所の IIS を構成します。
HTTP は、場所が使用アプリケーション内では、インターネット インフォメーション サービス (IIS) を受信します。 このトピックに HTTP を有効にする手順は、IIS 内の場所を受信します。 

オペレーティング システムに応じて、IIS アプリケーションを構成する手順が異なる場合があります。 として使用してこれらの手順、ガイドでは、ユーザー インターフェイスが、OS で異なる場合があります。
  
## <a name="32-bit-vs-64-bit"></a>32 ビットと 64 ビット

HTTP の受信場所が、BTSHTTPReceive.dll を使用します。 32 ビットと DLL の 64 ビット バージョンがあります。 使用するバージョンを選択します。 64 ビット プロセスで使用可能なメモリがためがあるかどうかより大きなメッセージを処理する、64 ビット バージョンが最適な可能性があります。 

**32 ビットのインストール場所**: *%program Files (x86) \Microsoft BizTalk Server\HttpReceive*です。
**64 ビットのインストール場所**: *%program Files (x86) \Microsoft BizTalk Server\HttpReceive64*

HTTP の 64 ビット バージョンを実行する 64 ビットのネイティブ モードで受信アダプター、コマンド プロンプトを開き、および次のスクリプトを実行します。  

1. 型:`cscript %SystemDrive%\inetpub\AdminScripts\adsutil.vbs set w3svc/AppPools/Enable32bitAppOnWin64 0`  

2. 型:`C:\WINDOWS\Microsoft.NET\Framework64\vX.X.XXXXX>aspnet_regiis.exe -i`  
  
> [!NOTE]
>  同一プロセスを共有する SOAP と HTTP を使用する IIS 構成は無効です。 プロセスごとに 1 つの分離受信場所のみを指定できます。  
  
##  <a name="configure-the-iis-application"></a>IIS アプリケーションを構成します。
  
1.  開く**インターネット インフォメーション サービス**(開く**サーバー マネージャー****ツール**を選択し、**インターネット インフォメーション サービス マネージャー**). 
  
2.  IIS では、サーバー名を選択します。 **機能ビュー**をダブルクリックして**ハンドラー マッピング**です。 [操作] ウィンドウで、次のように選択します。**スクリプト マップの追加**です。  
  
    > [!NOTE]
    >  Web サーバー レベルでスクリプト マッピングを構成するときに、マッピングがすべての web サイトに適用されます。 特定の Web サイトまたは仮想フォルダーへのマッピングを制限する場合は、その web サイトまたはフォルダーを選択し、スクリプト マップを追加します。  
  
3.  **スクリプト マップの追加****要求パス**、および種類`BtsHttpReceive.dll`です。  
  
4.  **実行可能ファイル**、省略記号 (**.**) を参照および[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\HttpReceive です。 選択**BtsHttpReceive.dll**、し、**開く**です。  
  
5.  **名前**、入力`BizTalk HTTP Receive`、し、**要求の制限**です。 このウィンドウには。
  
    1. **動詞****次の動詞のいずれかの**、入力と`POST`です。  
  
    2. **アクセス****スクリプト**、し、 **OK**。  
  
    3. ISAPI 拡張を許可するメッセージが表示されたら、**はい**です。  
  
6. 新しいアプリケーション プールの作成 (を右クリックして**アプリケーション プール****アプリケーション プールの追加**)。 **名前**アプリケーション プール (など`BTSHTTPReceive`) を選択**NET Framework v4.0.30319**を選択し、 **OK**です。  
  
    > [!NOTE]
    >  .NET バージョン番号は、コンピューターにインストールされている .NET Framework のバージョンによって異なる場合があります。  
  
     新しいアプリケーション プールが表示されます。  
  
7. 新しいアプリケーション プールを選択して開きます、**詳細設定**(**アクション**ウィンドウ)。 このウィンドウには。

    - **32 ビット アプリケーションを有効にする**: 'Éý' **True**する場合は、32 ビット**BtsHttpReceive.dll**
    - **モデルの処理** セクションで、 **Identity**: は、省略記号 (**.**) を選択**カスタム アカウント**、し**設定**のメンバーであるアカウントに、 **BizTalk Isolated Host Users**と**IIS_WPG**グループ。 [ **OK**] を選択します。 
  
8. Web サイトに新しいアプリケーションを追加 (を右クリックし、**既定の Web サイト****アプリケーションの追加**)。 このウィンドウには。
  
    1. **エイリアス**: アプリケーションに関連付けるエイリアスを入力 (など`BTS HTTP Receive`、し**選択**です。  
    2. 作成した新しいアプリケーション プールを選択し、選択**OK**です。  
    3. **物理パス**: は、省略記号 (**.**) を参照および[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\HttpReceive です。  
    4. **テストの設定**にエラーがないことを確認する、 **Test-connection**  ダイアログ ボックス。 **閉じる**、し、 **OK**です。  
  
    > [!TIP]
    > テストの設定には、警告が返された場合は、フォルダーへのアクセス許可またはグループへのアクセス、アプリケーション プールの id がない可能性がします。 トラブルシューティング手順として、次のように選択します。**接続として**、入力、**ユーザー名**と**パスワード**Administrators グループのメンバーであるユーザー アカウントのです。 

9. 新しいアプリケーションの表示の下に表示**既定の Web サイト**です。  
  
## <a name="see-also"></a>参照  
 [HTTP 受信場所を構成する方法](../core/how-to-configure-an-http-receive-location.md)
