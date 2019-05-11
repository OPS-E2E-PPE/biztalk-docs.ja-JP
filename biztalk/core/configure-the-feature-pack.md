---
title: Feature pack の構成 |Microsoft Docs
description: インストールし、機能パック 1 を構成し、機能パック 2 します。 API Management、team services のデプロイ、Azure の新しいアダプター、バックアップ、および BizTalk Server 2016 では、複数を含む新しい機能の一覧を参照してください。
ms.custom: ''
ms.date: 06/26/2018
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
ms.openlocfilehash: 5e9dad92a11357c121e01a958996d0b335ba741b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65356453"
---
# <a name="configure-the-feature-pack"></a>Feature pack を構成します。

## <a name="overview"></a>概要

[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] feature pack を使用して、機能強化、機能、および Azure との統合を提供します。 これらの feature pack は、展開、セキュリティ、分析、ランタイム、保守、標準的なコンプライアンス、およびハイブリッド統合などの主要分野における機能を拡張します。 

> [!NOTE]
> Feature pack の Enterprise および Developer エディションで使用可能な[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]とき。 
> 
> - ソフトウェア アシュアランス (SA) で使用または
> - 実行している[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]エンタープライズ契約を使用して Azure に
> 
> Feature pack がその他のご利用いただけません[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]エディション (Standard edition および Branch edition)、またはその他の[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]バージョン (2013 R2、2013、2010 など)。 

## <a name="download-and-install"></a>ダウンロードしてインストールする

Feature pack は累積されます。 したがって 3 用 feature pack をインストールするときに取得することも、機能および更新 feature pack 2 および 1。 最新の累積的更新プログラムを表示します。

