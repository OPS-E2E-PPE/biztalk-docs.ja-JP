---
title: HTTP 受信場所の IIS の構成 |Microsoft Docs
description: IIS では、BTS HTTP 受信アプリケーションを作成し、BizTalk Server でのアプリケーション プールの設定のテスト
ms.custom: ''
ms.date: 10/10/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1c420f46-01f1-4c9c-9144-d8d2acc8b0c4
caps.latest.revision: 26
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cfc616fa9834071c2ee8d2b4d63f486ff0abbeab
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004827"
---
# <a name="configure-iis-for-an-http-receive-location"></a>HTTP 受信場所用に IIS を構成します。
HTTP は受信場所が使用をアプリケーション内では、インターネット インフォメーション サービス (IIS)。 このトピックで、HTTP を有効にする手順が一覧には、IIS 内の場所が表示されます。 

オペレーティング システムに応じて、IIS アプリケーションを構成する手順が異なる場合があります。 ガイドとして次の手順を使用して、ユーザー インターフェイスは、OS で異なる可能性があります。
  
## <a name="32-bit-vs-64-bit"></a>32 ビットと 64 ビット

HTTP では、場所は、BTSHTTPReceive.dll を受信します。 32 ビットと 64 ビット版は、DLL があります。 使用するバージョンを選択します。 64 ビット プロセスで使用可能なメモリのためがあるかどうかには、大きなサイズのメッセージを処理し、64 ビット バージョンが最適な可能性があります。 

**32 ビットのインストール場所**: *Program Files (x86) \Microsoft BizTalk Server\HttpReceive*します。
**64 ビットのインストール場所**: *Program Files (x86) \Microsoft BizTalk Server\HttpReceive64*

HTTP の 64 ビット バージョンを実行する 64 ビットのネイティブ モードで受信アダプター、コマンド プロンプトを開き、次のスクリプトを実行します。  

1. 種類: `cscript %SystemDrive%\inetpub\AdminScripts\adsutil.vbs set w3svc/AppPools/Enable32bitAppOnWin64 0`  

2. 種類: `C:\WINDOWS\Microsoft.NET\Framework64\vX.X.XXXXX>aspnet_regiis.exe -i`  
  
> [!NOTE]
>  同一プロセスを共有する SOAP と HTTP を使用する IIS 構成は無効です。 プロセスごとに 1 つの分離受信場所のみを指定できます。  
  
##  <a name="configure-the-iis-application"></a>IIS アプリケーションを構成します。
  
1. 開く**インターネット インフォメーション サービス**(開く**サーバー マネージャー**を選択します**ツール**、選択と**インターネット インフォメーション サービス マネージャー**). 
  
2. IIS では、サーバー名を選択します。 **機能ビュー**、ダブルクリックして**ハンドラー マッピング**します。 [操作] ウィンドウで、次のように選択します。**スクリプト マップの追加**します。  
  
   > [!NOTE]
   >  Web サーバー レベルでスクリプトのマッピングを構成するときに、すべての web サイトに、マッピングが適用されます。 特定の Web サイトまたは仮想フォルダーへのマッピングを制限する場合は、その web サイトまたはフォルダーを選択し、し、スクリプト マップを追加します。  
  
3. **スクリプト マップの追加**を選択します**要求パス**、および種類`BtsHttpReceive.dll`します。  
  
4. **実行可能ファイル**、省略記号を選択します (**.**) を参照および[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\HttpReceive します。 選択**BtsHttpReceive.dll**、し、**オープン**します。  
  
5. **名前**、入力`BizTalk HTTP Receive`、し、**要求の制限**します。 このウィンドウには。
  
   1. **動詞**を選択します**次の動詞のいずれかの**、入力と`POST`します。  
  
   2. **アクセス**を選択します**スクリプト**、し、 **OK**します。  
  
   3. ISAPI 拡張を許可するメッセージが表示されたら、**はい**します。  
  
6. 新しいアプリケーション プールの作成 (を右クリックして**アプリケーション プール**を選択します**アプリケーション プールの追加**)。 **名前**、アプリケーション プール (など`BTSHTTPReceive`) を選択します**NET Framework v4.0.30319**を選択し、 **OK**します。  
  
    > [!NOTE]
    >  .NET のバージョン番号は、コンピューターにインストールされている .NET Framework のバージョンによって異なる場合があります。  
  
     新しいアプリケーション プールが表示されます。  
  
7. 新しいアプリケーション プールを選択して開きます、**詳細設定**(**アクション**ウィンドウ)。 このウィンドウには。

    - **32 ビット アプリケーションを有効にする**: に設定**True** 32 ビットを選択した場合**BtsHttpReceive.dll**
    - **モデルの処理** セクションで、 **Identity**: 省略記号を選択します (**.**) を選択します**カスタム アカウント**、し**設定**のメンバーであるアカウントに、 **BizTalk 分離ホスト ユーザー**と**IIS_WPG**グループ。 **[OK]** を選択します。 
  
8. Web サイトに新しいアプリケーションを追加 (を右クリックし、**既定の Web サイト**、**アプリケーションの追加**)。 このウィンドウには。
  
   1. **エイリアス**: アプリケーションに関連付けるエイリアスを入力します (など`BTS HTTP Receive`、し**選択**します。  
   2. 作成した新しいアプリケーション プールを選択し、選択**OK**します。  
   3. **物理パス**: 省略記号を選択します (**.**) を参照および[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\HttpReceive します。  
   4. **テストの設定**でエラーがないことを確認する、 **Test-connection**  ダイアログ ボックス。 **閉じる**、し、 **OK**します。  
  
      > [!TIP]
      > テストの設定には、警告が返された場合は、フォルダーへのアクセス許可またはグループにアクセスするアプリケーション プールの id がない可能性が。 トラブルシューティングの手順として次のように選択します。**接続として**、入力、**ユーザー名**と**パスワード**の Administrators グループのメンバーであるユーザー アカウント。 

9. 新しいアプリケーションが下に一覧表示**既定の Web サイト**します。  
  
## <a name="see-also"></a>参照  
 [HTTP 受信場所を構成する方法](../core/how-to-configure-an-http-receive-location.md)
