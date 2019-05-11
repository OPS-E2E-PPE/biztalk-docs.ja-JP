---
title: Oracle E-business Suite でカスタム web パーツを使用する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bf420061-41d1-4d97-9be1-403cd101e41c
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fe143d9926632150acb581f69a7f14cb1546d9c2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65376129"
---
# <a name="how-to-use-a-custom-web-part-with-oracle-e-business-suite"></a>Oracle E-business Suite でカスタム web パーツを使用する方法
このセクションでは、Microsoft Office SharePoint Server でカスタム Web パーツの使用に関する情報を提供します。 カスタム Web パーツを使用するには、次の操作を行う必要があります。  
  
1.  カスタム Web パーツを作成します。  
  
2.  SharePoint ポータルにカスタム Web パーツを展開します。  
  
3.  カスタム Web パーツを使用する SharePoint ポータルを構成します。  
  
## <a name="before-you-begin"></a>はじめに  
 カスタム Web パーツを作成する前に。  
  
-   WCF サービスとしての Oracle E-business Suite の成果物を発行します。 詳細については、次を参照してください。[手順 1。Oracle E-business アダプターを使用して作成および WCF サービス発行](../../adapters-and-accelerators/adapter-oracle-ebs/step-1-use-the-oracle-e-business-adapter-to-create-and-publish-a-wcf-service.md)で[チュートリアル。SharePoint サイト上の Oracle E-business Suite からデータを提示](Tutorial:%20Present%20data%20from%20Oracle%20E-Business%20Suite%20on%20a%20SharePoint%20Site.md)します。  
  
-   Microsoft Office SharePoint Server でビジネス データ カタログを使用して Oracle E-business Suite の成果物のアプリケーション定義ファイルを作成します。 詳細については、次を参照してください。[手順 2。Oracle E-business Suite の成果物のアプリケーション定義ファイルを作成](../../adapters-and-accelerators/adapter-oracle-ebs/step-2-create-an-application-definition-file-for-the-oracle-ebs-artifacts.md)で[チュートリアル。SharePoint サイト上の Oracle E-business Suite からデータを提示](Tutorial:%20Present%20data%20from%20Oracle%20E-Business%20Suite%20on%20a%20SharePoint%20Site.md)します。  
  
##  <a name="Create_a_Custom_Web_Part"></a> ステップ 1:カスタム Web パーツを作成します。  
  
1.  Visual Studio を起動し、プロジェクトを作成します。  
  
2.  **新しいプロジェクト** ダイアログ ボックスから、**プロジェクトの種類**ペインで、 **Visual c#** します。 **テンプレート**ペインで、**クラス ライブラリ**します。  
  
3.  ソリューションの場所と名前を指定します。 このトピックでは、次のように指定します。`CustomWebPart`で、**名前**と**ソリューション名**ボックス。 場所を指定し、クリックして**OK**します。  
  
4.  System.Web コンポーネントへの参照をプロジェクトに追加します。 プロジェクト名を右クリックして**ソリューション エクスプ ローラー**、 をクリックし、**参照の追加**します。 **参照の追加**ダイアログ ボックスで、 **System.Web**で、 **.NET**  タブをクリックして**OK**します。 System.Web コンポーネントには、System.Web.UI.WebControls.WebParts の必要な名前空間が含まれています。  
  
5.  プロジェクトの問題に基づいて、必要なコードを追加します。 特定の問題に関連するコード サンプルでは、「問題に関連するカスタム Web パーツ」を参照してください[SharePoint で Oracle Business Suite アダプターの使用に関する考慮事項](../../adapters-and-accelerators/adapter-oracle-ebs/considerations-using-the-oracle-business-suite-adapter-with-sharepoint.md)します。  
  
6.  プロジェクトをビルドする。 プロジェクトの成功したビルドで CustomWebPart.dll、.dll ファイルが生成されます、\<プロジェクト フォルダー\>bin/デバッグ フォルダー。  
  
