---
title: Windows SharePoint Services のトラブルシューティング |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9acf9a0d-2c92-4227-80f8-b2d0cca0c232
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 95d0b833028afdc3c2b560ed60802ff60d6d4046
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65253614"
---
# <a name="troubleshooting-windows-sharepoint-services"></a>Windows SharePoint Services のトラブルシューティング
Microsoft [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] Windows SharePoint Services アダプターによって使用されます。 このトピックでは、Windows SharePoint Services およびこれらの問題の解決方法で発生する可能性がある既知の問題について説明します。  
  
## <a name="known-issues"></a>既知の問題  
  
#### <a name="login-failed-for-user-nt-authoritynetwork-service-error-occurs-when-attempting-to-create-content-database"></a>ログイン ユーザー ' NT authority \network SERVICE' エラーのエラーは、コンテンツ データベースを作成するときに発生します。  
  
##### <a name="problem"></a>問題  
 SharePoint サーバーの全体管理 Web サイトを使用してコンテンツ データベースを作成しようとすると、次のようなエラーが表示されます。  
  
 ユーザー ' NT authority \network SERVICE' はログインできませんでした。  
  
##### <a name="cause"></a>原因  
 この問題に接続しているデータベースのデータベース所有者が Windows SharePoint Services が実行されているアプリケーション プール id と異なる場合に発生します。  
  
##### <a name="resolution"></a>解決策  
 この問題を解決するには、次のいずれかを実行します。  
  
-   ネットワーク サービス アカウントに SQL Server で「データベース作成」権限を付与します。  
  
-   SQL Server の「データベース作成」権限を持っているアカウントには、アプリケーション プール id アカウントを変更します。  
  
#### <a name="service-unavailable-error-occurs-when-accessing-the-sharepoint-central-administration-web-site"></a>「サービスは利用できません」エラーは、SharePoint サーバーの全体管理 Web サイトにアクセスするときに発生します。  
  
##### <a name="problem"></a>問題  
 SharePoint サーバーの全体管理 Web サイトを開こうとすると、次のようなエラーが表示されます。  
  
 サービス利用不可  
  
##### <a name="cause"></a>原因  
 このエラーの最も一般的な原因は、アプリケーション プール (IIS 6.0 または IIS 7.0) または COM + アプリケーションをホストしている (IIS 5.x) for SharePoint サーバーの全体管理 Web サイトが停止しています。 これは、問題は発生アプリケーション プールまたは COM + アプリケーションが構成されている場合、id を指定したユーザー名またはパスワードが無効です。  
  
##### <a name="resolution"></a>解決策  
 トピックの「IIS アプリケーション ホスト プロセス Id の設定」セクションの手順に従って[IIS アクセス許可問題を解決するためのガイドライン](../core/guidelines-for-resolving-iis-permissions-problems.md)適切なホスト プロセス id を設定します。  
  
#### <a name="cannot-connect-to-the-configuration-database-error-occurs-when-attempting-to-extend-and-create-a-content-database"></a>「構成データベースに接続できません」エラーは、拡張し、コンテンツ データベースを作成しようとしています。 ときに発生します。  
  
##### <a name="problem"></a>問題  
 拡張して、SharePoint サーバーの全体管理 Web サイトを使用してコンテンツ データベースを作成しようとすると、次のようなエラーが表示されます。  
  
 構成データベースに接続できません。  
  
##### <a name="cause"></a>原因  
 この問題は、SharePoint サーバーの全体管理 Web サイトを実行しているアプリケーション プールで使用されるアカウントに SQL Server データベースに必要なアクセス許可があるない場合に発生します。  
  
##### <a name="resolution"></a>解決策  
 この問題を解決するには、次のいずれかを実行します。  
  
-   SQL Server での SharePoint サーバーの全体管理 Web サイト「データベース作成」権限をアプリケーション プールで使用されるアカウントに付与します。  
  
-   SQL Server の「データベース作成」権限を持っているアカウントには、アプリケーション プール id アカウントを変更します。  
  
#### <a name="the-sharepoint-timer-service-service-failed-to-start-error-is-generated-in-the-application-log-after-rebooting-server"></a>サーバー再起動後に、アプリケーション ログに「SharePoint Timer サービスを開始できませんでした」エラーが生成されます。  
  
##### <a name="problem"></a>問題  
 サーバーの再起動後に、イベント ログに次のエラーでを参照してください。  
  
 SharePoint Timer サービスを開始できませんでした。  
  
 SharePoint サーバーの全体管理サイトを開く場合は、次のエラーを表示することがありますも。  
  
 WSS 構成データベースの STS_Config に接続できません。  
  
##### <a name="cause"></a>原因  
 このエラーは、SharePoint Timer サービスにアクセスできないときに発生します。、[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]データベースの再起動後です。 通知を送信し、スケジュールされたタスクを実行する SharePoint Timer サービスが使用される[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]します。 SharePoint Timer サービスを開始できない最も一般的な理由は、対象のユーザー名またはパスワードが無効になった id でサービスを実行するために使用するアカウントが構成されていることです。  
  
##### <a name="resolution"></a>解決策  
 ユーザー名と、SharePoint Timer サービス ログオン アカウントの指定したパスワードが正しいことと、サービスが開始されていることを確認します。  
  
## <a name="see-also"></a>参照  
 [Windows SharePoint Services 仮想サーバーを構成する方法](http://support.microsoft.com/kb/832769)   
 [バックアップし、Microsoft SQL Server 2000 Desktop Engine (Windows) を使用している Windows SharePoint Services のインストールを復元する方法](http://support.microsoft.com/kb/833797)   
 [Windows SharePoint Services Web サイトに接続するときに、「構成データベースに接続できません」エラー メッセージが表示されます。](http://support.microsoft.com/kb/823287)   
 [Windows SharePoint Services の Web サイトを参照すると、「サービス利用不可」エラー メッセージが表示されます。](http://support.microsoft.com/kb/823552)   
 [Windows SharePoint Services コンテンツ データベースを管理するときに「既に Database < Database_Name > が存在します」のエラー メッセージが表示されます。](http://support.microsoft.com/kb/828815)