* ダウンロード、 [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [Feature Pack 3](https://aka.ms/bts2016fp3)します。

* ダウンロード、 [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [Feature Pack 2](https://aka.ms/bts2016fp2)します。

* ダウンロード、 [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [Feature Pack 1](https://www.microsoft.com/download/details.aspx?id=55100)します。

#### <a name="install"></a>インストール

1. セットアップを管理者として実行します。
2. **ようこそ**を選択します**次**します。 
3. ライセンス条項に同意し、選択**次**します。 
4. インストールを続行します。 インストール中にはいくつかのコマンド ウィンドウが開き、閉じます。 完了すると、求められる**完了**します。

セットアップ ログが作成`C:\ProgramData\Microsoft\E-Business Servers Updates\Updates\Uninstall4014788-FP2\setup.log`です。

>[!TIP]
> インストールの包括的なガイダンスについては、次を参照してください。、 [BizTalk Server 2016 機能パック 3: ステップ バイ ステップ インストール](https://blog.sandro-pereira.com/2018/06/26/biztalk-server-2016-feature-pack-3/)ブログの投稿。

## <a name="feature-pack-3-updates"></a>機能パック 3 更新プログラム

**Office 365 アダプター**


Microsoft Office 365 統合した、最適なクラウド ベースのサブスクリプション サービスは、人々 のツールが現在動作します。 Excel や Outlook などのクラス最高のアプリを OneDrive や Microsoft Teams などの強力なクラウド サービスを組み合わせることにより、Office 365 はすべてのユーザーを作成し、任意のデバイスで任意の場所を共有できます。

Office 365 の Microsoft BizTalk Server アダプターには、Outlook のメール、連絡先、およびスケジュールを BizTalk Server 2016 に基づく新しいソリューションと統合するには、IT プロフェッショナルおよび企業の開発者が有効にします。

#### <a name="office-365-mail-adapteroffice365-mail-adaptermd"></a>[Office 365 メール アダプター](office365-mail-adapter.md)
BizTalk Adapter for Office 365 のメールを使用して読み取ることができます、既読としてマーク Outlook の一方向の BizTalk Server 経由で電子メール メッセージの受信場所を削除または。 このアダプターを使用して、一方向の静的で、メッセージの優先度の設定を含む電子メール メッセージを記述することができますか、動的な BizTalk Server 送信ポート。

#### <a name="office-365-calendar-adapteroffice365-calendar-adaptermd"></a>[Office 365 カレンダーのアダプター](office365-calendar-adapter.md)
BizTalk Adapter for Office 365 カレンダーを使用して取得できます今後の予定表が一方向の BizTalk Server を介してイベントを受信場所。 このアダプターを使用して、カレンダーのイベントを作成することができますと必須およびオプションの出席者の入力一方向の静的または動的な BizTalk Server から送信ポート。

#### <a name="office-365-contact-adapteroffice365-contact-adaptermd"></a>[Office 365 連絡先アダプター](office365-contact-adapter.md)
BizTalk アダプターを使用して、Office 365 の連絡先に、連絡先を作成できますとすべての設定を入力します。 一方向の静的または動的な BizTalk Server から送信ポート。

## <a name="feature-pack-2-updates"></a>機能パック 2 更新プログラム

#### <a name="expose-soap-endpoints-with-api-managementcoreconnect-to-azure-api-managementmd"></a>[API Management で SOAP エンドポイントを公開します。](../core/connect-to-azure-api-management.md)

Feature Pack 1 を使用した API management の統合で拡張すると、できるようになりました公開、Wcf-basichttp 受信場所として BizTalk Server 管理コンソールを使用して、SOAP エンドポイント。 

#### <a name="use-the-event-hub-adapterevent-hubs-adaptermd"></a>[イベント ハブのアダプターを使用します。](event-hubs-adapter.md)

Azure Event hubs では、BizTalk からのメッセージを送信して、BizTalk Server を Azure Event Hubs からメッセージを受信します。 トランスポートのプロパティを構成するときに、簡単に、Azure アカウントにサインインし、Azure Event Hubs 名前空間とイベント ハブを自動的に選択できます。

#### <a name="backup-to-azure-blob-accountcorehow-to-configure-the-backup-biztalk-server-jobmd"></a>[Azure blob アカウントへのバックアップ](../core/how-to-configure-the-backup-biztalk-server-job.md)
BizTalk Server のバックアップ ジョブは、BizTalk データベースとログ ファイルをバックアップします。 この SQL エージェント ジョブを構成するときに、ジョブのプロパティ内での Azure blob ストレージ アカウントを入力できます。 これにより、ローカルの物理ディスクを使用する代わりに、データをバックアップする別のオプション。 

#### <a name="multi-machine-deployment-using-vstscoreconfigure-automatic-deployment-with-visual-studio-team-services-in-biztalkmd"></a>[VSTS を使用して複数のコンピューターの展開](../core/configure-automatic-deployment-with-visual-studio-team-services-in-biztalk.md)
配置グループを使用して、複数の BizTalk Server アプリケーションをデプロイできます。 アプリケーション プロジェクト内でアプリケーション名を設定でき、管理サーバーを入力して、アプリケーションをインストールできます。

[配置グループ](https://docs.microsoft.com/vsts/build-release/concepts/definitions/release/deployment-groups/index)VSTS でこれを行う方法の詳細を提供します。  

#### <a name="use-service-bus-premiumcoresb-messaging-adaptermd"></a>[Service Bus Premium を使用します。](../core/sb-messaging-adapter.md)

Service Bus アダプターには、パーティション分割されたキューおよびトピックにメッセージの送信など、Service Bus Premium がサポートしています。 [Service Bus の Premium および Standard メッセージング レベル](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-premium-messaging)Service Bus Premium の詳細について詳しく説明します。 

#### <a name="use-named-instances-with-application-insightscoresend-tracking-data-to-azure-application-insights-using-biztalk-servermd"></a>[Application Insights で名前付きインスタンスを使用します。](../core/send-tracking-data-to-azure-application-insights-using-biztalk-server.md)
Analytics を有効にする Application Insights キーを入力すると、エラーが発生する可能性があります。 

```
Group settings were not applied. (A database failure occurred due to database connectivity problems.)
```

これは、名前付きインスタンスの SQL を使用する場合に発生します。 これは、この feature pack; に修正します。名前付きインスタンスの SQL および SQL の既定のインスタンスを使用できます。 

#### <a name="tls-12-support"></a>TLS 1.2 のサポート

TLS 1.2 は、BizTalk server のすべてのアダプターなど、すべてのアクセラレータがサポートされます。 SSL、TLS 1.0、および BizTalk Server の TLS 1.1 を無効にすることができます。 

重要な情報: 

* また、BizTalk と通信するすべての外部システムが TLS 1.2 をサポートする必要があります。
* Functoid などの任意のカスタム コードは、TLS 1.2 をサポートするように更新する必要があります。

[TLS と SSL プロトコルの説明](https://support.microsoft.com/kb/3155464)TLS 1.2 の環境をセットアップする方法について説明します。 

#### <a name="use-latest-newtonsoft-json"></a>最新 Newtonsoft の JSON を使用します。 
Newtonsoft は、.NET 用の JSON フレームワークです。 この機能パックのバージョン 10.0.3 のサポートが含まれます。 [V をダウンロードします。10.0.3](https://www.nuget.org/packages/Newtonsoft.Json/10.0.3) NuGet から直接します。 


## <a name="feature-pack-1-updates"></a>機能パック 1 更新プログラム

#### <a name="send-tracking-data-to-application-insightscoresend-tracking-data-to-azure-application-insights-using-biztalk-servermd"></a>[追跡データを Application Insights に送信する](../core/send-tracking-data-to-azure-application-insights-using-biztalk-server.md)

追跡データを分析、機械学習、診断などの機能を使用する Azure Application Insights に送信します。 

#### <a name="configure-the-operational-data-feed-using-power-bicoreconfigure-the-operational-data-feed-for-power-bi-with-biztalk-servermd"></a>[Power BI を使用してフィード オペレーション データを構成します。](../core/configure-the-operational-data-feed-for-power-bi-with-biztalk-server.md)

OData を使用して Power BI には、追跡データを送信します。 など、ポート、およびオーケストレーションから追跡データのビジュアル表現を取得します。 

#### <a name="connect-to-the-management-rest-apis-in-biztalkcoreinstall-and-configure-the-management-rest-apis-in-biztalk-servermd"></a>[管理 REST Api では、BizTalk への接続します。](../core/install-and-configure-the-management-rest-apis-in-biztalk-server.md)

REST Api を使用して、契約、中断されたインスタンス、オーケストレーションの参加解除など、BizTalk アイテムをリモートで管理します。

#### <a name="configure-advanced-schedulingcoreconfigure-the-time-zone-and-recurrence-scheduling-in-biztalk-servermd"></a>[高度なスケジュール設定を構成します。](../core/configure-the-time-zone-and-recurrence-scheduling-in-biztalk-server.md)

有効にする詳細なでスケジュールの受信場所。 など、タイム ゾーンを設定または特定の日の特定の月に繰り返しサービス時間帯を設定します。

#### <a name="configure-automatic-deployments-with-vstscoreconfigure-automatic-deployment-with-visual-studio-team-services-in-biztalkmd"></a>[VSTS を使用した自動展開を構成します。](../core/configure-automatic-deployment-with-visual-studio-team-services-in-biztalk.md)  

Visual Studio Team Services (VSTS) を使用して、ソリューションを自動的に展開するか、既存のアプリケーションを更新します。 VSTS と通信するエージェントがインストールされて、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]します。

#### <a name="connect-to-sql-server-always-encrypted-columns-with-biztalk-servercoreconnect-to-sql-server-always-encrypted-columns-with-biztalk-servermd"></a>[BizTalk Server と SQL Server の Always Encrypted の列への接続します。](../core/connect-to-sql-server-always-encrypted-columns-with-biztalk-server.md)  

WCF-SQL アダプターを使用して、SQL Server で Always Encrypted データベースから暗号化された列をクエリします。

#### <a name="integrate-with-api-managementcoreconnect-to-azure-api-managementmd"></a>[API Management との統合します。](../core/connect-to-azure-api-management.md)

Azure API management サービス内で作成しとして WSDL では、API を公開し、BizTalk SOAP エンドポイントに URI を使用することができます。  
