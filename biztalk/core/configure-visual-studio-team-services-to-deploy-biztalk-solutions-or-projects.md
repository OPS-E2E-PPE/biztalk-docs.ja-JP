---
redirect_url: /biztalk/core/feature-pack-add-build-release-definitions/
redirect_document_id: true
ROBOTS: NOINDEX
title: BizTalk Server ソリューションまたはプロジェクトをデプロイする、Visual Studio Team Services の構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2555712a-dfe4-420e-9a61-1d1a6d98c322
caps.latest.revision: 6
author: tordgladnordahl
ms.author: tonordah
manager: anneta
ms.openlocfilehash: 7178f85bce4087e5bc740810050817676a6c8996
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992475"
---
# <a name="configure-visual-studio-team-services-to-deploy-biztalk-server-solutions-or-projects"></a>BizTalk Server ソリューションまたはプロジェクトをデプロイする、Visual Studio Team Services の構成します。
自動的に展開する VSTS セットアップ[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]プロジェクト。 

**以降で[!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** 、自動的にビルドすることができます、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]ソリューションが Visual Studio Team Services (VSTS) を使用します。 

このトピックを設定して、BizTalk の自動展開を使用する Visual Studio Team Service (VSTS) を構成する方法を示します。 

> [!IMPORTANT]
> VSTS エージェントは、1 つにのみインストールできます[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]グループ。 

## <a name="prerequisites"></a>前提条件

