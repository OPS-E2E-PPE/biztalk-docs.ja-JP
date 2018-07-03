---
title: '手順 2: Fabrikam LOBWebApplication の作成 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- private process tutorial, creating LOBWebApplication
- LOBWebApplication
ms.assetid: 2ff8bd20-7fbc-4e16-b177-bb4afac7f7c3
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9c55234d8ee9c123c9efe9e7ec66b7c0db590b54
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966627"
---
# <a name="step-2-creating-the-fabrikam-lobwebapplication"></a>手順 2: Fabrikam LOBWebApplication の作成
ここでは、Fabrikam が 3A2 PIP 要求を Contoso に送信するために使用する LOB アプリケーションを作成します。 LOBWebApplication プロジェクトは、[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] SDK にインストールされています。 Web アプリケーションを実行するには、Microsoft インターネット インフォメーション サービス (IIS) 仮想ディレクトリを作成し、LOBWebApplication プロジェクトをビルドがあります。  
  
> [!NOTE]
>  ダブル アクション チュートリアルを完了済みであれば、この手順を実行する必要はありません。  
  
### <a name="to-create-the-lobwebapplication-virtual-directory"></a>LOBWebApplication 仮想ディレクトリを作成するには  
  
1.  クリックして**開始**、 をポイント**管理ツール**、順にクリックします**インターネット インフォメーション サービス マネージャー**します。  
  
    > [!NOTE]
    >  ダブル アクション チュートリアルを完了済みであれば、このチュートリアルで LOBWebApplication 仮想ディレクトリを作成しています。 その場合は、この手順を実行する必要はありません。 仮想ディレクトリからのアクセス許可を変更する必要が、ただし、**スクリプトを実行する**に**読み取り**します。  
  
2.  インターネット インフォメーション サービス マネージャーで  **< computer_name > (ローカル コンピューター)**、順に展開**Websites**します。  
  
3.  右クリック**既定の Web サイト**、 をポイント**新規**、 をクリックし、**仮想ディレクトリ**します。  
  
4.  **Welcometo 仮想ディレクトリの作成ウィザードのページ**、 をクリックして**次**します。  
  
5.  **仮想ディレクトリ エイリアス**] ページの [、**エイリアス**ボックスに「 **LOBWebApplication**、順にクリックします**次**します。  
  
6.  **Web サイトのコンテンツ ディレクトリ**] ページで [**参照**を選択、 **\<ドライブ\>: \Program Files\Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\lobwebapplication**フォルダー、およびクリック**OK**します。 **[次へ]** をクリックします。  
  
7.  **仮想ディレクトリのアクセス許可**] ページで [**次**します。  
  
8.  クリックして**完了**仮想ディレクトリを作成します。  
  
### <a name="excluding-lobwebapplication-from-sharepoint"></a>SharePoint からの LOBWebApplication の除外  
  
1.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**管理ツール**、順にクリックします**SharePoint Central Administration**。  
  
    > [!NOTE]
    >  ダブル アクション チュートリアルを完了済みであれば、チュートリアルで LOBWebApplication 仮想ディレクトリを SharePoint から除外しています。 その場合は、この手順を実行する必要はありません。  
  
2.  **サーバーの全体管理**] ページの [、**仮想サーバーの構成**セクションで、**アップグレード仮想サーバーの拡張または**します。  
  
3.  コンピューターで構成されている URL が表示されない場合はクリックして**完全な一覧**します。  
  
4.  選択**Default Web Site**します。  
  
5.  **仮想サーバーの管理**セクションで、**管理パスの定義**します。  
  
6.  **新しいパスの追加**セクションで、**パス**ボックスに「"/LOBWebApplication". **型**を選択します**エクスクルード パス**、順にクリックします**OK**します。  
  
### <a name="to-build-the-lobwebapplication-project"></a>LOBWebApplication プロジェクトをビルドするには  
  
1.  開始**Microsoft Visual Studio 2012**します。  
  
2.  **ファイル**メニューで、**オープン**、 をクリックし、**プロジェクト \ ソリューション**します。  
  
3.  プロジェクトを開く ダイアログ ボックスで**検索対象の**に移動**\<ドライブ\>: \Program Files\Microsoft BizTalk\<バージョン\>して sdk \ のアクセラレータLOBWebApplication**を選択、 **LOBWebApplication.sln**ソリューション、およびクリック**オープン**します。  
  
4.  ソリューション エクスプ ローラーで最上位ノードを右クリックし (http://localhost/LOBWebApplication)、 をクリックし、**参照の追加**します。  
  
5.  [参照の追加] ダイアログ ボックスで、**参照**に移動し、 **\<ドライブ\>: \Program Files\Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \bin**.  
  
6.  **選択 Microsoft.Solutions.BTARN.ConfigurationManager.dll および Microsoft.Solutions.BTARN.Shared.dll**アセンブリ**し、[ok] をクリックします。**  
  
7.  **ビルド** メニューのをクリックして**Web サイトのビルド**します。  
  
### <a name="to-run-the-lobwebapplication-project"></a>LOBWebApplication プロジェクトを実行するには  
  
1.  ソリューション エクスプ ローラーで右クリックして**default.aspx**、し、**スタート ページとして設定**します。  
  
2.  **デバッグ** メニューのをクリックして**デバッグなしで開始**します。  
  
## <a name="see-also"></a>参照  
 [ソリューションのテスト](../../adapters-and-accelerators/accelerator-rosettanet/testing-the-solution.md)