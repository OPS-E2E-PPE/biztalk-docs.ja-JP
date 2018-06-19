---
title: 展開して、BizTalk アプリケーションの管理に必要なアクセス許可 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying [applications], security
- permissions, EDI adapters
- deploying, security
- security, applications
- security, EDI adapters
- assemblies, permissions
- permissions, deploying
- EDI adapters, security
- permissions, assemblies
- security, assemblies
- permissions, applications
- deploying, permissions
- applications, importing
- applications, exporting
- permissions, exporting
- installing, permissions
- applications, security
- security, permissions
- applications, installing
- assemblies, security
- managing, security
ms.assetid: 4a459ff1-661d-403a-99e0-d54b82e008d0
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 608da93cd1960d26304f4dcebe239367de2404e4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22265546"
---
# <a name="permissions-required-for-deploying-and-managing-a-biztalk-application"></a>BizTalk アプリケーションの展開と管理に必要なアクセス許可
アプリケーションの展開には、BizTalk アプリケーションのインポート、エクスポート、およびインストールの他に、Visual Studio から BizTalk アセンブリを展開することが含まれています。 これらの作業を実行するために必要な基本的なアクセス許可は次のとおりです。  
  
-   BizTalk Server 管理者グループのメンバーには、Visual Studio から BizTalk アセンブリを展開するために必要なアクセス許可が付与されます。  
  
-   BizTalk Server 管理者グループのメンバーには、BizTalk アプリケーションを BizTalk グループにインポートするために必要なアクセス許可が付与されます。 インポート時に、アプリケーション内のアセンブリをグローバル アセンブリ キャッシュ (GAC) に追加するオプションを指定する場合、アセンブリ フォルダーに対する書き込みアクセス許可も必要です。 このアクセス許可は、ローカルの Administrators グループのメンバーとして付与されます。  
  
-   BizTalk Server 管理者グループまたは BizTalk Server Operators グループのメンバーとして、次の作業を行うために必要なアクセス許可が付与されます。  
  
    -   BizTalk アプリケーションをエクスポートします。  
  
    -   送信ポート、送信ポート グループ、およびオーケストレーションの開始と停止  
  
    -   受信場所の有効化と無効化  
  
    -   インスタンスの中断、再開、および終了  
  
    -   起動し、アプリケーションを停止  
  
-   ローカルの Administrators グループのメンバーには、ローカル コンピューターに BizTalk アプリケーションをインポートするためのアクセス許可が付与されます。  
  
 ユーザーがこれらの作業を実行する際には、最も制限されたアクセス許可を提供する必要がある場合があります。 このトピックの残りの部分では、必要なアクセス許可の詳細について説明します。  
  
