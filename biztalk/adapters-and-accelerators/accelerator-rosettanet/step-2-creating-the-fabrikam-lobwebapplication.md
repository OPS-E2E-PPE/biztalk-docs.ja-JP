---
title: "手順 2: Fabrikam LOBWebApplication の作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- private process tutorial, creating LOBWebApplication
- LOBWebApplication
ms.assetid: 2ff8bd20-7fbc-4e16-b177-bb4afac7f7c3
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ed64aac8ea0cf4073f3085f4491f607373d721b6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-2-creating-the-fabrikam-lobwebapplication"></a>手順 2: Fabrikam LOBWebApplication の作成
ここでは、Fabrikam が 3A2 PIP 要求を Contoso に送信するために使用する LOB アプリケーションを作成します。 LOBWebApplication プロジェクトは、[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] SDK にインストールされています。 Web アプリケーションを実行するためには、[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] インターネット インフォメーション サービス (IIS) 仮想ディレクトリを作成し、LOBWebApplication プロジェクトをビルドする必要があります。  
  
> [!NOTE]
>  ダブル アクション チュートリアルを完了済みであれば、この手順を実行する必要はありません。  
  
### <a name="to-create-the-lobwebapplication-virtual-directory"></a>LOBWebApplication 仮想ディレクトリを作成するには  
  
1.  をクリックして**開始**、 をポイント**管理ツール**、順にクリック**インターネット インフォメーション サービス マネージャー**です。  
  
    > [!NOTE]
    >  ダブル アクション チュートリアルを完了済みであれば、このチュートリアルで LOBWebApplication 仮想ディレクトリを作成しています。 その場合は、この手順を実行する必要はありません。 仮想ディレクトリのアクセス許可を変更する必要が、ただし、**スクリプトを実行する**に**読み取り**です。  
  
2.  インターネット インフォメーション サービス マネージャーで  **< computer_name > (ローカル コンピューター)**、順に展開**Websites**です。  
  
3.  右クリック**既定の Web サイト**、 をポイント**新規**、クリックして**仮想ディレクトリ**です。  
  
4.  **Welcometo 仮想ディレクトリの作成ウィザード ページ**、 をクリックして**次**です。  
  
5.  **仮想ディレクトリ エイリアス**] ページの [、**エイリアス**ボックスに、入力**LOBWebApplication**、順にクリック**次**です。  
  
6.  **Web サイトのコンテンツのディレクトリ**] ページで [**参照**を選択、 **\<ドライブ >: \Program Files\Microsoft BizTalk\<バージョン > Accelerator forRosettanet \sdk\lobwebapplication**フォルダー、およびクリック**OK**です。 **[次へ]**をクリックします。  
  
7.  **仮想ディレクトリのアクセス許可**] ページで [**次**です。  
  
8.  をクリックして**完了**仮想ディレクトリを作成します。  
  
### <a name="excluding-lobwebapplication-from-sharepoint"></a>SharePoint からの LOBWebApplication の除外  
  
1.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**管理ツール**、順にクリック**SharePoint サーバーの全体管理**です。  
  
    > [!NOTE]
    >  ダブル アクション チュートリアルを完了済みであれば、チュートリアルで LOBWebApplication 仮想ディレクトリを SharePoint から除外しています。 その場合は、この手順を実行する必要はありません。  
  
2.  **サーバーの全体管理**] ページの [、**仮想サーバーの構成**セクションで、**拡張またはアップグレードの virtual server**です。  
  
3.  コンピューターで構成されている URL が表示されない場合にクリックして**完全な一覧**です。  
  
4.  選択**既定の Web サイト**です。  
  
5.  **仮想サーバーの管理**セクションで、**管理パスの定義**です。  
  
6.  **新しいパスの追加**セクションで、**パス**ボックスに、入力"/LOBWebApplication"。 **型**を選択**エクスクルード パス**、順にクリック**OK**です。  
  
### <a name="to-build-the-lobwebapplication-project"></a>LOBWebApplication プロジェクトをビルドするには  
  
1.  開始**Microsoft Visual Studio 2012**です。  
  
2.  **ファイル** メニューのをポイント**開く**、クリックして**Project\Solution**です。  
  
3.  プロジェクトを開く ダイアログ ボックスで**検索対象の**に移動**\<ドライブ >: \Program Files\Microsoft BizTalk\<バージョン > Accelerator for RosettaNet\ SDK\LOBWebApplication**、選択、 **LOBWebApplication.sln**ソリューション、およびクリック**開く**です。  
  
4.  ソリューション エクスプ ローラーで、最上位ノード (http://localhost/LOBWebApplication) を右クリックし、をクリックして**参照の追加**です。  
  
5.  [参照の追加] ダイアログ ボックスで、**参照**に移動する**\<ドライブ >: \Program Files\Microsoft BizTalk\<バージョン > Accelerator for rosettanet \bin**です。  
  
6.  **選択、Microsoft.Solutions.BTARN.ConfigurationManager.dll および Microsoft.Solutions.BTARN.Shared.dll**アセンブリ**し、[OK] をクリックします。**  
  
7.  **ビルド** メニューのをクリックして**Web サイトのビルド**です。  
  
### <a name="to-run-the-lobwebapplication-project"></a>LOBWebApplication プロジェクトを実行するには  
  
1.  ソリューション エクスプ ローラーで右クリック**default.aspx**、し、**スタート ページとして設定**です。  
  
2.  **デバッグ** メニューのをクリックして**デバッグなしで開始**です。  
  
## <a name="see-also"></a>参照  
 [ソリューションをテストします。](../../adapters-and-accelerators/accelerator-rosettanet/testing-the-solution.md)