---
title: インストールし、管理 REST Api の構成 |Microsoft Docs
description: BizTalk Server の Feature pack の管理データ REST Api を使用して、BizTalk 環境のアイテムをクエリします。
ms.custom: fp1
ms.date: 02/25/2019
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
ms.openlocfilehash: 680b7390462a7a64d3064f621b2011952ba2551c
ms.sourcegitcommit: 0e14c3e018b091d81d0e4a68fafc10f6e31697e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/26/2019
ms.locfileid: "56828567"
---
# <a name="install-and-configure-the-management-rest-apis-in-biztalk-server"></a>インストールし、BizTalk Server での管理 REST Api の構成

## <a name="what-are-management-data-apis"></a>管理データ Api とは
管理データの Api は、リモートで更新、追加、および内の各アイテムの状態を照会できるエンドポイント、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]環境。 エンドポイントは、REST を使用して、swagger 定義に追加されます。 

**以降で[!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** 、これらの REST Api とその swagger 定義をインストールする Windows PowerShell スクリプトがあります。 これらの Api は、ポート、オーケストレーション、パートナー、契約、パイプライン、および詳細をリモートで管理する REST 呼び出しを行います。 

利用可能な Api、および実行できる内容を確認するを参照してください[機能パックの REST API リファレンス](https://docs.microsoft.com/rest/api/biztalk/?view=rest-biztalk-2016)します。

## <a name="prerequisites"></a>前提条件
* インストール[Feature Pack 2](https://aka.ms/bts2016fp2)で、 [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]

* IIS をインストール、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]します。 開き、BizTalk Server で IIS がインストールされていることを確認します。**インターネット インフォメーション サービス マネージャー**します。 

  ほとんどの[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]環境では、IIS が既にインストールされています。 参照してください[BizTalk Server 2016 のハードウェアおよびソフトウェア](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)します。 

## <a name="step-1-install-the-rest-apis"></a>手順 1:REST Api をインストールします。

1. Windows PowerShell を管理者として実行 (**開始**メニュー > 型**PowerShell** > を右クリックして >**管理者として実行**)。 
2. BizTalk インストール フォルダーに移動して (たとえば、入力: `cd 'C:\Program Files (x86)\Microsoft BizTalk Server 2016\'`)。
3. 次のテキストで置換`Default Web Site`、 `mgmtServiceAppPool`、 `domain/user`、 `password`、および`domain\group`の値。

    ```Powershell
    FeaturePack.ConfigureServices.ps1 -Service management -WebSiteName '<Default Web Site>' -ApplicationPool <mgmtServiceAppPool> -ApplicationPoolUser <domain>\<user> -ApplicationPoolUserPassword <password> -AuthorizationRoles '<domain>\<group>, <domain>\<group>'
    ```

    次の例では使用して、 `Default Web Site`、という名前のアプリケーション プールを作成`RESTAppPool`、として appPool を実行、`bootcampbts2016\btsservice`アカウントを使用して`BIZTALK-serviceacct`し、ユーザー アカウントのパスワードとして、BizTalk Server 管理者グループのアクセス許可。 次を入力してください、周囲の値にスペースが引用符など、1 つ。 

    ```Powershell
    FeaturePack.ConfigureServices.ps1 -Service management -WebSiteName 'Default Web Site' -ApplicationPool RESTAppPool -ApplicationPoolUser bootcampbts2016\btsservice -ApplicationPoolUserPassword  BIZTALK-serviceacct -AuthorizationRoles 'BOOTCAMPBTS2016\BizTalk Server Administrators'
    ```

    完了すると、 **BizTalkManagementService** IIS 内でアプリケーションを作成します。  
    ![BizTalkManagementService アプリケーション](../core/media/biztalkmanagementservice-apppool.png)

4. 参照するには、動作していることを確認するに`http://localhost/BizTalkManagementService/swagger`します。 サインイン、前の手順で入力した domain \group のメンバーであるアカウントでサインインを求められるかどうか (`-AuthorizationRoles 'BOOTCAMPBTS2016\BizTalk Server Administrators'`)。 

> [!WARNING]
> IIS で BizTalkManagementService アプリケーションでは、web.config ファイルを使用します。 Web.config 内の要素**大文字と小文字は**します。 Windows PowerShell スクリプトを実行するときに必ずに正しい文字を入力する`-AuthorizationRoles`値。 ケースのことを確認していない場合は、次に確認する簡単な方法を示します。 
> 
> 1. 開いている**コンピュータの管理**、展開と**ローカル ユーザーとグループ**します。
> 2. 選択**グループ**、まで下へスクロールし、 **SQLServer.** グループ。 
> 3. 次の例では、次に注意してください。 **BOOTCAMPBTS2016**すべて大文字にします。 すべて大文字を表示する場合は、すべて大文字でコンピューター名を入力します。 
> 
> ![すべて大文字でコンピューター名には](../core/media/groups-case.png)

できたので、REST Api は、IIS を介して公開される、これらは、アクセスし、その他のアプリケーションによって実行されることができます。 [機能パックの REST API リファレンス](https://docs.microsoft.com/rest/api/biztalk/?view=rest-biztalk-2016)Api を一覧表示されます。

手動で更新することでアクセスを持っているユーザーを変更することができます、 **web.config**ファイル。 これは、管理アプリケーションのルート フォルダーにします。 たとえば、すべてのユーザーを許可するのには、次のアクセス、swagger を使用して出力。 

```
<authorization>
   <allow users="*" />
</authorization>
```

## <a name="step-2-test-the-apis"></a>手順 2:Api をテストします。

1. BizTalk Server を参照`http://localhost/BizTalkManagementService/swagger`します。

2. スクロールして**ホスト**を選択し、**表示/非表示**します。 Get-command; があります。この行をクリックします。  
![すべてのホストを取得します。](../core/media/managment-rest-apis-hosts-get.png)

3. 詳細が表示されます。 選択**試して**:  
![お試しください](../core/media/managment-rest-apis-hosts-tryitout.png)

4. 応答本文には、すべてのホストが返されます。  
![応答](../core/media/managment-rest-apis-hosts-response.png)

> [!NOTE]
> 参照する場合`http://localhost/BizTalkManagementService`、500 エラーが発生する必要があります。 これは良いことです。 追加するだけで`/swagger`URL の末尾に利用可能な REST Api が表示されます。 


## <a name="see-also"></a>関連項目
 [Feature Pack を構成します。](../core/configure-the-feature-pack.md)