-   [Visual Studio から BizTalk アセンブリを展開するためのアクセス許可](#BKMK_Permissions_for_deploying)  
  
-   [アプリケーションをインポートするためのアクセス許可](#BKMK_Permissions_for_importing)  
  
-   [アプリケーションをエクスポートするためのアクセス許可](#BKMK_Permissions_for_exporting)  
  
-   [アプリケーションをインストールするためのアクセス許可](#BKMK_Permissions_for_installing_an_application)  
  
##  <a name="BKMK_Permissions_for_deploying"></a>Visual Studio から BizTalk アセンブリを展開するためのアクセス許可  
 Visual Studio から BizTalk アセンブリを展開するには、少なくとも BizTalk 管理データベースに対する書き込みアクセス許可が必要です。 このアクセス許可は、BizTalk Server 管理者グループのメンバーとして付与されます。  
  
##  <a name="BKMK_Permissions_for_importing"></a>アプリケーションをインポートするためのアクセス許可  
 BizTalk アプリケーションをインポートするには、少なくとも次のアクセス許可が必要です。 必要なすべてのアクセス許可は、BizTalk Server 管理者グループのメンバーに付与されますが、アセンブリを GAC にインストールする場合は、アセンブリ フォルダーに対する書き込みアクセス許可も必要になります。  
  
|アイテム|Permissions|必要な場合|  
|----------|-----------------|-------------------|  
|BizTalk 管理データベース|[読み取り/書き込み]|常に必要です。|  
|BizTalk ルール エンジン データベース|[読み取り/書き込み]|アプリケーションにルール リソースが含まれている場合のみ必要です。|  
|BAM データベース|[読み取り/書き込み]|アプリケーションに BAM リソースが含まれている場合のみ必要です。|  
|グローバル アセンブリ キャッシュ (GAC)|[読み取り/書き込み]|アプリケーションにアセンブリ リソースが含まれている場合、およびアセンブリがインポート時に GAC に追加されていることを指定する場合のみ必要です  (以下の「メモ」を参照)。|  
  
> [!NOTE]
>  インポート ウィザードを使用してアセンブリをインポートする場合、アセンブリをグローバル アセンブリ キャッシュ (GAC) に追加するオプションを指定できます。 この場合、アセンブリ フォルダーに対する書き込みアクセス許可が必要です。 アセンブリ フォルダーの詳細については、次を参照してください。[アプリケーションをインストールするためのアクセス許可](#BKMK_Permissions_for_installing_an_application)です。  
>   
>  前の一覧に示されていない項目を展開するスクリプトがアプリケーションに含まれている場合、それらの項目を展開するための適切なアクセス許可が必要です。  
  
##  <a name="BKMK_Permissions_for_exporting"></a>アプリケーションをエクスポートするためのアクセス許可  
 BizTalk アプリケーションをエクスポートするには、少なくとも次のアクセス許可が必要です。 必要なアクセス許可は、BizTalk Operators グループのメンバーとして付与されます。  
  
|アイテム|Permissions|必要な場合|  
|----------|-----------------|-------------------|  
|BizTalk 管理データベース|読み取り|常に必要です。|  
|BizTalk ルール エンジン データベース|読み取り|アプリケーションにルール リソースが含まれている場合のみ必要です。|  
|証明書ストア|読み取り|アプリケーションに証明書リソースが含まれている場合のみ必要です。|  
|[インターネット インフォメーション サービス]|読み取り|アプリケーションに仮想ディレクトリ リソースが含まれている場合のみ必要です。|  
  
##  <a name="BKMK_Permissions_for_installing_an_application"></a>アプリケーションをインストールするためのアクセス許可  
 既定では、ローカルの Administrators グループのメンバーには、ローカル コンピューターに BizTalk アプリケーションをインポートするために必要なアクセス許可が付与されます。 アプリケーションをインストールするユーザーに対して、制限の厳しいアクセス許可を付与する場合は、次の表に示す最低限のアクセス許可を構成する必要があります。 次に示すアクセス許可以外にも、インストール時に追加のアクセス許可 (新しいデータベースやデータベース テーブルを作成するアクセス許可など) が必要となるリソースがアプリケーションに含まれている場合、それらのアクセス許可も保持する必要があります。  
  
|アイテム|Permissions|必要な場合|  
|----------|-----------------|-------------------|  
|証明書ストア|[読み取り/書き込み]|アプリケーションに証明書リソースが含まれている場合のみ必要です。|  
|[インターネット インフォメーション サービス]|[読み取り/書き込み]|アプリケーションに仮想ディレクトリ リソースが含まれている場合のみ必要です。|  
|GAC (GAC)|[読み取り/書き込み]|アプリケーションにアセンブリ リソースが含まれている場合、およびアセンブリがインストール時に GAC に追加されるように指定する場合のみ必要です  (下の注を参照してください)。|  
|ファイル システム|[読み取り/書き込み]|リソースの対象のプロパティが設定されている場合のみ必要です。|  
|レジストリ|[読み取り/書き込み]|必要な場合、 **regsvcs**または**regasm**COM コンポーネントまたは COM + コンポーネントを含むアセンブリ リソース管理のプロパティが True に設定します。|  
|レジストリ|[読み取り/書き込み]|アプリケーションにアンマネージ COM リソースが含まれている場合に必要です。|  
  
> [!NOTE]
>  BizTalk Server 管理コンソールで、アセンブリのインストール時に GAC に追加するように指定できます (この操作を行うには、リソース フォルダー内のアセンブリを右クリックし、[変更] をクリックします)。 このオプションを指定した場合、BizTalk アプリケーションのインストールには GAC が含まれているアセンブリ フォルダーに対する書き込みアクセス許可が必要です。 アセンブリ フォルダーのパスは %SystemRoot%\assembly です。  
  
## <a name="see-also"></a>参照  
 [アプリケーションの展開のセキュリティに関する考慮事項](../core/security-considerations-for-application-deployment.md)