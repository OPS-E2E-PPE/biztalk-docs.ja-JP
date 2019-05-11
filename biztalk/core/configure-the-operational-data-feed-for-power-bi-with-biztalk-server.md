---
title: Power BI を有効にする |Microsoft Docs
description: Power BI テンプレートを BizTalk Server の Feature Pack のインストールします。
ms.custom: fp1
ms.date: 6/26/2018
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fe6d3a97-c7c0-4147-baa9-ee12f93248eb
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1ba5e0944c8b816a4800618940048b3e427143ad
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391437"
---
# <a name="configure-the-power-bi-operational-data-feed-in-biztalk-server"></a>Power BI にオペレーション データ フィードでは、BizTalk Server の構成します。

**以降で[!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** 追跡を指定すると、Power BI テンプレートを使用して Power BI に送信します。 または、独自に作成します。 

## <a name="what-is-operational-data"></a>オペレーション データとは
オペレーション データは、インスタンスとで転送されるメッセージについては、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]環境。 オペレーション データ フィードは、同じデータのグループのハブを見て取得[!INCLUDE[btsBizTalkServerAdminConsoleui_md](../includes/btsbiztalkserveradminconsoleui-md.md)]します。 データにアクセスし、Power BI などの視覚化ツールを使用してクエリを実行します。 

フィードには、次のデータ テーブルが含まれています。
* アプリケーション データ
* AS2 状態レコード
* バッチ処理の情報
* インスタンス情報
* インターチェンジの集計レコード
* インターチェンジの状態レコード
* メッセージ
* サブスクリプション
* 追跡したイベント
* トランザクションのレポート
* トランザクション セット

