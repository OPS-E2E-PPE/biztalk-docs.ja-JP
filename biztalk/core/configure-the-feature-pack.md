---
title: Feature pack の構成 |Microsoft ドキュメント
description: インストールし 1, 用 feature pack を構成および機能パック 2 です。 新しい機能の一覧から、API Management、team services デプロイメント、Azure に新しいアダプター、バックアップなど、BizTalk Server 2016 での詳細を参照してください。
ms.custom: ''
ms.date: 11/22/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1027bfa6-49b9-4f58-a2e2-3e0ae2fc3bf3
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e5b4164cf1f1355ab9a0d2f350aa5b3b5ce411e0
ms.sourcegitcommit: f4c0d7bc4b617688c643101a34062db90014851a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2017
ms.locfileid: "25550761"
---
# <a name="configure-the-feature-pack"></a>この機能パックを構成します。

## <a name="overview"></a>概要

[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]feature pack を使用して、機能強化、機能、および Azure でよくの統合を提供します。 これらの機能パックは、展開、セキュリティ、分析、ランタイム、およびバックアップなど、重要な分野の機能を拡張します。 

> [!NOTE]
> Feature pack の Enterprise および Developer エディションで使用可能な[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]とき。 
> 
> - Software Assurance (SA) で使用または
> - 実行している[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]Enterprise Agreement を使用して azure
> 
> Feature pack がそれ以外のご利用いただけません[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]edition、またはその他の[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]バージョン。 

## <a name="download-and-install"></a>ダウンロードしてインストールする

Feature pack は累積されます。 ように feature pack 2 をインストールするときに取得することも、機能と更新プログラム機能パック 1 でします。

