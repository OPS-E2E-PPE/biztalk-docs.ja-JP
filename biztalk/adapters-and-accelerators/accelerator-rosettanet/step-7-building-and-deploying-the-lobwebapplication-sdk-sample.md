---
title: "手順 7: ビルドと LOBWebApplication SDK サンプルの展開 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- double action tutorial, building solutions
- double action tutorial, deploying solutions
ms.assetid: f61de666-ebda-4831-9669-598e9284e4c1
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fa2504ebf80537e81e9ef0ee2f72e1e7afeb716d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-7-building-and-deploying-the-lobwebapplication-sdk-sample"></a>手順 7: ビルドと LOBWebApplication SDK サンプルの展開
ここでは、Fabrikam が PIP (Partner Interface Process) 要求を Contoso に送信するために使用する基幹業務 (LOB) アプリケーションを作成します。 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] SDK フォルダーに LOBWebApplication プロジェクトがあります。 Web アプリケーションを実行するためには、[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] インターネット インフォメーション サービス (IIS) 仮想ディレクトリを作成した後で、LOBWebApplication プロジェクトをビルドする必要があります。  
  
### <a name="to-create-the-lobwebapplication-virtual-directory"></a>LOBWebApplication 仮想ディレクトリを作成するには  
  
1.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**管理ツール**、クリックして**インターネット インフォメーション サービス (IIS) マネージャー**.  
  
2.  インターネット インフォメーション サービス マネージャー ウィンドウで、 **< computer_name > (ローカル コンピューター)**、順に展開**Websites**です。  
  
3.  右クリック**既定の Web サイト**、 をポイント**新規**、クリックして**仮想ディレクトリ**です。  
  
4.  **Welcometo 仮想ディレクトリの作成ウィザード**] ページで [**次**です。  
  
5.  **仮想ディレクトリ エイリアス**] ページの [、**エイリアス**ボックスに、入力**LOBWebApplication**、順にクリック**次**です。  
  
6.  **Web サイトのコンテンツのディレクトリ**] ページで [**参照**です。 フォルダーの参照 ダイアログ ボックスに移動 ***\<ドライブ >*: \Program Files\Microsoft BizTalk\<バージョン > Accelerator for rosettanet \sdk\lobwebapplication**、およびをクリックして**OK**です。 **[次へ]**をクリックします。  
  
7.  **仮想ディレクトリのアクセス許可**] ページで、選択を解除**読み取り**[ **(ASP) などのスクリプトを実行**、順にクリック**[次へ]**です。  
  
8.  **仮想ディレクトリの作成ウィザードを正常に完了しました** ページで、をクリックして**完了**仮想ディレクトリを作成します。  
  
### <a name="to-exclude-the-lobwebapplication-web-site-from-the-sharepoint-configuration"></a>SharePoint 構成から LOBWebApplication Web サイトを除外するには  
  
1.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**管理ツール**、順にクリック**SharePoint サーバーの全体管理**です。  
  
2.  **サーバーの全体管理**Web ページの**仮想サーバーの構成**セクションで、**拡張またはアップグレードの virtual server**です。  
  
3.  コンピューターで構成されている URL が表示されない場合にクリックして**完全な一覧**です。  
  
4.  **仮想サーバーのリスト**] ページで、[ **Default Web Site**です。  
  
5.  **仮想サーバーの管理**セクションで、**管理パスの定義**です。  
  
6.  **新しいパスの追加**セクションで、**パス**ボックスに、入力**/LOBWebApplication**です。  
  
7.  **型**を選択**エクスクルード パス**、順にクリック**OK**です。  
  
### <a name="to-build-the-lobwebapplication-project"></a>LOBWebApplication プロジェクトをビルドするには  
  
1.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft Visual Studio 2008**、順にクリック**Microsoft Visual Studio 2008**です。  
  
2.  **[ファイル]** メニューの **[開く]**をポイントし、 **[プロジェクト/ソリューション]**をクリックします。  
  
3.  プロジェクトを開く ダイアログ ボックスに移動 ***\<ドライブ >*: \Program Files\Microsoft BizTalk\<バージョン > Accelerator for rosettanet \sdk\lobwebapplication**を選択**LOBWebApplication.sln**ソリューション ファイル、およびクリック**開く**です。  
  
4.  ソリューション エクスプ ローラーで右クリック**http://localhost/LOBWebApplication**、クリックして**参照の追加**です。  
  
5.  [参照の追加] ダイアログ ボックスで、**参照**です。 [参照の追加] ダイアログ ボックスに移動 ***\<ドライブ >*: \Program Files\Microsoft BizTalk\<バージョン > Accelerator for rosettanet \bin**フォルダーです。  
  
6.  Bin フォルダーから次のように選択します。、 **Microsoft.Solutions.BTARN.ConfigurationManager.dll**と**Microsoft.Solutions.BTARN.Shared.dll**アセンブリ、およびクリック**開きます。**  
  
7.  をクリックして**OK**を閉じる、**参照の追加** ダイアログ ボックス。  
  
8.  ソリューション エクスプ ローラーで右クリック**ソリューション 'LOBWebApplication'**  をクリックし、**ソリューションのビルド**です。  
  
9. 右クリック**default.aspx**、クリックして**スタート ページとして設定**です。  
  
## <a name="see-also"></a>参照  
 [ダブル アクション チュートリアルのテスト](../../adapters-and-accelerators/accelerator-rosettanet/testing-the-double-action-tutorial.md)