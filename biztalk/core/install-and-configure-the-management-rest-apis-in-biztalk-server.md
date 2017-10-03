---
title: "インストールし、管理 REST Api の構成 |Microsoft ドキュメント"
description: "BizTalk server 機能パック 1 で管理データの REST Api を使用して BizTalk 環境内の成果物の状態をクエリします。"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 39442756-5886-4ddd-b700-3800a237de4a
caps.latest.revision: "8"
author: tordgladnordahl
ms.author: tonordah
manager: anneta
ms.openlocfilehash: 009b3b0bb333b8f92f6235da57b0c3e9f5daca96
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="install-and-configure-the-management-rest-apis-in-biztalk-server"></a>インストールし、BizTalk Server での管理 REST Api の構成
リモートで管理 REST Api を有効にする、Windows PowerShell スクリプトを使用して、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]です。

## <a name="what-are-management-data-apis"></a>管理データ Api とは
管理データの Api は、エンドポイントでのリモート更新、追加、および内の各アイテムの状態を照会することのできる、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]環境。 エンドポイントは追加され、残りの部分を使用して Swagger 定義が付属します。 

**以降で[!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** 、これらの REST Api とその swagger 定義をインストールする Windows PowerShell スクリプトがあります。 これらの Api は、ポート、オーケストレーション、パートナー、契約、パイプライン、および詳細をリモートで管理する REST 呼び出しを行います。 

このトピックでは、REST Api をインストールする方法を示します。

## <a name="prerequisites"></a>前提条件
* インストール[機能パック 1](https://www.microsoft.com/download/details.aspx?id=55100)で、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]

* IIS をインストール、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]です。 ほとんどの[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]環境では、IIS が既にインストールされています。 参照してください[Hardware and Software Requirements for BizTalk Server 2016](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)です。

## <a name="enable-the-rest-apis"></a>REST Api を有効にします。

1. Windows PowerShell を管理者として実行 (**開始**メニューで、「 **PowerShell**、右クリックし、、選択**管理者として実行**)。 
2. BizTalk フォルダーに移動**Program Files (x86)/microsoft BizTalk Server 2016**
3. 次のコマンドを実行します。 更新してください、 `website`、 `domain/user`、 `password`、および`domain\group`実際の値にします。 

    ```Powershell
    FeaturePack.ConfigureServices.ps1 -Service management -WebSiteName '<Default Web Site>' -ApplicationPool <mgmtServiceAppPool> -ApplicationPoolUser <domain>\<user> -ApplicationPoolUserPassword <password> -AuthorizationRoles '<domain>\<group>, <domain>\<group>'
    ```
4. スクリプトを実行した後は、新しい IIS アプリケーションを参照してください。  
    1. Web ブラウザーを開きます
    2. 参照**http://localhost/OperationalDataService/swagger**

5. Swagger 定義ロードします。 更新することによってアクセスを持っているユーザーを変更することも、 **web.config**管理アプリケーションのルート フォルダー内のファイルです。

REST Api は、マシンを介して公開されますと、アクセスして他のアプリケーションで実行できることができます。 


## <a name="see-also"></a>参照
 [この機能パックを構成します。](../core/configure-the-feature-pack.md)