* インストール[Feature Pack 1](https://www.microsoft.com/download/details.aspx?id=55100)で、 [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]
* 一部のエクスペリエンスと VSTS での定義の作成と操作の情報が提供します。 VSTS にまったく新しい場合は、これらの優れたリソースがあります。 

  [Visual Studio Team Services の概要](https://www.visualstudio.com/docs/overview)  
  [初心者の CI/CD](https://www.visualstudio.com/docs/build/get-started/ci-cd-part-1)
  

## <a name="create-a-vsts-account-and-create-a-definition"></a>VSTS アカウントを作成し、定義を作成します。

1. Web ブラウザーでに移動、 [Visual Studio online プロファイル](https://app.vsaex.visualstudio.com/go/profile)、サインイン、および選択を**新しいアカウントを作成する**:

    ![[新しいアカウントを作成する]](../core/media/create-a-new-account.png)

2. アカウントの名前を入力、優先されるソース コード リポジトリを選択および選択**続行**:

    ![新しいプロジェクトを作成する](../core/media/create-a-new-project.png)

3. 新しいアカウントを作成し、サイトのような`https://YourAccountName.visualstudio.com/MyFirstProject`が開きます。
    
4. インストール、 [BizTalk アプリケーションのデプロイ サービス](https://marketplace.visualstudio.com/items?itemName=ms-biztalk.deploy-biztalk-application)作成したアカウントにします。

    ![新しいリリースをビルドします。](../core/media/build-new-release.png)

5. いくつかのメッセージを取得する可能性があります。 続行することを確認します。 VSTS でプロジェクトにサインインしていることを確認します。

6. 選択**ビルドとリリース**、作成し、**新規**ビルド定義。

    ![ビルドとリリースを選択します。](../core/media/select-build-and-release.png)

    > [!TIP]
    > あなたは仕事を必ず`https://YourAccountName.visualstudio.com/MyFirstProject`します。 それ以外の場合、**新規**または**新しい定義**ボタンが不要であります。 
    
7. 選択、 **Visual Studio**テンプレート、および選択**次**:

    ![Visual studio を選択し、[次へ] をクリックしてください](../core/media/select-visual-studio-and-click-next.png)

8. 設定を確認し、選択**作成**です。

9. 不要な手順を削除します。 このチュートリアルでは、次のように削除できます。 
10. NuGet の復元
11. テスト アセンブリ
12. シンボル パスを発行します。 

      ![削除の手順は必要ありません。](../core/media/delete-steps-not-needed.png)

13. **省略可能な**します。 継続的インテグレーション (CI) を有効にする場合は、選択**トリガー**チェックし、メニューで**継続的インテグレーション (CI)** します。

次に、エージェントをインストール、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]します。 

## <a name="install-the-agent"></a>エージェントをインストールします。

ソリューションが機能するには、ローカル コンピューターにプライベートの Windows エージェントを有効にします。 忘れないでください**1 つのみで、エージェントをインストールする必要があります[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]グループ**します。 

1. 定義に、選択、**全般**(上部) にあるタブ。
2. **既定のエージェント キュー**プロパティを選択、**既定**一覧からエージェント。 
3. 選択**管理**横に、**既定のエージェント キュー**プロパティ。 新しいブラウザー タブが開きます。

    ![新しい管理エージェントを作成します。](../core/media/create-new-management-agent.png)

4. 左側のウィンドウで、既定のキューが選択されます。 完了したら、オンラインで、エージェントが既に表示されている場合。 エージェントをインストールし、実行があります。 

    エージェントが表示されない場合は選択し、**エージェントのダウンロード**のインストールを続行し、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]します。 **移動して[Windows エージェントを展開](https://www.visualstudio.com/docs/build/actions/agents/v2-windows)完全な手順について**エージェントをインストールして、エージェントを開始します。 

    > [!IMPORTANT]
    > すべての手順に従う[Windows エージェントを展開](https://www.visualstudio.com/docs/build/actions/agents/v2-windows)します。 この手順は省略しないでください。 

5. 既定のエージェントで**オンライン**に戻り、**全般**定義に、タブを確認します**既定**が選択されている、 **既定のエージェントキュー**.
6. **保存**と**新しいビルドをキュー**します。

次に、BizTalk Server アプリケーションの展開の定義を作成します。

## <a name="create-the-biztalk-deployment-definition"></a>BizTalk 展開の定義を作成します。

1. 選択、**ビルド**] タブで [**すべて定義**、選択と**新規**:

    ![新しいリリース定義を作成します。](../core/media/create-new-release-defintion.png)

2. 選択、**空**テンプレート、および選択**次**:

    ![空のテンプレートから新しい定義を作成します。](../core/media/create-new-defintion-from-an-empty-template.png)

3. 選択、**リポジトリ**ソースと**ブランチ**定義については、します。
4. **省略可能な**します。 選択**継続的インテグレーション**します。
5. 選択、**既定**エージェントを選択し、キューの一覧から**作成**です。
6. **ビルド ステップの追加**を選択、 **BizTalk Server アプリケーションの展開**タスク、および選択**追加**します。 **閉じる**タスク カタログ。

    ![追加する新しい定義の展開](../core/media/add-new-deploy-definition.png)

7. 選択、**操作名**を使用します。
    * **新しい BizTalk アプリケーションを作成する**新しいアプリケーションをデプロイします。 場合、アプリケーション既に存在は、新しいアプリケーションをインストールし、現在のアプリケーション (完全停止) をアンインストールします。 継続的インテグレーションを有効にするでは、リポジトリで更新されるときに、そのアプリケーションが自動的に再します。
    * **既存の BizTalk アプリケーションを更新**など、変更を追加します**スキーマ**を既に実行されているアプリケーションにします。 アプリケーションの完全な再デプロイは必要ありません。
8. 入力、**アプリケーション名**で、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]環境。
9. **デプロイ パッケージのパス**リポジトリに zip ファイルへのパスを選択します。
10. 選択**トリガー**メニューから、有効にする**継続的インテグレーション**、正しい選択と**ブランチ**ビルドの。
11. 選択**保存**:

    ![新しいビルド定義を保存します。](../core/media/save-the-new-build-definition.png)

12. 新しい名前**定義**、し、正しいパスを設定します。 
13. 定義が保存されると、選択**新しいビルドをキュー**します。 次に、選択、**キュー エージェント**コミットにコメントを追加します。
