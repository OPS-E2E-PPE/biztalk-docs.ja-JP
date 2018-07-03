---
title: BizTalk Server 2016 の新機能新機能 |Microsoft Docs
description: 変更および強化、feature pack、アダプター、セキュリティ、追跡、パフォーマンス、および BizTalk Server 2016 では、複数
ms.custom: ''
ms.prod: biztalk-server
ms.date: 6/22/2018
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3fce1fe8-f515-462d-bf6d-19408d515479
caps.latest.revision: 28
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 75f9dcce6fceb9816df05549a5a4a1e9ddcd7318
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992963"
---
# <a name="whats-new-in-biztalk-server-2016"></a>BizTalk Server 2016 の新機能
[!INCLUDE[bts2016](../includes/bts2016-md.md)] の新機能について確認します。 
  
## <a name="new-in-biztalk-server-2016"></a>BizTalk Server 2016 の新機能  
  
|機能|説明|  
|-------------|-----------------|  
|新しいプラットフォームのサポート|[!INCLUDE[bts2016](../includes/bts2016-md.md)] では、次の Microsoft プラットフォームのサポートを追加します。<br /><br /> -   Visual Studio 2015<br />-   Windows Server 2016<br />-   [!INCLUDE[sqlserver2016](../includes/sqlserver2016-md.md)]<br />-   Office 2016<br/><br/>[BizTalk Server 2016 のハードウェア/ソフトウェア要件](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)|  
| 3 用 feature Pack | 電子メール、予定表、連絡先を使用する Office 365 のアダプターが含まれています。 <br/><br/>[Feature Pack のインストール](https://aka.ms/bts2016fp3)<br/>[含まれているし、その機能の構成を参照してください。](../core/configure-the-feature-pack.md) |
| Feature Pack 2 | 機能強化には、Azure Event Hubs アダプターを Azure blob ストレージ アカウント、Service Bus のパーティションをサポートするバックアップを API Management では、との統合が含まれます。 <br/><br/>[Feature Pack のインストール](https://www.microsoft.com/download/details.aspx?id=55100)<br/>[含まれているし、その機能の構成を参照してください。](../core/configure-the-feature-pack.md) |
| Feature Pack 1 | VSTS を使用しての自動展開のサポート、Azure Application Insights および Power BI への追跡データの送信、受信場所の高度なスケジュール オプションなどが含まれます。<br/><br/>[Feature Pack のインストール](https://www.microsoft.com/download/details.aspx?id=55100)<br/>[含まれているし、その機能の構成を参照してください。](../core/configure-the-feature-pack.md) |
|[!INCLUDE[sqlserver2016](../includes/sqlserver2016-md.md)] AlwaysOn 可用性グループ|サポートは次のとおりです。<br /><br /> -   オンプレミスおよび [!INCLUDE[winazure](../includes/winazure-md.md)] IaaS 仮想マシンでの使用<br />-   運用環境のワークロード向けの使用<br />-   [!INCLUDE[winazure](../includes/winazure-md.md)] での高可用性 (HA) ソリューションを提供 <br/><br/>[SQL Server AlwaysOn を使用した高可用性](../core/high-availability-using-sql-server-always-on-availability-groups.md)<br/><br/> 参照してください[always On AG での分散トランザクション](https://docs.microsoft.com/sql/database-engine/availability-groups/windows/transactions-always-on-availability-and-database-mirroring)は、SQL に固有の要件と機能します。|  
|運用環境の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Azure VM|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の Azure Virtual Machines が、運用環境で完全にサポートされるようになりました。 [!INCLUDE[sqlserver2016](../includes/sqlserver2016-md.md)] AlwaysOn を使用した高可用性ソリューションが実現可能になりました。<br/><br/>[SQL Server AlwaysOn を使用した高可用性](../core/high-availability-using-sql-server-always-on-availability-groups.md)|  
|ロジック アプリのアダプター|Azure でホストされている Logic Apps に接続し、Salesforce、SharePoint、CRM Online などのすべてのコネクタにアクセスします。 たとえば、BizTalk Server で注文を受信したり、ロジック アプリに接続したり、Salesforce を更新したりすることができます。<br/><br/>[ロジック アプリのアダプター](../core/logic-app-adapter.md)|  
| ファイル アダプター | Azure Storage のファイル共有に接続します。 Azure のファイル共有からファイルを受信し、メッセージを Azure のファイル共有に送信できます。 <br/><br/>[ファイル アダプターを構成する](../core/configure-the-file-adapter.md)|
| FTP アダプター | SYST コマンドは必須ではなくなりました。 受信場所または送信ポートで FTP アダプターを構成する場合、**FTP サーバーの種類**と呼ばれるプロパティがあります。 このプロパティを使用して、必要な FTP サーバーを選択します。ここで、SYST が必須かどうかを決定します。 <br/><br/>この変更の結果として、"サポートされる" FTP サーバーが多くなります。 <br/><br/> [FTP アダプターの構成](../core/configuring-the-ftp-adapter.md)|
|SFTP アダプター| SFTP アダプターは、WinSCP を使用して SFTP に接続するために再設計されています。これによって、より多くの SFTP サーバーをサポートできます。 クライアント側のログやその他の暗号化用の暗号も新しくなっています。 <br/><br/>[SFTP アダプター](../core/sftp-adapter.md)|  
| 追跡設定のインポートを許可 | バインド ファイルをインポートすると、オーケストレーションや送信ポートなどで有効になっている追跡プロパティをインポートする (またはインポートしない) ことを選択できます。 これはグローバル設定 (グループ レベルでの設定) のため、この機能をさまざまな環境で設定できます。 たとえば、開発環境の既存の追跡プロパティをインポートすることができ、運用環境の追跡プロパティはインポートしません。<br/><br/>参照してください**BizTalk 設定ダッシュ ボード、グループのページ**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。|
| Shared Access Signature (SAS) | *BasicHttpRelay*、*NetTcpRelay*、*BasicHttp*、*WebHttp* アダプターを使用して、Service Bus 接続に SAS 認証を使用することができます。<br/><br/>[WCF-BasicHttpRelay アダプター](../core/wcf-basichttprelay-adapter.md)<br/>[WCF-NetTcpRelay アダプター](../core/wcf-nettcprelay-adapter.md)<br/>[WCF-BasicHttp アダプター](../core/wcf-basichttp-adapter.md)<br/>[WCF-WebHTTP アダプター](../core/wcf-webhttp-adapter.md)<br/><br/> [SB-Messaging アダプター](../core/sb-messaging-adapter.md) には、PowerShell を使用した Access Control (ACS) の値を取得する手順が含まれるようになりました。|
|動的ポートでの順次配送|静的送信ポートで順次配送をサポートするアダプターに適用されます。 BizTalk 管理コンソールで順次配送オプションを有効にすることができます。<br /><br />[送信ポートに対してトランスポートの詳細オプションを構成する方法](../core/how-to-configure-backup-transport-options-for-a-send-port.md)<br />[メッセージの順次配送](../core/ordered-delivery-of-messages.md)|  
|SHA-2 ハッシュ関数|SHA-2 は完全にサポートされています。次を含みます。<br /><br /> <ul><li>BizTalk では、HTTPS、FTPS、POP3、および WCF アダプターでの SSL メッセージを含むすべてのコンポーネントに SHA2 署名証明書を利用できます。 </li><li>AS2、RosettaNet、および MIME/SMIME エンコーダーの署名キーに対して、次の Advanced Encryption Standard (AES) Exchange システムをサポートします。<ul><li>AES128 (既定値)</li><li>AES192</li><li>AES256</li><br /></ul></li><li>AS2 では、次の SHA2 ベース MIC 計算をサポートします。<ul><li>SHA256 (既定値)</li><li>SHA384</li><li>SHA512</li><br /></ul></li><li>RosettaNet では、次の SHA2 ベースのダイジェスト メソッドをサポートします。<ul><li>SHA256 (既定値)</li><li>SHA384</li><li>SHA512</li><br /></ul></li><li>SHA1 証明書は旧バージョンとの互換性のために引き続き機能します</li></ul><br />[検証の構成 (AS2)](../core/configuring-validation-as2.md)<br />[受信確認 (MDN) の構成 (AS2)](../core/configuring-acknowledgements-mdns-as2.md)<br />[MIME-SMIME エンコーダー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-mime-smime-encoder-pipeline-component.md)|  
|マップのコンパイル|XslTransform または XslCompiledTransform を使用して、マップをコンパイルすることを選択します<br/><br/>[マップのコンパイルを設定し、出力の設定](../core/how-to-specify-xslt-output-settings.md)|  
|スキーマ ウィンドウ|BizTalk マッパーで、送信元スキーマと送信先スキーマを追加/置換します。 この操作を行うと、[型の選択] ウィンドウのサイズを変更できるようになります。 この変更では、ウィンドウを展開し、スキーマの完全な名前を表示することができます。<br/><br/>[スキーマの選択のサイズを変更し、スキーマ ツリーを展開および折りたたむ方法](../core/how-to-resize-the-schema-picker-and-expand-and-collapse-the-schema-trees.md)|  
|アダプターとアクセラレータ|改善と変更は次のとおりです。<ul><li>SAP アダプターはクラシックの RFC SDK、および SAP バインド プロパティの .NET コネクタをサポートしています。 <br/><br/>SAP Service Marketplace (service.sap.com/connectors) で入手できる **SAP Connector for .NET** をインストールします。 インストール中に、**[Install Assemblies to GAC (アセンブリを GAC にインストールする)]** を選択してください。<br/><br/>[SAP .NET コネクタの WCF-SAP アダプターのサポート](https://support.microsoft.com/kb/3100811)では、詳細情報を提供します。  </li><br /><li>BizTalk Accelerator for HL7: 受信場所の MLLP アダプターでは、リモート LOB リスナーへの送信接続を開始するためのオプションをサポートするようになりました。</li></ul>|  
|パーティのインポート/エクスポート|次のような変更が含まれます。<br /><br /> -   インポートおよびエクスポート オプションは、アプリケーションから切り離されています。 たとえば、アプリケーションをエクスポートせずに、パーティをエクスポートすることができます。 アプリケーションをインポートせずに、パーティをインポートすることができます。<br />-   インポートまたはエクスポートする必要があるパーティ、ビジネス プロファイル、契約を選択できます。<br />-   [!INCLUDE[bts2013r2](../includes/bts2013r2-md.md)]、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2013、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2010 での操作と同様に、引き続き企業間アイテムをインポート/エクスポートできます。<br/><br/>[バインド ファイルを使用してインポートまたはエクスポートする](../core/use-binding-files-to-import-or-export.md)|  
|BizTalk 管理|最新の外観に加えて、次のような追加の変更があります。<br /><br /> -   複数のホスト/ホスト インスタンスの設定を同時に構成します。 たとえば、複数のホスト インスタンスの .NET CLR 設定を同時に設定できます。<br />-   新しい検索機能を使用して、スキーマ、リソースなどのアプリケーションのアイテムをフィルター処理して見つけます。<br />-   保留中のメッセージをトラブルシューティングするときに、複数の保留メッセージを同時に 1 つのファイルに保存できます。<br /><br />[BizTalk Server 管理コンソールの使用](../core/using-the-biztalk-server-administration-console.md)|  
|追加の更新プログラム|<ul><li>[!INCLUDE[HL7_CurrentVersion_FirstRef_md](../includes/hl7-currentversion-firstref-md.md)] が基幹業務 (LOB) サーバーへの接続を開始し、その接続経由でメッセージをプッシュします。 LOB は接続を待機して、メッセージを送信します。 <br/><br/>これまでのバージョンの [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の HL7 MLLP 受信アダプターは、LOB サーバーが HL7 に接続するのを待ってから、メッセージを送信していました。 LOB は HL7 に接続してから、メッセージを送信します。 </li><br/><li>Office Web コンポーネント (OWC) のインストールは省略可能になり、[プログラム] のリストで別に表示されています</li><br/><li>オーケストレーション インスタンス ID が XLANG FireEvent トレース出力に追加されます</li></ul>|   
  
## <a name="deprecated--removed-list"></a>非推奨と削除の一覧  
  
|               プログラム               |   状態   |                                                                                                                                                代替                                                                                                                                                |
|-------------------------------------|------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|             RFID Mobile             |  削除   |                                                                                                                                                   なし                                                                                                                                                    |
|             RFID サーバー             |  削除   |                                                                                                                                                   なし                                                                                                                                                    |
| SharePoint SSOM/Web サービス アダプター |  削除   | クライアント側オブジェクト モデル (CSOM) オプションを使用します。<br /><br /> [Windows SharePoint Services アダプター](../core/windows-sharepoint-services-adapter.md)<br /><br /> [付録 B: Microsoft SharePoint アダプターのインストール](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md) |
|            SOAP アダプター             | 非推奨 |                                                                                                                         [WCF-BasicHttp アダプター](../core/wcf-basichttp-adapter.md)                                                                                                                         |
|           以前の SQL アダプター           | 非推奨 |                                                                                                   [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] の WCF ベースの SQL アダプター                                                                                                   |
|                UDDI                 |  削除   |                                                                                                                                                   なし                                                                                                                                                    |
  
> [!IMPORTANT]
>  これらの非推奨の機能の一部は、新しいバージョンの BizTalk に搭載されている場合があります。 そのような場合、次の点を考慮してください。  
>   
> -   機能は、BizTalk 内で内部的に使用可能性があり、顧客のソリューションで使用するものではありません。 その場合、顧客のソリューションではサポートされません。  
> -   インターフェイスは、Microsoft によって変更されている可能性があり、公開されていることができない可能性があります。

## <a name="next-steps"></a>次のステップ
[ハードウェアおよびソフトウェア要件](hardware-and-software-requirements-for-biztalk-server-2016.md)  
[セットアップおよびインストールの前提条件](set-up-and-install-prerequisites-for-biztalk-server-2016.md)  
[BizTalk をインストールします。](install-biztalk-server-2016.md)