> [!TIP]
> [PowerBI.com](http://powerbi.microsoft.com)優れたリソースを理解し、Power BI の詳細について説明します。

## <a name="prerequisites"></a>前提条件
* ダウンロードしてインストール[Power BI Desktop](https://powerbi.microsoft.com/desktop/)にネットワーク アクセス権を持つ任意のコンピューターで、 [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]
* インストール[Feature Pack 2](https://aka.ms/bts2016fp2)、またはそれ以降の機能パックを [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]
* IIS をインストール、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]します。 ほとんどの[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]環境では、IIS が既にインストールされています。 参照してください[BizTalk Server 2016 のハードウェアおよびソフトウェア](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)します。 開くことで IIS がインストールされていることを確認します。**インターネット インフォメーション サービス マネージャー**します。 
* 任意。 インストールし、構成、 [Power BI Gateway](https://powerbi.microsoft.com/gateway/)接続[PowerBI.com](http://powerbi.microsoft.com)オンプレミスの BizTalk Server とします。 オンプレミスの BizTalk Server を使用していない場合は、ゲートウェイを必要はありません。

## <a name="step-1-enable-operational-data"></a>手順 1:オペレーション データを有効にします。

1. Windows PowerShell を管理者として実行 (**開始**メニューで、「 **PowerShell**、を右クリックしてし選択、**管理者として実行**)。 
2. BizTalk インストール フォルダーに移動して (たとえば、入力: `cd 'C:\Program Files (x86)\Microsoft BizTalk Server 2016\'`)。
3. 次のテキストで置換`Default Web Site`、 `operationalDataServiceAppPool`、 `domain\user`、 `password`、および`domain\group`の値。

    ```Powershell
    FeaturePack.ConfigureServices.ps1 -Service operationaldata -WebSiteName '<Default Web Site>' -ApplicationPool <operationalDataServiceAppPool> -ApplicationPoolUser <domain>\<user\> -ApplicationPoolUserPassword <password> -AuthorizationRoles '<domain>\<group1\>, <domain>\<group2\>, <domain>\<user\>, <domain>\<user2\>'
    ```

   * **サービス**:サービスを構成できます (**OperationalData** Power BI 用)
   * **WebSiteName**:サービスをホストする既存の IIS web サイト。 既定値は**既定の Web サイト**します。
   * **ApplicationPool**:サービスによって使用されるアプリケーション プール。 存在する場合、新しいものは作成されません。 既定値は**DefaultAppPool**します。
   * **ApplicationPoolUser**:このユーザー id として実行するアプリケーション プールを構成します。 BizTalk Server Operator、またはより高い権限が必要です。
   * **ApplicationPoolUserPassword**:ApplicationPoolUser のパスワード
   * **AuthorizationAccount**:承認済みのグループまたはこのサービスを使用できるユーザーの一覧

     次の例では使用して、 `Default Web Site`、という名前のアプリケーション プールを作成`PowerBIAppPool`、として appPool を実行、`bootcampbts2016\btsservice`アカウントを使用して`BIZTALK-serviceacct`し、ユーザー アカウントのパスワードとして、`BizTalk Server Administrators`アクセス許可をグループ化します。 次を入力してください、周囲の値にスペースが引用符など、1 つ。 

     ```Powershell
     FeaturePack.ConfigureServices.ps1 -Service operationaldata -WebSiteName 'Default Web Site' -ApplicationPool PowerBIAppPool -ApplicationPoolUser bootcampbts2016\btsservice -ApplicationPoolUserPassword  BIZTALK-serviceacct -AuthorizationRoles 'BOOTCAMPBTS2016\BizTalk Server Administrators'
     ```

     完了したら、IIS 内で BizTalkOperationalDataService アプリケーションが作成されます。  
     ![BizTalkMOperationalDataServer アプリケーション](../core/media/biztalkmanagementservice-apppool.png)


4. 参照するには、動作していることを確認するに`http://localhost/BizTalkOperationalDataService`します。 

    サインイン、前の手順で入力した domain \group のメンバーであるアカウントでサインインを求められるかどうか (`-AuthorizationRoles 'BOOTCAMPBTS2016\BizTalk Server Administrators'`)。 

    開くか保存 BizTalkOperationalDataService.json メッセージが表示されたら、インストールが完了します。 ローカルに保存してメモ帳などの内容を表示する Visual Studio で開きます。 

> [!WARNING]
> IIS で BizTalkOperationalDataService アプリケーションでは、web.config ファイルを使用します。 Web.config 内の要素**大文字と小文字は**します。 Windows PowerShell スクリプトを実行するときに必ずに正しい文字を入力する`-AuthorizationRoles`値。 ケースのことを確認していない場合は、次に確認する簡単な方法を示します。 
> 
> 1. 開いている**コンピュータの管理**、展開と**ローカル ユーザーとグループ**します。
> 2. 選択**グループ**、まで下へスクロールし、 **SQLServer.** グループ。 
> 3. 次の例では、次に注意してください。 **BOOTCAMPBTS2016**すべて大文字にします。 すべて大文字を表示する場合は、すべて大文字でコンピューター名を入力します。 
> 
> ![すべて大文字でコンピューター名には](../core/media/groups-case.png)

## <a name="step-2-use-the-template-in-power-bi"></a>手順 2:Power BI でテンプレートを使用します。

1. ダウンロードしてインストール、 [Power BI Desktop](https://powerbi.microsoft.com/desktop/) BizTalk Server にします。 これは省略可能なを開くを選択できます。 職場または学校のアカウントがあれば、Power BI へのアクセスがあります。 そのアカウントでサインインしてみてください。 またはへのサインアップ後に無料で試すことができます。 
2. 開く、`\Program Files (x86)\Microsoft BizTalk Server 2016\OperationalDataService`フォルダー、およびオープン、`BizTalkOperationalData.pbit`ファイル。  
![開いている pbit ファイル](../core/media/operational-data-pbit.png)

3. Power BI desktop が開き、URL が要求されます。 入力、 `http://localhost/<yourWebSite>` OData フィード用に作成した URL。 たとえば、`http://localhost/BizTalkOperationalDataService` と入力します。 URL は、次のような検索します。  
![URL を入力します](../core/media/operational-data-url.png)

4. 選択**ロード**します。 ウィンドウは、読み込みを BizTalkOperationalDataService.json ファイル内の別の oData ソースに接続します。 完了したら、ダッシュ ボードは、環境に関する詳細を表示します。

## <a name="couldnt-authenticate"></a>認証できませんでした。
表示された場合`couldn't authenticate with the credentials provided`メッセージは次のように、アプリケーション プール id は、BizTalk Server データベースに十分なアクセスがない可能性があります。 変更できます IIS 内でアプリケーション プール id 多くの特権を持つアカウントに可能性があります (これは、ローカル管理者特権を持つ) サインイン ユーザー アカウント。 

![指定された資格情報で認証できませんでした。](../core/media/operational-data-authentication-error.png)

## <a name="do-more"></a>さらに活用します。
これは、ほんの始まりにすぎません。 Power BI では、オンプレミスの BizTalk Server にインストールできるゲートウェイもあります。 ゲートウェイを使用して、ダッシュ ボードを発行することができます、リアルタイムのデータを取得、ダッシュ ボードを更新するスケジュールを作成および。 次のブログは、次の手順の詳細を示す良い仕事をします。 

* [Power BI – 詳細な構成手順で BizTalk のオペレーション データを発行する方法](https://blog.sandro-pereira.com/2017/05/07/biztalk-server-2016-feature-pack-1-how-to-publish-biztalk-operational-data-power-bi-step-by-step-configuration-part-3/)

[ガイド付き学習](https://powerbi.microsoft.com/guided-learning/)も甲斐の Power BI に関する詳細、およびすべてのことを実行することができます。 

## <a name="see-also"></a>関連項目

[Power BI を詳細します。](https://www.powerbi.com)  
[Feature Pack を構成します。](../core/configure-the-feature-pack.md)
