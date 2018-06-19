---
title: Power BI を有効にする |Microsoft ドキュメント
description: Power BI テンプレートを BizTalk Server 用 Feature Pack のインストールします。
ms.custom: fp1
ms.date: 11/07/2017
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
ms.openlocfilehash: 585927b494f51ddd3ab7abd0503df7586c30b041
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25969472"
---
# <a name="configure-the-power-bi-operational-data-feed-in-biztalk-server"></a>Power BI の運用データを BizTalk Server でフィードを構成します。

**以降で[!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** 追跡を指定すると、Power BI テンプレートを使用して Power BI に送信します。 または、独自に作成します。 

## <a name="what-is-operational-data"></a>オペレーション データとは
オペレーション データは、インスタンスおよび経由でやり取りされるメッセージに関する情報、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]環境。 オペレーション データ フィードは、同じデータのグループ ハブを見て取得[!INCLUDE[btsBizTalkServerAdminConsoleui_md](../includes/btsbiztalkserveradminconsoleui-md.md)]です。 データにアクセスされ、Power BI を含む、視覚化ツールを使用してクエリします。 

フィードには、次のデータ テーブルが含まれています。
* アプリケーション データ
* AS2 状態レコード
* バッチ処理の情報
* インスタンス情報
* インターチェンジの集計レコード
* インターチェンジの状態レコード
* メッセージ
* サブスクリプション
* 追跡イベント
* トランザクションのレポート
* トランザクション セット

