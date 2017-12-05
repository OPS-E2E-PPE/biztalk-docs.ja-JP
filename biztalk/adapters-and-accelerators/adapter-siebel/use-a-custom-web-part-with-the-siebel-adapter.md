---
title: "Siebel アダプターとカスタム Web パーツを使用して |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ee3a6c04-6523-483c-bdf4-ce0ac47cda87
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5ad29a3ad28fcea81b00b6b2e2dabf51f0962e79
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="use-a-custom-web-part-with-the-siebel-adapter"></a>Siebel アダプターとカスタム Web パーツを使用します。
このセクションでは、Microsoft Office SharePoint Server でカスタム Web パーツの使用に関する情報を提供します。 カスタム Web パーツを使用するには、次の操作を行う必要があります。  
  
1.  カスタム Web パーツを作成します。  
  
2.  SharePoint ポータルにカスタム Web パーツを展開します。  
  
3.  カスタム Web パーツを使用する SharePoint ポータルを構成します。  
  
## <a name="before-you-begin"></a>はじめに  
 カスタム Web パーツを作成する前に。  
  
-   WCF サービスとしては、Siebel の成果物を発行します。 詳細については、次を参照してください。[手順 1: WCF サービスとしての Siebel ビジネス コンポーネント操作の公開](../../adapters-and-accelerators/adapter-siebel/step-1-publish-the-siebel-business-component-operations-as-a-wcf-service.md)で[チュートリアル 1: 提示データ Siebel システムから SharePoint サイトで](../../adapters-and-accelerators/adapter-siebel/tutorial-1-presenting-data-from-a-siebel-system-on-a-sharepoint-site.md)です。  
  
-   Microsoft Office SharePoint Server でビジネス データ カタログを使用して Siebel 成果物のためのアプリケーション定義ファイルを作成します。 詳細については、次を参照してください。[手順 2: Siebel ビジネス コンポーネント操作のアプリケーション定義ファイルを作成](../../adapters-and-accelerators/adapter-siebel/step-2-create-an-application-definition-file-for-siebel-business-component.md)で[チュートリアル 1: 提示データ Siebel システムから SharePoint サイトで](../../adapters-and-accelerators/adapter-siebel/tutorial-1-presenting-data-from-a-siebel-system-on-a-sharepoint-site.md)です。  
  
##  <a name="Create_a_Custom_Web_Part"></a>手順 1: がカスタム Web パーツを作成します。  
 Visual Studio を使用してカスタム Web パーツを作成するには、次の操作を行います。  
  
1.  Visual Studio を起動し、プロジェクトを作成します。  
  
2.  **新しいプロジェクト** ダイアログ ボックスから、**プロジェクトの種類**ペインで、 **Visual c#**です。 **テンプレート**ペインで、**クラス ライブラリ**です。  
  
3.  ソリューションの場所と名前を指定します。 このトピックでは、指定`CustomWebPart`で、**名前**と**ソリューション名**ボックス。 場所を指定し、をクリックして**OK**です。  
  
4.  System.Web コンポーネントへの参照をプロジェクトに追加します。 プロジェクト名を右クリックして**ソリューション エクスプ ローラー**、クリックして**参照の追加**です。 **参照の追加**ダイアログ ボックスで、 **System.Web**で、 **.NET**  タブをクリックして**OK**です。 System.Web コンポーネントには、System.Web.UI.WebControls.WebParts の必要な名前空間が含まれています。  
  
5.  プロジェクトで、問題に基づく、必要なコードを追加します。 特定の問題に関連するコード サンプルを参照してください「の問題に関連する追加の Web パーツ」 [SharePoint で Siebel アダプターの使用時の考慮事項](../../adapters-and-accelerators/adapter-siebel/considerations-when-using-the-siebel-adapter-with-sharepoint.md)です。  
  
6.  プロジェクトをビルドする。 プロジェクトの成功したビルドで CustomWebPart.dll、.dll ファイルが生成されます、 \<*プロジェクト フォルダー*\>bin/デバッグ フォルダーです。  
  
## <a name="step-2-deploy-the-custom-web-part-to-a-sharepoint-portal"></a>手順 2: カスタム Web パーツを SharePoint ポータルを展開します。  
 CustomWebPart.dll ファイル (カスタム Web パーツ) で作成されるようにする、次を実行する必要があります"手順 1: カスタム Web パーツを作成する"このトピックは SharePoint ポータル上で使用。  
  
