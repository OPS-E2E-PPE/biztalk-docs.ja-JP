---
redirect_url: /biztalk/core/feature-pack-add-build-release-definitions/
redirect_document_id: true
ROBOTS: NOINDEX
title: BizTalk Server ソリューションまたはプロジェクトを展開する Visual Studio Team Services の構成 |Microsoft ドキュメント
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
ms.openlocfilehash: 95d8e9fc274793471335fc03bc38c82c1b3e3469
ms.sourcegitcommit: a0165ec2f1e8b58545638666b7bfa2bf440036fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/09/2017
ms.locfileid: "24054586"
---
# <a name="configure-visual-studio-team-services-to-deploy-biztalk-server-solutions-or-projects"></a>BizTalk Server ソリューションまたはプロジェクトを展開する Visual Studio Team Services を構成します。
自動的に展開する VSTS セットアップ[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]プロジェクト。 

**以降で[!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** 、自動的にビルドすることができます、 [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] Visual Studio Team Services (VSTS) を使用したソリューションです。 

このトピックを設定して、BizTalk の自動展開を使用する Visual Studio Team サービス (VSTS) を構成する方法を示します。 

> [!IMPORTANT]
> VSTS エージェントは、1 つにのみインストールできます[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]グループにします。 

## <a name="prerequisites"></a>前提条件

* インストール[機能パック 1](https://www.microsoft.com/download/details.aspx?id=55100)で、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]
* 一部のエクスペリエンスと知識 VSTS 内の定義の作成と操作をします。 VSTS をまったく新しい場合は、これら優れたリソースがあります。 

  [Visual Studio Team Services の概要](https://www.visualstudio.com/docs/overview)  
  [初心者の CI/CD](https://www.visualstudio.com/docs/build/get-started/ci-cd-part-1)
  

## <a name="create-a-vsts-account-and-create-a-definition"></a>VSTS アカウントを作成し、定義を作成します。

1. Web ブラウザーでに移動、 [Visual Studio online プロファイル](https://app.vsaex.visualstudio.com/go/profile)、サインインし、選択、**新しいアカウントを作成**:

    ![[新しいアカウントを作成する]](../core/media/create-a-new-account.png)

2. アカウントの名前を入力して、優先されるソース コード リポジトリを選択して、選択**続行**:

    ![新しいプロジェクトを作成する](../core/media/create-a-new-project.png)

3. 新しいアカウントを作成すると、およびサイトのような`https://YourAccountName.visualstudio.com/MyFirstProject`が開きます。
    
4. インストール、 [BizTalk アプリケーションの配置サービス](https://marketplace.visualstudio.com/items?itemName=ms-biztalk.deploy-biztalk-application)作成したアカウントにします。

    ![新しいリリースをビルドします。](../core/media/build-new-release.png)

5. いくつかのメッセージを取得する可能性があります。 続行することを確認します。 VSTS でプロジェクトにサインインしていることを確認します。

6. 選択**ビルドとリリース**、作成して、**新規**ビルド定義。

    ![ビルドとリリースを選択します。](../core/media/select-build-and-release.png)

    > [!TIP]
    > しているかどうかを必ず`https://YourAccountName.visualstudio.com/MyFirstProject`です。 それ以外の場合、**新規**または**新しい定義**ボタンできない可能性がありますがあります。 
    
7. 選択、 **Visual Studio**テンプレート、および選択**次**:

    ![Visual studio を選択し、[次へ] をクリックしてください](../core/media/select-visual-studio-and-click-next.png)

8. 設定を確認し、選択**作成**です。

9. 不要、手順を削除します。 このチュートリアルでは、次のように削除できます。 
* NuGet の復元
* テスト アセンブリ
* シンボル パスを発行します。 

    ![手順は必要ありませんの削除します。](../core/media/delete-steps-not-needed.png)

10. **省略可能な**します。 継続的な統合 (CI) を有効にする場合は、選択**トリガー**メニューのおよびチェックで**継続的インテグレーション (CI)** です。

次に、エージェントをインストール、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]です。 

## <a name="install-the-agent"></a>エージェントをインストールします。

ソリューションが機能するには、ローカル コンピューター上のプライベート Windows エージェントを有効にします。 思い出してください **、エージェントは、1 つだけにインストールする必要があります[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]グループで**です。 

1. 定義に、選択、**全般**(上部) のタブです。
2. **既定のエージェント キュー**プロパティを選択、**既定**一覧からエージェントです。 
3. 選択**管理** の横に、**既定のエージェント キュー**プロパティです。 新しいブラウザー タブが表示されます。

    ![新しい管理エージェントを作成します。](../core/media/create-new-management-agent.png)

4. 左側のウィンドウで、既定のキューが選択されます。 完了したら、オンラインにして、エージェントが既に表示されている場合。 エージェント インストールし、実行があります。 

    エージェントが表示されない場合を選択し、**ダウンロード エージェント**のインストールを続行し、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]です。 **移動して[Windows 上のエージェントを展開](https://www.visualstudio.com/docs/build/actions/agents/v2-windows)手順については、完全な**エージェントをインストールしてエージェントを起動します。 

    > [!IMPORTANT]
    > すべての手順に従う[Windows 上のエージェントを展開](https://www.visualstudio.com/docs/build/actions/agents/v2-windows)です。 この手順は省略しないでください。 

5. 既定のエージェントで**オンライン**に戻り、**全般**タブで、定義し、確認**既定**が選択されて、**既定のエージェント キュー**.
6. **保存**と**新しいビルドをキュー**です。

次に、BizTalk Server アプリケーションの展開の定義を作成します。

## <a name="create-the-biztalk-deployment-definition"></a>BizTalk 展開の定義を作成します。

1. 選択、**ビルド**] タブで [**すべて定義**を選択して**新規**:

    ![新しいリリース定義を作成します。](../core/media/create-new-release-defintion.png)

2. 選択、**空**テンプレート、および選択**次**:

    ![空のテンプレートから新しい定義を作成します。](../core/media/create-new-defintion-from-an-empty-template.png)

3. 選択、**リポジトリ**ソースと**ブランチ**定義については、します。
4. **省略可能な**します。 選択**継続的インテグレーション**です。
5. 選択、**既定**を選択し、キューの一覧からエージェント**作成**です。
6. **ビルド ステップの追加**、select、 **BizTalk Server アプリケーションの展開**タスク、および選択**追加**です。 **閉じる**タスク カタログ。

    ![追加の定義を新しい展開](../core/media/add-new-deploy-definition.png)

7. 選択、**操作名**を使用します。
    * **新しい BizTalk アプリケーションを作成する**新しいアプリケーションを展開します。 場合アプリケーション既に exsist は、現在のアプリケーション (完全停止) をアンインストールし、新しいアプリケーションをインストールします。 継続的インテグレーションが有効になっているでは、リポジトリで更新されるときに、そのアプリケーションが自動的に再です。
    * **既存の BizTalk アプリケーションを更新**など、変更を追加**スキーマ**を既に実行中のアプリケーションにします。 アプリケーションの完全再展開は必要ありません。
8. 入力、**アプリケーション名**で、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]環境。
9. **展開パッケージのパス**リポジトリ内の zip ファイルへのパスを選択します。
10. 選択**トリガー**メニューから、有効にする**継続的インテグレーション**、正しい選択と**ブランチ**ビルドのです。
11. 選択**保存**:

    ![新しいビルド定義を保存します。](../core/media/save-the-new-build-definition.png)

12. 新しい名前を付けます**定義**、し、正しいパスを設定します。 
13. 定義が保存されると、選択**新しいビルドをキュー**です。 次に、選択、**キュー エージェント**コミットにコメントを追加します。