* ダウンロード、 [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [Feature Pack 2](https://aka.ms/bts2016fp2)です。

* ダウンロード、 [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [機能パック 1](https://www.microsoft.com/download/details.aspx?id=55100)です。

#### <a name="install"></a>Install

1. セットアップを管理者として実行します。
2. **へようこそ]**[**次**です。 
3. ライセンス契約に同意して、**[次へ]** を選択します。 
4. インストールを続行します。 インストール中にいくつかのコマンド ウィンドウ可能性があります開いたり閉じたりします。 完了したら、されたら**完了**です。

セットアップ ログに作成されて`C:\ProgramData\Microsoft\E-Business Servers Updates\Updates\Uninstall4014788-FP2\setup.log`です。

>[!TIP]
> インストールの包括的なガイダンスについては、次を参照してください。、 [Feature Pack のインストールに関する手順](https://blog.sandro-pereira.com/2017/04/27/microsoft-biztalk-server-2016-feature-pack-1-step-by-step-installation/)ブログの投稿。

## <a name="feature-pack-2-updates"></a>機能パック 2 の更新

#### <a name="expose-soap-endpoints-with-api-managementcoreconnect-to-azure-api-managementmd"></a>[API Management の SOAP エンドポイントを公開します](../core/connect-to-azure-api-management.md)

機能パック 1 で行われた API 管理の統合に展開すると、できるようになりましたを公開して、Wcf-basichttp 受信、BizTalk Server 管理コンソールを使用して SOAP エンドポイントの場所。 

#### <a name="use-the-event-hub-adapterevent-hubs-adaptermd"></a>[Event Hub のアダプターを使用します。](event-hubs-adapter.md)

BizTalk からのメッセージを Azure Event Hubs に送信し、Azure Event Hubs から BizTalk Server にメッセージを受信します。 トランスポートのプロパティを構成するときに、簡単に、Azure アカウントにサインインし、Azure Event Hubs の名前空間、および Event Hub を自動的に選択できます。

#### <a name="backup-to-azure-blob-accountcorehow-to-configure-the-backup-biztalk-server-jobmd"></a>[Azure blob アカウントへのバックアップ](../core/how-to-configure-the-backup-biztalk-server-job.md)
BizTalk Server のバックアップ ジョブは、BizTalk データベースとログ ファイルをバックアップします。 この SQL エージェント ジョブを構成するときに、ジョブのプロパティ内での Azure blob ストレージ アカウントを入力できます。 これにより、ローカルの物理ディスクを使用する代わりに、データをバックアップする別のオプションです。 

#### <a name="multi-machine-deployment-using-vstscoreconfigure-automatic-deployment-with-visual-studio-team-services-in-biztalkmd"></a>[VSTS を使用して複数のコンピューターの展開](../core/configure-automatic-deployment-with-visual-studio-team-services-in-biztalk.md)
展開グループを使用して、複数の BizTalk Server にアプリケーションを展開できます。 また、アプリケーション プロジェクト内でアプリケーション名を設定でき、管理サーバーを入力して、アプリケーションをインストールできます。

[展開グループ](https://docs.microsoft.com/vsts/build-release/concepts/definitions/release/deployment-groups/index)VSTS でこれを行う方法の詳細を提供します。  

#### <a name="use-service-bus-premiumcoresb-messaging-adaptermd"></a>[サービス バス Premium を使用します。](../core/sb-messaging-adapter.md)

Service Bus アダプターには、パーティション分割されたキューおよびトピックにメッセージを送信するなど、サービス バス Premium がサポートしています。 [サービス バス プレミアムおよび標準的なメッセージング層](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-premium-messaging)サービス バス Premium の詳細について詳しく説明します。 

#### <a name="use-named-instances-with-application-insightscoresend-tracking-data-to-azure-application-insights-using-biztalk-servermd"></a>[Application Insights による名前付きインスタンスを使用します。](../core/send-tracking-data-to-azure-application-insights-using-biztalk-server.md)
分析を可能になり、Application Insights キーを入力すると、エラーが発生する可能性があります。 

```
Group settings were not applied. (A database failure occurred due to database connectivity problems.)
```

これは、名前付きインスタンスの SQL を使用する場合に発生します。 これは、です。 この feature pack で修正します。名前付きインスタンスの SQL および SQL の既定のインスタンスを使用できます。 

#### <a name="tls-12-support"></a>TLS 1.2 サポート

TLS 1.2 は、BizTalk Server で、すべてのアダプターなど、すべてのアクセラレータがサポートされます。 SSL、TLS 1.0、および BizTalk サーバーで TLS 1.1 を無効にすることができます。 

重要な情報: 

* BizTalk とも通信するすべての外部システムは、TLS 1.2 をサポートする必要があります。
* Functoid などの任意のカスタム コードは、サポート TLS 1.2 に更新する必要があります。

[TLS と SSL プロトコルの説明](https://support.microsoft.com/kb/3155464)TLS 1.2 環境をセットアップする方法について説明します。 

#### <a name="use-latest-newtonsoft-json"></a>最新の Newtonsoft の JSON を使用します。 
Newtonsoft は、.NET 用 JSON フレームワークです。 この機能パックには、バージョン 10.0.3 のサポートが含まれます。 [V をダウンロードします。10.0.3](https://www.nuget.org/packages/Newtonsoft.Json/10.0.3) NuGet から直接です。 


## <a name="feature-pack-1-updates"></a>機能パック 1 の更新

#### <a name="send-tracking-data-to-application-insightscoresend-tracking-data-to-azure-application-insights-using-biztalk-servermd"></a>[追跡データを Application Insights に送信する](../core/send-tracking-data-to-azure-application-insights-using-biztalk-server.md)

追跡データを分析、機械学習、診断などの機能を使用する Azure Application Insights に送信します。 

#### <a name="configure-the-operational-data-feed-using-power-bicoreconfigure-the-operational-data-feed-for-power-bi-with-biztalk-servermd"></a>[フィードの Power BI を使用して運用データを構成します。](../core/configure-the-operational-data-feed-for-power-bi-with-biztalk-server.md)

OData を使用して Power BI に追跡データを送信します。 たとえば、ポートやオーケストレーションから追跡データのビジュアル表現を取得します。 

#### <a name="connect-to-the-management-rest-apis-in-biztalkcoreinstall-and-configure-the-management-rest-apis-in-biztalk-servermd"></a>[管理の BizTalk で REST Api への接続します。](../core/install-and-configure-the-management-rest-apis-in-biztalk-server.md)

REST Api を使用すると、契約、中断されたインスタンス、参加解除のオーケストレーションなど、BizTalk アイテムをリモートで管理します。

#### <a name="configure-advanced-schedulingcoreconfigure-the-time-zone-and-recurrence-scheduling-in-biztalk-servermd"></a>[高度なスケジュール設定を構成します。](../core/configure-the-time-zone-and-recurrence-scheduling-in-biztalk-server.md)

有効にする詳細なでスケジュールの受信場所。 たとえば、タイム ゾーンを設定または特定の月に特定の日の定期的なサービス時間帯を設定します。

#### <a name="configure-automatic-deployments-with-vstscoreconfigure-automatic-deployment-with-visual-studio-team-services-in-biztalkmd"></a>[VSTS と自動展開を構成します。](../core/configure-automatic-deployment-with-visual-studio-team-services-in-biztalk.md)  

Visual Studio Team Services (VSTS) を使用して、ソリューションを自動的に展開するか、既存のアプリケーションを更新します。 インストールされたエージェントと通信する VSTS、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]です。

#### <a name="connect-to-sql-server-always-encrypted-columns-with-biztalk-servercoreconnect-to-sql-server-always-encrypted-columns-with-biztalk-servermd"></a>[BizTalk Server と SQL Server の Always Encrypted の列への接続します。](../core/connect-to-sql-server-always-encrypted-columns-with-biztalk-server.md)  

WCF-SQL アダプターを使用して、SQL Server で Always Encrypted データベースから暗号化された列をクエリします。

#### <a name="integrate-with-api-managementcoreconnect-to-azure-api-managementmd"></a>[API Management を統合します。](../core/connect-to-azure-api-management.md)

Azure API management サービス内で作成および WSDL、として API を公開したり BizTalk SOAP エンドポイントに URI を使用します。  