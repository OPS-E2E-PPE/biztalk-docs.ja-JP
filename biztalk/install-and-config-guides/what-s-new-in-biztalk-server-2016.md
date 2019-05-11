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
ms.openlocfilehash: 9db2edbf6661a2658dba882f102fcc5d355fefc2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401429"
---
# <a name="whats-new-in-biztalk-server-2016"></a>BizTalk Server 2016 の新機能新機能
最新情報について[!INCLUDE[bts2016](../includes/bts2016-md.md)]します。 
  
## <a name="new-in-biztalk-server-2016"></a>BizTalk Server 2016 の新機能  
  
|機能|説明|  
|-------------|-----------------|  
|新しいプラットフォームのサポート|[!INCLUDE[bts2016](../includes/bts2016-md.md)] 次の Microsoft プラットフォームのサポートを追加します。<br /><br /> -   Visual Studio 2015<br />-   Windows Server 2016<br />-   [!INCLUDE[sqlserver2016](../includes/sqlserver2016-md.md)]<br />Office 2016<br/><br/>[BizTalk Server 2016 のハードウェア/ソフトウェア要件](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)|  
| 3 用 feature Pack | 電子メール、予定表、連絡先を使用する Office 365 のアダプターが含まれています。 <br/><br/>[Feature pack をインストールします。](https://aka.ms/bts2016fp3)<br/>[含まれているし、その機能の構成を参照してください。](../core/configure-the-feature-pack.md) |
| Feature Pack 2 | 機能強化には、Azure Event Hubs アダプターを Azure blob ストレージ アカウント、Service Bus のパーティションをサポートするバックアップを API Management では、との統合が含まれます。 <br/><br/>[Feature pack をインストールします。](https://www.microsoft.com/download/details.aspx?id=55100)<br/>[含まれているし、その機能の構成を参照してください。](../core/configure-the-feature-pack.md) |
| Feature Pack 1 | VSTS、Azure Application Insights を Power BI では、追跡データの送信を使用して自動展開のスケジュール設定を高度なサポートが含まれていますのオプションを受信場所、および詳細。<br/><br/>[Feature pack をインストールします。](https://www.microsoft.com/download/details.aspx?id=55100)<br/>[含まれているし、その機能の構成を参照してください。](../core/configure-the-feature-pack.md) |
|[!INCLUDE[sqlserver2016](../includes/sqlserver2016-md.md)] AlwaysOn 可用性グループ|サポートが含まれます。<br /><br /> -オンプレミスを使用し、 [!INCLUDE[winazure](../includes/winazure-md.md)] IaaS 仮想マシン<br />-運用環境のワークロードを使用します。<br />-での高可用性 (HA) ソリューションを提供します。 [!INCLUDE[winazure](../includes/winazure-md.md)] <br/><br/>[SQL Server AlwaysOn を使用して高可用性](../core/high-availability-using-sql-server-always-on-availability-groups.md)<br/><br/> 参照してください[always On AG での分散トランザクション](https://docs.microsoft.com/sql/database-engine/availability-groups/windows/transactions-always-on-availability-and-database-mirroring)は、SQL に固有の要件と機能します。|  
|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 運用環境での azure Vm|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Azure の仮想マシンが運用環境では完全にサポートされています。 使用して[!INCLUDE[sqlserver2016](../includes/sqlserver2016-md.md)]AlwaysOn 高可用性ソリューションが可能になりました。<br/><br/>[SQL Server AlwaysOn を使用して高可用性](../core/high-availability-using-sql-server-always-on-availability-groups.md)|  
|ロジック アプリのアダプター|Azure でホストされているロジック アプリに接続し、Salesforce、SharePoint、CRM Online、および詳細を含むすべてのコネクタにアクセスできます。 たとえば、BizTalk Server で注文を受信、ロジック アプリへの接続、および Salesforce を更新します。<br/><br/>[ロジック アプリのアダプター](../core/logic-app-adapter.md)|  
| ファイル アダプター | Azure storage のファイル共有に接続します。 Azure ファイル共有からファイルを受信でき、Azure ファイル共有にメッセージを送信できます。 <br/><br/>[ファイル アダプターを構成します。](../core/configure-the-file-adapter.md)|
| FTP アダプター | SYST コマンドは必要なくなりました。 という名前のプロパティがある場合、受信場所で FTP アダプターを構成する場合、または送信ポートは、 **FTP サーバーの種類**します。 。 FTP サーバーを選択するためにこのプロパティを使用します。これは、SYST が必要なかどうかを決定します。 <br/><br/>この変更の結果は、その他の「サポートされる」FTP サーバーがあります。 <br/><br/> [FTP アダプターの構成](../core/configuring-the-ftp-adapter.md)|
|SFTP アダプター| SFTP アダプターは、WinSCP を使用して、SFTP; に接続するように再設計多くの SFTP サーバーをサポートをできます。 クライアント側のログ記録と追加の暗号化の暗号も新しくなっています。 <br/><br/>[SFTP アダプター](../core/sftp-adapter.md)|  
| 追跡設定のインポートを許可します。 | バインドをインポートするときにファイルをすることができます、オーケストレーションでの選択を有効になっている追跡プロパティをインポート (またはインポートしない)、送信ポート、および具合です。 これは、ため、この機能を設定するには、さまざまな環境でのグローバル設定 (グループ レベル設定) です。 たとえば、既存の追跡、開発環境のプロパティをインポートし、追跡のプロパティを運用環境のインポートは行いません。<br/><br/>参照してください**BizTalk 設定ダッシュ ボード、グループのページ**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。|
| Shared Access Signature (SAS) | SAS 認証を使用するには、Service Bus 接続用の*BasicHttpRelay*、 *NetTcpRelay*、 *BasicHttp*、および*WebHttp*アダプター。<br/><br/>[Wcf-basichttprelay アダプター](../core/wcf-basichttprelay-adapter.md)<br/>[Wcf-nettcprelay アダプター](../core/wcf-nettcprelay-adapter.md)<br/>[Wcf-basichttp アダプター](../core/wcf-basichttp-adapter.md)<br/>[Wcf-webhttp アダプター](../core/wcf-webhttp-adapter.md)<br/><br/> [SB Messaging アダプター](../core/sb-messaging-adapter.md) PowerShell を使用して Access Control (ACS) の値を取得する手順が含まれています。|
|順次配送が動的ポートで|静的送信ポートで順次配送をサポートするアダプターに適用されます。 BizTalk 管理コンソールで順次配送オプションを有効にすることができます。<br /><br />[送信ポートに対してトランスポートの詳細オプションを構成する方法](../core/how-to-configure-backup-transport-options-for-a-send-port.md)<br />[メッセージの配信を順序付け](../core/ordered-delivery-of-messages.md)|  
|Sha-2 ハッシュ関数|Sha-2 は完全にサポートを含みます。<br /><br /> <ul><li>BizTalk は、すべてのコンポーネントは、SSL、HTTPS、FTPS、POP3、および WCF アダプターのメッセージングを含む SHA2 署名証明書を利用できます。 </li><li>AS2、RosettaNet、および MIME/SMIME エンコーダーの署名キーは、次の Advanced Encryption Standard (AES) exchange システムをサポートしています。<ul><li>AES128 (既定値)</li><li>AES192</li><li>AES256</li><br /></ul></li><li>As2 は、次の SHA2 ベース MIC 計算をサポートしています。<ul><li>SHA256 (既定値)</li><li>SHA384</li><li>SHA512</li><br /></ul></li><li>RosettaNet では、次の SHA2 ベースのダイジェスト メソッドをサポートしています。<ul><li>SHA256 (既定値)</li><li>SHA384</li><li>SHA512</li><br /></ul></li><li>SHA1 証明書は、旧バージョンとの互換性のための作業を続ける</li></ul><br />[検証の構成 (AS2)](../core/configuring-validation-as2.md)<br />[受信確認 (MDN) の構成 (AS2)](../core/configuring-acknowledgements-mdns-as2.md)<br />[MIME-SMIME エンコーダー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-mime-smime-encoder-pipeline-component.md)|  
|マップをコンパイルします。|XslTransform または XslCompiledTransform を使用して、マップをコンパイルします。<br/><br/>[マップのコンパイルの設定し、出力の設定](../core/how-to-specify-xslt-output-settings.md)|  
|スキーマ ウィンドウ|BizTalk マッパーを追加/置換送信元スキーマと送信先スキーマです。 これを行う、型の選択 ウィンドウはサイズ変更可能なようになりました。 この変更では、ウィンドウを展開し、スキーマの完全名を参照できます。<br/><br/>[スキーマの選択のサイズを変更しを展開し、スキーマ ツリーを折りたたむ方法](../core/how-to-resize-the-schema-picker-and-expand-and-collapse-the-schema-trees.md)|  
|アダプターとアクセラレータ|機能強化と変更は、次のとおりです。<ul><li>SAP アダプターは、SAP バインドのプロパティで、クラシックの RFC SDK、および .NET Connector をサポートしています。 <br/><br/>インストール、 **SAP Connector for .NET**、これは、SAP Service Marketplace (service.sap.com/connectors) で使用できます。 インストール中に、必ず選択して**アセンブリを GAC にインストール**します。<br/><br/>[SAP .NET コネクタの WCF-SAP アダプターのサポート](https://support.microsoft.com/kb/3100811)詳細に説明します。  </li><br /><li>BizTalk Accelerator 用 HL7:受信場所の MLLP アダプターでは、リモート LOB リスナーへの送信接続を開始するには、オプションできるようになりました。</li></ul>|  
|パーティのインポート/エクスポート|変更は次のとおりです。<br /><br /> -インポートおよびエクスポート オプションは、アプリケーションから区切られます。 たとえば、アプリケーションをエクスポートすることがなく、パーティをエクスポートできます。 アプリケーションをインポートせず、パーティをインポートできます。<br />-どのパーティ、ビジネス プロファイル、およびインポートまたはエクスポートする契約を選択できます。<br />-同様に、企業間取引の成果物をインポート/エクスポートを引き続きできます[!INCLUDE[bts2013r2](../includes/bts2013r2-md.md)]、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2013、および[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]2010。<br/><br/>[バインド ファイルを使用して、インポートまたはエクスポートするには](../core/use-binding-files-to-import-or-export.md)|  
|BizTalk 管理コンソール|最新のルック アンド フィールに加えていくつか追加の変更は次のとおりです。<br /><br /> -同時に複数のホスト/ホスト インスタンスの設定を構成します。 たとえば、複数のホスト インスタンスの .NET CLR 設定を同時に設定できます。<br />-をフィルター処理、スキーマ、リソースなど、アプリケーションでの成果物を検索し、新しい検索機能を使用します。<br />-保留中のメッセージをトラブルシューティングするとき、ファイルに同時に複数の保留メッセージを保存できます。<br /><br />[BizTalk Server 管理コンソールを使用します。](../core/using-the-biztalk-server-administration-console.md)|  
|追加の更新プログラム|<ul><li>[!INCLUDE[HL7_CurrentVersion_FirstRef_md](../includes/hl7-currentversion-firstref-md.md)]基幹業務 (LOB) サーバーへの接続を開始し、接続経由でメッセージをプッシュします。 LOB では、接続の待機し、メッセージを送信します。 <br/><br/>以前[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]バージョンでは、HL7 MLLP 受信アダプター、HL7 に接続する LOB サーバーの間、待機、およびメッセージを送信します。 LOB は HL7 に接続し、し、メッセージを送信します。 </li><br/><li>Office web コンポーネント (OWC) が、インストールでは省略可能になりプログラムで個別に一覧表示されています。</li><br/><li>オーケストレーション インスタンス ID が XLANG FireEvent トレース出力に追加されます。</li></ul>|   
  
## <a name="deprecated--removed-list"></a>非推奨と削除の一覧  
  
|               プログラム               |   状態   |                                                                                                                                                代替                                                                                                                                                |
|-------------------------------------|------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|             RFID Mobile             |  削除   |                                                                                                                                                   なし                                                                                                                                                    |
|             RFID サーバー             |  削除   |                                                                                                                                                   なし                                                                                                                                                    |
| SharePoint SSOM/Web サービス アダプター |  削除   | クライアント側オブジェクト モデル (CSOM) オプションを使用します。<br /><br /> [Windows SharePoint Services アダプター](../core/windows-sharepoint-services-adapter.md)<br /><br /> [付録 b:Microsoft SharePoint アダプターをインストールします。](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md) |
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