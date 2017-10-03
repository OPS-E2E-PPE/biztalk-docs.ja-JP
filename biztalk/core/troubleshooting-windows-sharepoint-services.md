---
title: "Windows SharePoint Services のトラブルシューティング |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9acf9a0d-2c92-4227-80f8-b2d0cca0c232
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 51243216f2adb73454477252c7b54358df229610
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshooting-windows-sharepoint-services"></a>Windows Sharepoint Services のトラブルシューティング
Microsoft [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] は Windows SharePoint Services アダプターによって使用されます。 このトピックでは、Windows SharePoint Services で発生する可能性がある既知の問題点とその解決策について説明します。  
  
## <a name="known-issues"></a>既知の問題  
  
#### <a name="login-failed-for-user-nt-authoritynetwork-service-error-occurs-when-attempting-to-create-content-database"></a>コンテンツ データベースを作成しようとすると、"ユーザー 'NT AUTHORITY\NETWORK SERVICE' のログインが失敗しました。" というエラーが発生する  
  
##### <a name="problem"></a>問題  
 [SharePoint のサーバー管理] Web サイトを使用してコンテンツ データベースを作成しようとすると、次のようなエラーが表示されます。  
  
 ユーザー 'NT AUTHORITY\NETWORK SERVICE' はログインできませんでした。  
  
##### <a name="cause"></a>原因  
 この問題は、接続先データベースの所有者が、Windows SharePoint Services を実行しているアプリケーション プールの ID と異なっている場合に発生します。  
  
##### <a name="resolution"></a>解決策  
 この問題を解決するには、次のいずれかの操作を行います。  
  
-   NETWORK SERVICE アカウントに、SQL Server での "データベース作成" 権限を与えます。  
  
-   アプリケーション プール ID アカウントを、SQL Server での "データベース作成" 権限を持つアカウントに変更します。  
  
#### <a name="service-unavailable-error-occurs-when-accessing-the-sharepoint-central-administration-web-site"></a>[SharePoint のサーバー管理] Web サイトにアクセスすると、"サービスは利用できません" というエラーが発生する  
  
##### <a name="problem"></a>問題  
 [SharePoint のサーバー管理] Web サイトを開こうとすると、次のようなエラーが表示されます。  
  
 “サービスは利用できません”  
  
##### <a name="cause"></a>原因  
 このエラーの最も一般的な原因は、[SharePoint のサーバー管理] Web サイトのアプリケーション プール (IIS 6.0 または IIS 7.0) またはホスト元 COM+ アプリケーション (IIS 5.x) が停止していることです。 これは、アプリケーション プールまたは COM + アプリケーションが構成されている id を使用する場合によく発生指定されたユーザー名またはパスワードが有効ではありません。  
  
##### <a name="resolution"></a>解決策  
 "IIS アプリケーション ホスト プロセス Id の設定"」トピックの手順に従います[IIS アクセス許可の問題を解決するためのガイドライン](../core/guidelines-for-resolving-iis-permissions-problems.md)を適切なホスト プロセス id を設定します。  
  
#### <a name="cannot-connect-to-the-configuration-database-error-occurs-when-attempting-to-extend-and-create-a-content-database"></a>コンテンツ データベースを拡張して作成しようとすると "構成データベースに接続できません" というエラーが発生する  
  
##### <a name="problem"></a>問題  
 [SharePoint のサーバー管理] Web サイトを使用してコンテンツ データベースを拡張して作成しようとすると、次のようなエラーが表示されます。  
  
 構成データベースに接続できません  
  
##### <a name="cause"></a>原因  
 この問題は、[SharePoint のサーバー管理] Web サイトを実行しているアプリケーション プールが使用するアカウントに、SQL Server データベースに対する必要なアクセス許可がない場合に発生します。  
  
##### <a name="resolution"></a>解決策  
 この問題を解決するには、次のいずれかの操作を行います。  
  
-   [SharePoint のサーバー管理] Web サイトのアプリケーション プールが使用するアカウントに、SQL Server での "データベース作成" 権限を与えます。  
  
-   アプリケーション プール ID アカウントを、SQL Server での "データベース作成" 権限を持つアカウントに変更します。  
  
#### <a name="the-sharepoint-timer-service-service-failed-to-start-error-is-generated-in-the-application-log-after-rebooting-server"></a>サーバー再起動後にアプリケーション ログで、SharePoint Timer サービスを開始できませんでしたというエラーが生成される  
  
##### <a name="problem"></a>問題  
 サーバーを再起動した後に、次のようなエラーがイベント ログに記録されます。  
  
 SharePoint Timer サービスを開始できませんでした  
  
 また、[SharePoint のサーバー管理] サイトを開いたときに次のようなエラーが表示される場合もあります。  
  
 WSS 構成データベースの STS_Config に接続できません。"  
  
##### <a name="cause"></a>原因  
 このエラーは、再起動後に SharePoint Timer サービスが [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] データベースにアクセスできない場合に発生します。 SharePoint Timer サービスは、[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] に対する通知の送信および予定されたタスクの実行を行うために使用されます。 SharePoint Timer サービスを開始できない最も一般的な理由は、サービスの実行に使用されるアカウントの ID に指定されているユーザー名またはパスワードが無効になっていることです。  
  
##### <a name="resolution"></a>解決策  
 SharePoint Timer サービスのログオン アカウントに指定されているユーザー名とパスワードが正しいこと、およびこのサービスが開始されていることを確認します。  
  
## <a name="see-also"></a>参照  
 [Windows SharePoint Services 仮想サーバーを構成する方法](http://support.microsoft.com/kb/832769)   
 [バックアップし、Microsoft SQL Server 2000 Desktop Engine (Windows) を使用している Windows SharePoint Services のインストールを復元する方法](http://support.microsoft.com/kb/833797)   
 [Windows SharePoint Services Web サイトに接続するときに、「構成データベースに接続できません」エラー メッセージが表示されます。](http://support.microsoft.com/kb/823287)   
 [Windows SharePoint Services の Web サイトを参照すると、「サービスを利用できません」エラー メッセージが表示されます。](http://support.microsoft.com/kb/823552)   
 [Windows SharePoint Services コンテンツ データベースを管理するときに、「Database < Database_Name > が既に存在する」エラー メッセージが表示されます。](http://support.microsoft.com/kb/828815)