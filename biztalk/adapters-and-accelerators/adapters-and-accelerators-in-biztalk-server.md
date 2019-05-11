---
title: BizTalk Server のアダプターとアクセラレータ |Microsoft Docs
description: すべてのアダプターと組み込みのアダプター、BAP、HL7、Swift、RosettaNet、FileAct および InterAct を含む biztalk アクセラレータの概要
caps.latest.revision: 3
author: MandiOhlinger
manager: anneta
ms.custom: ''
ms.date: 08/09/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: df7f26a1-e47b-4323-b9f0-58842c55a6f8
ms.author: mandia
ms.openlocfilehash: 5d1d43e53a385f8b2116845fac0a4303f4ec388d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65367343"
---
# <a name="adapters-and-accelerators-in-biztalk-server"></a>BizTalk Server のアダプターとアクセラレータ
 [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] 別のアダプターとアクセラレータのデータを受信、さまざまなサービスにデータを送信し、LOB システムとアプリケーションを作成するために含まれています。 
 
このセクションでは、別のアダプターとアクセラレータで使用可能なについて説明します。[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]します。 

## <a name="out-of-the-box-adapters"></a>ボックスのアダプター
BizTalk Server をインストールするときに、使用することができる組み込みのアダプターをインストールします。 これらのアダプターの一部には、ファイル、FTP、MQ Series、Service Bus、Logic Apps、POP3、SharePoint などが含まれます。

**[アダプターを使用して](../core/using-adapters.md)、それらのすべてを一覧表示し、各アダプターを使用する方法も示します。**
 
## <a name="biztalk-adapter-pack"></a>BizTalk アダプター パック
[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]に含まれている[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、接続する WCF ベース アダプターを提供し、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Oracle、SAP、Siebel、および SQL Server にします。 使用して、独自の WCF ベース アダプターを作成することも、[!INCLUDE[afproductnameshort_md](../includes/afproductnameshort-md.md)]します。 

**参照してください[BizTalk Adapter Pack](../adapters-and-accelerators/biztalk-adapter-pack.md)インストールをステップ実行のチュートリアルとシナリオでは、これらのアダプターを構成する別のアダプターを使用してアプリケーションを作成し、WCF ベースのサービス プロセスのメッセージのことをお勧めを取得します。**

## <a name="adapters-for-enterprise-applications"></a>Adapters for Enterprise Applications
これらのアダプターに含まれている[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。 これらのアダプターを使用して、JD Edwards EnterpriseOne、JD Edwards OneWorld を BizTalk Server、PeopleSoft Enterprise、TIBCO Enterprise Message Service では、TIBCO Rendezvous とを接続します。

**参照してください[BizTalk Adapter for Enterprise Applications](biztalk-adapters-for-enterprise-applications.md)インストールをステップ実行のチュートリアルとシナリオでは、これらのアダプターを構成するには、別のアダプターを使用するアプリケーションを作成します。** 


## <a name="fileact-and-interact"></a>FileAct および InterAct
[!INCLUDE[swift_adapter_md](../includes/swift-adapter-md.md)]に含まれている[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]、間の接続を提供し、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]社会世界銀行間金融電気通信 (SWIFT) Secure IP Network (SIPN) にします。 

FileAct アダプターでは、ファイル、およびそれらのファイルに関連する情報の交換を安全かつ高い信頼性を提供します。 

InterAct アダプターは、構造化された個々 の財務メッセージの交換を安全かつ高い信頼性を提供します。 

**参照してください[FileAct および InterAct](../adapters-and-accelerators/fileact-interact/microsoft-biztalk-server-fileact-and-interact-adapters-documentation.md)をインストールして、これらのアダプターを構成、いくつかのチュートリアルとシナリオをステップ実行し、アーキテクチャの理解します。** 

## <a name="hl7"></a>HL7

[!INCLUDE[btaBTAHL7NoNumber_md](../includes/btabtahl7nonumber-md.md)]に含まれている[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]、間の接続を提供し、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]と正常性レベル 7 (HL7) の標準に基づく医療コンピューター アプリケーションです。

**参照してください[HL7](../adapters-and-accelerators/accelerator-hl7/microsoft-biztalk-accelerator-for-hl7-documentation.md)インストールして、アダプターでは、いくつかのチュートリアルとシナリオをステップを構成するには、アダプターの動作について説明し、スキーマ、受信確認をバッチ処理、検証、および詳細を含む、さまざまな機能を使用します。**

## <a name="rosettanet"></a>RosettaNet
BizTalk Accelerator for RosettaNet (BTARN) は、BizTalk Server に含まれているし、開発と RosettaNet の標準ベースの統合ソリューションの展開を合理化します。 BTARN の RNIF RosettaNet Implementation Framework (); をサポートしていますこれは、ビジネス パートナーに共同作業 RosettaNet Partner Interface Process (Pip) を実行できるようにするオープン ネットワーク アプリケーション フレームワークです。 

**参照してください[RosettaNet](../adapters-and-accelerators/accelerator-rosettanet/microsoft-biztalk-accelerator-for-rosettanet-documentation.md)については、このアクセラレータと BizTalk Server ソリューションを使用する詳細についてはします。** 

## <a name="swift"></a>SWIFT
[!INCLUDE[btaA4SWIFTNoVersion_md](../includes/btaa4swiftnoversion-md.md)]に含まれている[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]、間の接続を提供し、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]とメッセージ形式、Society for 世界銀行間金融電気通信 (SWIFT)。

アダプターを使用して[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]顧客、パートナー、およびシステム インテグレーターは、開発、展開、およびコア金融サービス アプリケーションのインフラストラクチャやビジネス プロセスの統合ソリューションのサポートを合理化できます。

**参照してください[SWIFT](../adapters-and-accelerators/accelerator-swift/microsoft-biztalk-accelerator-for-swift-documentation.md)をインストールして、アダプターを構成するステップのチュートリアルでは、実行し、メッセージの修復、FIN 応答と FRR 成果物を使用します。**

## <a name="get-some-help"></a>いくつかのヘルプを表示します。 
いくつかのヘルプを取得し、他のユーザーのため、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]フォーラムで[ http://go.microsoft.com/fwlink/p/?LinkId=87695](http://go.microsoft.com/fwlink/p/?LinkId=87695)します。