-   **CustomWebPart.dll ファイルを SharePoint Portal の bin フォルダーにコピー**: Microsoft Office SharePoint Server は、ポータルを作成、 \<*ドライブのルート*\>: \Inetpub\wwwroot\wss\VirtualDirectories フォルダーです。 フォルダーは、各ポータルが作成され、ポート番号で識別できます。 作成した CustomWebPart.dll ファイルをコピーする必要があります"手順 1: カスタム Web パーツを作成する"に、このトピックの\<*ドライブのルート*\>: \Inetpub\wwwroot\wss\VirtualDirectories\\ <*Port_Number*\>\bin フォルダーです。 たとえば、SharePoint portal のポート番号が 13614 の場合に CustomWebPart.dll ファイルをコピーする必要があります、 \<*ドライブのルート*\>: \Inetpub\wwwroot\wss\VirtualDirectories\13614\bin フォルダーです。  
  
    > [!TIP]
    >  使用して、SharePoint portal のフォルダーの場所を検索する別の方法は、**インターネット インフォメーション サービス (IIS) マネージャー**ウィンドウ (**開始** > **実行** >  **inetmgr**)。 検索で、SharePoint portal、**インターネット インフォメーション サービス (IIS) マネージャー**ウィンドウ ([*computer_name*] > Web サイト > [*ポータル名*])、し、右クリックし、をクリックして**プロパティ**ショートカット メニュー。 SharePoint portal の [プロパティ] ダイアログ ボックスをクリックして、**ホーム ディレクトリ**、タブをクリックし、**ローカル パス**ボックス。  
  
-   **Web.config ファイルに安全なコントロール エントリを追加**: CustomWebPart.dll ファイルを使用する別のコンピューターに、複数のユーザーが、ために、ファイルを"safe"としてを宣言する必要があります SharePoint portal フォルダーにある web.config ファイルを開くためには、 \<*ドライブのルート*\>: \Inetpub\wwwroot\wss\VirtualDirectories\\< Port_Number\>です。 下にある、`<SafeControls>`セクションで、web.config ファイルの次の安全なコントロール エントリを追加します。  
  
    ```  
    <SafeControl Assembly="CustomWebPart" Namespace="CustomWebPart" TypeName="*" Safe="True" />  
    ```  
  
     Web.config ファイルを保存し、閉じます。  
  
## <a name="step-3-configure-the-sharepoint-portal-to-use-the-custom-web-part"></a>手順 3: カスタムの Web パーツを使用する SharePoint ポータルを構成します。  
 SharePoint ポータルで使用できるようにする、Microsoft Office SharePoint Server Web パーツ ギャラリー、カスタムの Web パーツを追加する必要があります。 そのためには次を行います。  
  
1.  SharePoint 3.0 サーバーの全体管理を開始します。 をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft Office Server**、クリックして**SharePoint 3.0 サーバーの全体管理**.  
  
2.  左側のナビゲーション ウィンドウでの共有サービス プロバイダー (SSP) カスタム Web パーツを追加する名前をクリックします。  
  
3.  **共有サービスの管理**ページの右上隅で、をクリックして**サイトの操作**、クリックして**作成**です。  
  
4.  **サイト設定** ページで、をクリックして**Web パーツ**下にある、**ギャラリー**列です。  
  
5.  **Web パーツ ギャラリー**  ページで、ギャラリーにカスタム Web パーツを追加する をクリックして**新規**です。 この時点でカスタム Web パーツでは使用できません、 **Web パーツ ギャラリー**ページ。  
  
6.  **新しい Web パーツ** ページで、検索**CustomWebPart** (カスタムの Web パーツの名前) の一覧で、左側のチェック ボックスをオンにし、をクリックして**ギャラリー**の上にページです。 これが追加されます、 **CustomWebPart**内のエントリ、 **Web パーツ ギャラリー**ページ。  
  
 これで、カスタム Web パーツを使用することができます (**CustomWebPart**) ポータルの SharePoint Web パーツを作成します。 カスタム Web パーツ (**CustomWebPart**) 下に表示されます、 **[その他]** 」の「、 **Web パーツの追加**ページ。  
  
## <a name="see-also"></a>参照  
 [SharePoint での Siebel アダプターの使用](../../adapters-and-accelerators/adapter-siebel/use-the-siebel-adapter-with-sharepoint.md)