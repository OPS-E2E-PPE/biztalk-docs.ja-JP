---
title: '手順 7: ビルドと LOBWebApplication SDK サンプルの展開 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- double action tutorial, building solutions
- double action tutorial, deploying solutions
ms.assetid: f61de666-ebda-4831-9669-598e9284e4c1
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3a0716c854c20f5ea7fa7d2ad91576cb142f6a02
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996187"
---
# <a name="step-7-building-and-deploying-the-lobwebapplication-sdk-sample"></a>手順 7: ビルドと LOBWebApplication SDK サンプルの展開
ここでは、Fabrikam が PIP (Partner Interface Process) 要求を Contoso に送信するために使用する基幹業務 (LOB) アプリケーションを作成します。 LOBWebApplication プロジェクトは、Microsoft® で見つかります[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]SDK フォルダー。 Web アプリケーションを実行するには、Microsoft インターネット インフォメーション サービス (IIS) の仮想ディレクトリを作成し、LOBWebApplication プロジェクトを作成するがあります。  
  
### <a name="to-create-the-lobwebapplication-virtual-directory"></a>LOBWebApplication 仮想ディレクトリを作成するには  
  
1.  クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**管理ツール**、順にクリックします**インターネット インフォメーション サービス (IIS) マネージャー**.  
  
2.  インターネット インフォメーション サービス マネージャ ウィンドウで、 **< computer_name > (ローカル コンピューター)**、順に展開**Websites**します。  
  
3.  右クリック**既定の Web サイト**、 をポイント**新規**、 をクリックし、**仮想ディレクトリ**します。  
  
4.  **Welcometo 仮想ディレクトリの作成ウィザード**] ページで [**次**します。  
  
5.  **仮想ディレクトリ エイリアス**] ページの [、**エイリアス**ボックスに「 **LOBWebApplication**、順にクリックします**次**します。  
  
6.  **Web サイトのコンテンツ ディレクトリ**] ページで [**参照**します。 フォルダーの参照 ダイアログ ボックスに移動します ***\<ドライブ\>*:\Program files \microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\lobwebapplication**、し、。クリックして**OK**します。 **[次へ]** をクリックします。  
  
7.  **仮想ディレクトリのアクセス許可** ページで、選択を解除**読み取り**を選択します **(ASP) などのスクリプトを実行する**、順にクリックします**次**。  
  
8.  **仮想ディレクトリの作成ウィザードを正常に完了しました**] ページで [**完了**仮想ディレクトリを作成します。  
  
### <a name="to-exclude-the-lobwebapplication-web-site-from-the-sharepoint-configuration"></a>SharePoint 構成から LOBWebApplication Web サイトを除外するには  
  
1.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**管理ツール**、順にクリックします**SharePoint Central Administration**。  
  
2.  **サーバーの全体管理**Web ページの**仮想サーバーの構成**セクションで、**アップグレード仮想サーバーの拡張または**します。  
  
3.  コンピューターで構成されている URL が表示されない場合はクリックして**完全な一覧**します。  
  
4.  **仮想サーバーのリスト**] ページで、[**既定の Web サイト**します。  
  
5.  **仮想サーバーの管理**セクションで、**管理パスの定義**します。  
  
6.  **新しいパスの追加**セクションで、**パス**ボックスに「 **/LOBWebApplication**します。  
  
7.  **型**を選択します**エクスクルード パス**、順にクリックします**OK**します。  
  
### <a name="to-build-the-lobwebapplication-project"></a>LOBWebApplication プロジェクトをビルドするには  
  
1.  クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft Visual Studio 2008**、順にクリックします**Microsoft Visual Studio 2008**します。  
  
2.  **[ファイル]** メニューの **[開く]** をポイントし、 **[プロジェクト/ソリューション]** をクリックします。  
  
3.  プロジェクトを開く ダイアログ ボックスに移動します。 ***\<ドライブ\>*:\Program files \microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\lobwebapplication**、、を選択します。**LOBWebApplication.sln**ソリューション ファイル、およびクリック**オープン**します。  
  
4.  ソリューション エクスプ ローラーで右クリックして**http://localhost/LOBWebApplication**、 をクリックし、**参照の追加**します。  
  
5.  [参照の追加] ダイアログ ボックスで、**参照**します。 [参照の追加] ダイアログ ボックスに移動します。 ***\<ドライブ\>*:\Program files \microsoft BizTalk\<バージョン\>Accelerator for rosettanet \bin**フォルダー。  
  
6.  Bin フォルダーから次のように選択します。、 **Microsoft.Solutions.BTARN.ConfigurationManager.dll**と**Microsoft.Solutions.BTARN.Shared.dll**アセンブリ、およびクリック**開く。**  
  
7.  をクリックして**OK**を閉じる、**参照の追加** ダイアログ ボックス。  
  
8.  ソリューション エクスプ ローラーで右クリック**ソリューション 'LOBWebApplication'** し**ソリューションのビルド**します。  
  
9. 右クリックして**default.aspx**、 をクリックし、**スタート ページとして設定**します。  
  
## <a name="see-also"></a>参照  
 [ダブル アクション チュートリアルのテスト](../../adapters-and-accelerators/accelerator-rosettanet/testing-the-double-action-tutorial.md)