> [!TIP]
> [PowerBI.com](http://powerbi.microsoft.com)を理解し、Power BI の詳細です。

## <a name="prerequisites"></a>前提条件
* ダウンロードしてインストール[Power BI Desktop](https://powerbi.microsoft.com/desktop/)ネットワーク アクセス権を持つ任意のコンピューターで、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]
* インストール[Feature Pack 2](https://aka.ms/bts2016fp2)で、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]
* IIS をインストール、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]です。 ほとんどの[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]環境では、IIS が既にインストールされています。 参照してください[Hardware and Software Requirements for BizTalk Server 2016](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)です。 開くことによって IIS がインストールされていることを確認**インターネット インフォメーション サービス マネージャー**です。 
* 省略可。 インストールし、構成、 [Power BI Gateway](https://powerbi.microsoft.com/gateway/)接続[PowerBI.com](http://powerbi.microsoft.com)内部設置型の BizTalk Server とします。 オンプレミス BizTalk Server を使用していない場合は、ゲートウェイを必要ありません。

## <a name="step-1-enable-operational-data"></a>手順 1: オペレーション データを有効にします。

1. Windows PowerShell を管理者として実行 (**開始**メニューで、「 **PowerShell**、右クリックし、、選択**管理者として実行**)。 
2. BizTalk のインストール フォルダーに移動 (たとえば、入力: `cd 'C:\Program Files (x86)\Microsoft BizTalk Server 2016\'`)。
3. 次のテキストで置き換えます`Default Web Site`、 `operationalDataServiceAppPool`、 `domain\user`、 `password`、および`domain\group`実際の値にします。

    ```Powershell
    FeaturePack.ConfigureServices.ps1 -Service operationaldata -WebSiteName '<Default Web Site>' -ApplicationPool <operationalDataServiceAppPool> -ApplicationPoolUser <domain>\<user\> -ApplicationPoolUserPassword <password> -AuthorizationRoles '<domain>\<group1\>, <domain>\<group2\>, <domain>\<user\>, <domain>\<user2\>'
    ```

    * **サービス**: サービスを構成する (**OperationalData** Power BI 用)
    * **WebSiteName**: サービスをホストする既存の IIS web サイトです。 既定値は**Default Web Site**です。
    * **ApplicationPool**: アプリケーション プールが、サービスで使用します。 存在する場合は、新しいは作成されません。 既定値は**DefaultAppPool**です。
    * **ApplicationPoolUser**: このユーザー id として実行するアプリケーション プールを構成します。 BizTalk Server Operator、またはより高い特権が必要です。
    * **ApplicationPoolUserPassword**: ApplicationPoolUser のパスワード
    * **AuthorizationAccount**: 承認済みのグループまたはこのサービスを使用するユーザーの一覧

    次の例では使用して、 `Default Web Site`、というアプリケーション プールを作成`PowerBIAppPool`、として、アプリケーション プールを実行、`bootcampbts2016\btsservice`アカウントを使用して`BIZTALK-serviceacct`により、ユーザー アカウントのパスワードとして、`BizTalk Server Administrators`アクセス許可をグループ化します。 次を入力するようにし、スペースを含む周囲の値を引用符で、1 つを含みます。 

    ```Powershell
    FeaturePack.ConfigureServices.ps1 -Service operationaldata -WebSiteName 'Default Web Site' -ApplicationPool PowerBIAppPool -ApplicationPoolUser bootcampbts2016\btsservice -ApplicationPoolUserPassword  BIZTALK-serviceacct -AuthorizationRoles 'BOOTCAMPBTS2016\BizTalk Server Administrators'
    ```

    完了したら、IIS 内で BizTalkOperationalDataService アプリケーションが作成されます。  
    ![BizTalkMOperationalDataServer アプリケーション](../core/media/biztalkmanagementservice-apppool.png)


4. 動作していることを確認する」を参照`http://localhost/BizTalkOperationalDataService`です。 

    かどうかサインイン、前の手順で入力した domain \group のメンバーであるアカウントでサインインするように求められます (`-AuthorizationRoles 'BOOTCAMPBTS2016\BizTalk Server Administrators'`)。 

    開くか BizTalkOperationalDataService.json を保存するメッセージが表示されたら、インストールが完了しました。 ローカルに保存してメモ帳または内容を表示する Visual Studio で開きます。 

> [!WARNING]
> IIS で BizTalkOperationalDataService アプリケーションは、web.config ファイルを使用します。 Web.config 内の要素**大文字と小文字は**します。 ので、Windows PowerShell スクリプトを実行するときに、必ずに正しい文字を入力する`-AuthorizationRoles`値。 ケースのことを確認していない場合は、確認する簡単な方法を次に示します。 
> 
> 1. 開いている**コンピューターの管理**、展開と**ローカル ユーザーとグループ**です。
> 2. 選択**グループ**、下方向にスクロールし、 **SQLServer.** グループ。 
> 3. 次の例では、次に注意してください。 **BOOTCAMPBTS2016**すべて大文字にします。 すべて大文字を表示する場合は、すべて大文字でコンピューター名を入力します。 
> 
> ![すべて大文字では、コンピューター名です。](../core/media/groups-case.png)

## <a name="step-2-use-the-template-in-power-bi"></a>手順 2: Power BI でのテンプレートを使用します。

1. ダウンロードしてインストール、 [Power BI Desktop](https://powerbi.microsoft.com/desktop/) BizTalk Server にします。 開くには、これはオプションを選択することができます。 職場または学校のアカウントを使っている場合は、Power BI へのアクセスがあります。 そのアカウントでサインインしてください。 または、サインアップ後無料試用できます。 
2. 開く、`\Program Files (x86)\Microsoft BizTalk Server 2016\OperationalDataService`フォルダーを開き、`BizTalkOperationalData.pbit`ファイル。  
![開いている pbit ファイル](../core/media/operational-data-pbit.png)

3. Power BI desktop が開き、URL のメッセージが表示されたら、します。 入力、 `http://localhost/<yourWebSite>` OData フィード用に作成した URL です。 たとえば、入力`http://localhost/BizTalkOperationalDataService`です。 URL は、次のようにはなります。  
![URL を入力します](../core/media/operational-data-url.png)

4. 選択**ロード**です。 ウィンドウを読み込んで BizTalkOperationalDataService.json ファイル内の別の oData ソースに接続します。 これが完了すると、ダッシュ ボードは、環境に関する詳細を示します。

## <a name="couldnt-authenticate"></a>認証できませんでした。
表示された場合`couldn't authenticate with the credentials provided`メッセージは次のように、アプリケーション プール id は、BizTalk Server データベースへの十分なアクセスを持っていない可能性があります。 変更できます IIS 内の appPool id 多くの特権を持つアカウントになる可能性があります (をローカルの管理者特権を持つ) サインイン ユーザー アカウント。 

![指定された資格情報で認証できませんでした。](../core/media/operational-data-authentication-error.png)

## <a name="do-more"></a>複数の操作を行います
これは、始まりにすぎません。 Power BI では、内部設置型 BizTalk Server にインストールできるゲートウェイもあります。 ゲートウェイを使用するには、ダッシュ ボードを発行、リアルタイムのデータを取得でき、ダッシュ ボードの更新スケジュールを作成できます。 次のブログに大変これらの手順を説明します。 

* [Power BI – 構成手順で BizTalk のオペレーション データを公開する方法](https://blog.sandro-pereira.com/2017/05/07/biztalk-server-2016-feature-pack-1-how-to-publish-biztalk-operational-data-power-bi-step-by-step-configuration-part-3/)

[ガイド付き学習](https://powerbi.microsoft.com/guided-learning/)はでも、最適な場所に Power BI に関する詳細、およびすべての処理を行うことができます。 

## <a name="see-also"></a>参照

[Power BI を詳細します。](https://www.powerbi.com)  
[この機能パックを構成します。](../core/configure-the-feature-pack.md)