7.  **64 ビット コンピューターに対してのみ**:次の手順を実行する前に厳密な名前で CustomWebPart.dll ファイルを署名します。 それ以外の場合、することができなくインポート、および SharePoint ポータルで、CustomWebPart.dll のため、使用する"手順 3。カスタム Web パーツを使用する SharePoint ポータルを構成します。" 厳密な名前でアセンブリに署名する方法については、次を参照してください。[方法。厳密な名前でアセンブリに署名](https://msdn.microsoft.com/library/xc31ft41.aspx)します。
  
## <a name="step-2-deploy-the-custom-web-part-to-a-sharepoint-portal"></a>手順 2:SharePoint ポータルにカスタム Web パーツを展開します。  
 作成される CustomWebPart.dll ファイル (カスタム Web パーツ) を作成するには、次を行う必要があります"手順 1。カスタム Web パーツを作成"このトピックでの SharePoint ポータルの使用:  
  
- **SharePoint Portal の bin フォルダーに CustomWebPart.dll ファイルをコピー**:Microsoft Office SharePoint Server は、ポータルを作成、\<ドライブのルート\>: \Inetpub\wwwroot\wss\VirtualDirectories フォルダー。 フォルダーは、それぞれのポータルが作成され、ポート番号で識別できます。 作成した CustomWebPart.dll ファイルをコピーする必要があります"手順 1。カスタム Web パーツの作成"するには、このトピックの\<ドライブのルート\>: \Inetpub\wwwroot\wss\VirtualDirectories\\< Port_Number\>\bin フォルダー。 たとえば、SharePoint ポータルのポート番号が 13614 の場合に CustomWebPart.dll ファイルをコピーする必要があります、\<ドライブのルート\>: \Inetpub\wwwroot\wss\VirtualDirectories\13614\bin フォルダー。  
  
  > [!TIP]
  >  使用して、SharePoint ポータルのフォルダーの場所を検索する別の方法は、**インターネット インフォメーション サービス (IIS) マネージャー**ウィンドウ (**開始** > **実行** >  **inetmgr**)。 SharePoint ポータルの検索、**インターネット インフォメーション サービス (IIS) マネージャー**ウィンドウ ([コンピューター名] > の Web サイト > [ポータル-Name])、右クリックしをクリック**プロパティ**で、ショートカット メニュー。 SharePoint ポータルの [プロパティ] ダイアログ ボックスでをクリックして、**ホーム ディレクトリ**、タブを選び、**ローカル パス**ボックス。  
  
- **Web.config ファイルに安全なコントロール エントリを追加**:CustomWebPart.dll ファイルを別のコンピューターと、複数のユーザーが使用するため、「安全」としてファイルを宣言する必要があります。 これを行うには、SharePoint portal フォルダーにある web.config ファイルを開く\<ドライブのルート\>: \Inetpub\wwwroot\wss\VirtualDirectories\\< Port_Number\>します。 下、`<SafeControls>`セクション、web.config ファイルの次の安全なコントロール エントリを追加します。  
  
  - **32 ビット コンピューター。**  
  
    ```  
    <SafeControl Assembly="CustomWebPart" Namespace="CustomWebPart" TypeName="*" Safe="True" />  
    ```  
  
  - **64 ビット コンピューター。**  
  
    ```  
    <SafeControl Assembly="CustomWebPart, Version=1.0.0.0, Culture=neutral, PublicKeyToken=<PUBLICKKEYTOKEN_OF_CustomWebPart.dll>" Namespace="CustomWebPart" TypeName="*" Safe="True" />  
    ```  
  
    Web.config ファイルを保存して、閉じます。  
  
## <a name="step-3-configure-the-sharepoint-portal-to-use-the-custom-web-part"></a>手順 3:カスタム Web パーツを使用する SharePoint ポータルを構成します。  
 これを使用するには、SharePoint ポータルにするために、Microsoft Office SharePoint Server Web パーツ ギャラリーでカスタム Web パーツを追加する必要があります。 そのためには次を行います。  
  
1. SharePoint 3.0 サーバーの全体管理を開始します。 クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft Office Server**、順にクリックします**SharePoint 3.0 サーバーの全体管理**.  
  
2. 左側のナビゲーション ウィンドウでの共有サービス プロバイダー (SSP) カスタム Web パーツを追加する名前をクリックします。  
  
3. 共有サービス管理 ページで、右上隅にある**サイトの操作**、 をクリックし、**作成**です。  
  
4. サイトの設定 ページで、次のようにクリックします。 **Web パーツ**下、**ギャラリー**列。  
  
5. Web パーツ ギャラリー ページで、カスタム Web パーツをギャラリーを追加するクリックして**新規**します。 この時点でカスタム Web パーツでは、Web パーツのギャラリー ページでは使用できません。  
  
6. 新しい Web パーツ ページで、検索**CustomWebPart** (カスタムの Web パーツの名前) の一覧で、左側のチェック ボックスをオンにし**ギャラリー**ページ上部にあります。 これは追加、 **CustomWebPart** Web パーツのギャラリー ページのエントリ。  
  
   カスタム Web パーツを使用するようになりました (**CustomWebPart**)、SharePoint ポータルで Web パーツを作成します。 カスタム Web パーツ (**CustomWebPart**) 下に表示されます、 **その他** Web パーツの追加 ページでセクション。  
  
## <a name="see-also"></a>参照  
[SharePoint で Oracle E-business Suite アダプターを使用します。](../../adapters-and-accelerators/adapter-oracle-ebs/use-the-oracle-e-business-suite-adapter-with-sharepoint.md)