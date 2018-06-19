---
title: インストールし、管理 REST Api の構成 |Microsoft ドキュメント
description: BizTalk server 用 Feature Pack の管理データの REST Api を使用して BizTalk 環境内の成果物をクエリします。
ms.custom: fp1
ms.date: 11/06/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 39442756-5886-4ddd-b700-3800a237de4a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c207b0aca5f2673e615167f75f7f1c7c3fb0e042
ms.sourcegitcommit: f65e8ed2b8c18cded26b9d60868fb6a56bcc1205
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
ms.locfileid: "25497899"
---
# <a name="install-and-configure-the-management-rest-apis-in-biztalk-server"></a>インストールし、BizTalk Server での管理 REST Api の構成

## <a name="what-are-management-data-apis"></a>管理データ Api とは
管理データの Api は、エンドポイントでのリモート更新、追加、および内の各アイテムの状態を照会することのできる、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]環境。 エンドポイントは追加され、残りの部分を使用して swagger 定義が付属します。 

**以降で[!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** 、これらの REST Api とその swagger 定義をインストールする Windows PowerShell スクリプトがあります。 これらの Api は、ポート、オーケストレーション、パートナー、契約、パイプライン、および詳細をリモートで管理する REST 呼び出しを行います。 

## <a name="prerequisites"></a>前提条件
* インストール[Feature Pack 2](https://aka.ms/bts2016fp2)で、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]

* IIS をインストール、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]です。 ほとんどの[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]環境では、IIS が既にインストールされています。 参照してください[Hardware and Software Requirements for BizTalk Server 2016](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)です。 開き、BizTalk Server で IIS がインストールされていることを確認**インターネット インフォメーション サービス マネージャー**です。 

## <a name="step-1-install-the-rest-apis"></a>手順 1: REST Api をインストールします。

1. Windows PowerShell を管理者として実行 (**開始**メニューで、「 **PowerShell**、右クリックし、、選択**管理者として実行**)。 
2. BizTalk のインストール フォルダーに移動 (たとえば、入力: `cd 'C:\Program Files (x86)\Microsoft BizTalk Server 2016\'`)。
3. 次のテキストで置き換えます`Default Web Site`、 `mgmtServiceAppPool`、 `domain/user`、 `password`、および`domain\group`実際の値にします。

    ```Powershell
    FeaturePack.ConfigureServices.ps1 -Service management -WebSiteName '<Default Web Site>' -ApplicationPool <mgmtServiceAppPool> -ApplicationPoolUser <domain>\<user> -ApplicationPoolUserPassword <password> -AuthorizationRoles '<domain>\<group>, <domain>\<group>'
    ```

    次の例では使用して、 `Default Web Site`、というアプリケーション プールを作成して`RESTAppPool`、として、アプリケーション プールを実行、`bootcampbts2016\btsservice`アカウントを使用して`BIZTALK-serviceacct`BizTalk Server 管理者グループのアクセス許可を与える、ユーザー アカウントのパスワードとして。 次を入力するようにし、スペースを含む周囲の値を引用符で、1 つを含みます。 

    ```Powershell
    FeaturePack.ConfigureServices.ps1 -Service management -WebSiteName 'Default Web Site' -ApplicationPool RESTAppPool -ApplicationPoolUser bootcampbts2016\btsservice -ApplicationPoolUserPassword  BIZTALK-serviceacct -AuthorizationRoles 'BOOTCAMPBTS2016\BizTalk Server Administrators'
    ```

    完了すると、 **BizTalkManagementService** IIS 内でアプリケーションを作成します。  
    ![BizTalkManagementService アプリケーション](../core/media/biztalkmanagementservice-apppool.png)

4. 動作していることを確認する」を参照`http://localhost/BizTalkManagementService/swagger`です。 かどうかサインイン、前の手順で入力した domain \group のメンバーであるアカウントでサインインするように求められます (`-AuthorizationRoles 'BOOTCAMPBTS2016\BizTalk Server Administrators'`)。 

> [!WARNING]
> IIS で BizTalkManagementService アプリケーションは、web.config ファイルを使用します。 Web.config 内の要素**大文字と小文字は**します。 ので、Windows PowerShell スクリプトを実行するときに、必ずに正しい文字を入力する`-AuthorizationRoles`値。 ケースのことを確認していない場合は、確認する簡単な方法を次に示します。 
> 
> 1. 開いている**コンピューターの管理**、展開と**ローカル ユーザーとグループ**です。
> 2. 選択**グループ**、下方向にスクロールし、 **SQLServer.** グループ。 
> 3. 次の例では、次に注意してください。 **BOOTCAMPBTS2016**すべて大文字にします。 すべて大文字を表示する場合は、すべて大文字でコンピューター名を入力します。 
> 
> ![すべて大文字では、コンピューター名です。](../core/media/groups-case.png)

これで、REST Api は、IIS を通じて公開される、アクセスおよびできます他のアプリケーションによって実行します。 

手動で更新することによってアクセスを持っているユーザーを変更することができます、 **web.config**管理アプリケーションのルート フォルダーにあるファイルです。 たとえばを使用して、swagger へのアクセスを許可するには、次の出力。 

```
<authorization>
   <allow users="*" />
</authorization>
```

## <a name="step-2-test-the-apis"></a>手順 2: テスト Api

1. BizTalk Server を参照`http://localhost/BizTalkManagementService/swagger`です。

2. スクロール**ホスト**を選択して**表示/非表示**です。 GET コマンド。この行をクリックします。  
![すべてのホストを取得します。](../core/media/managment-rest-apis-hosts-get.png)

3. 詳細情報が表示されます。 選択**お試しください**:  
![お試しください](../core/media/managment-rest-apis-hosts-tryitout.png)

4. 応答本文には、すべてのホストが返されます。  
![応答](../core/media/managment-rest-apis-hosts-response.png)

> [!NOTE]
> 参照する場合は`http://localhost/BizTalkManagementService`、500 エラーが発生する必要があります。 良いことです。 追加するだけで`/swagger`して、URL の末尾に使用できる REST Api が表示されます。 


## <a name="see-also"></a>参照
 [この機能パックを構成します。](../core/configure-the-feature-pack.md)