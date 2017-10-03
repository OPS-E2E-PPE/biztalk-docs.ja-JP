---
title: "アダプターと BizTalk server アクセラレータ |Microsoft ドキュメント"
description: "すべてのアダプターと組み込みアダプター、BAP、HL7、Swift、RosettaNet、FileAct および InterAct を含む biztalk アクセラレータの概要"
caps.latest.revision: "3"
author: MandiOhlinger
manager: anneta
ms.custom: 
ms.date: 08/09/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: df7f26a1-e47b-4323-b9f0-58842c55a6f8
ms.author: mandia
ms.openlocfilehash: 9f3f73fd4b53161e5d3e0aa81ee660a56d8ff850
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="adapters-and-accelerators-in-biztalk-server"></a>アダプターと BizTalk server アクセラレータ
 [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]別のアダプターとのデータを受信し、さまざまなサービスにデータを送信し、システムの LOB アプリケーションを作成するためのアクセラレータが含まれます。 
 
このセクションでは、別のアダプターやアクセラレータで利用可能なについて説明します。[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]です。 

## <a name="out-of-the-box-adapters"></a>既定のアダプター
BizTalk Server をインストールするときに、使用する準備ができている組み込みのアダプターをインストールします。 これらのアダプターの一部には、ファイル、FTP、MQ Series、Service Bus、Logic Apps、POP3、SharePoint、および詳細が含まれます。

**[アダプターを使用して](../core/using-adapters.md)、それらのすべてを一覧表示し、また各アダプターを使用する方法を示します。**
 
## <a name="biztalk-adapter-pack"></a>BizTalk アダプター パック
[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]が付属して[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、WCF ベース アダプターの接続を提供し、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Oracle、SAP、Siebel、および SQL Server にします。 使用して、独自の WCF ベース アダプターを作成することも、[!INCLUDE[afproductnameshort_md](../includes/afproductnameshort-md.md)]です。 

**参照してください[BizTalk Adapter Pack](../adapters-and-accelerators/biztalk-adapter-pack.md)インストールをステップ実行チュートリアルおよびシナリオでは、これらのアダプターを構成する別のアダプターを使用してアプリケーションを作成し、取得WCFベースのサービスプロセスメッセージのことをお勧め**. 

一部のサンプルはいただけますも[http://go.microsoft.com/fwlink/p/?LinkID=196854](http://go.microsoft.com/fwlink/p/?LinkID=196854)です。 

## <a name="fileact-and-interact"></a>FileAct と対話します。
[!INCLUDE[swift_adapter_md](../includes/swift-adapter-md.md)]に含まれて[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]、間の接続を提供し、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]と社会 Worldwide 銀行間財務通信 (SWIFT) セキュリティで保護された IP ネットワーク (SIPN) にします。 

FileAct アダプターでは、ファイル、およびそれらのファイルに関連する情報の交換をセキュリティと堅牢性を提供します。 

InterAct アダプターでは、安全性と信頼性の高いメッセージ交換の各構造化された財務を提供します。 

**参照してください[FileAct および InterAct](../adapters-and-accelerators/fileact-interact/microsoft-biztalk-server-fileact-and-interact-adapters-documentation.md)をインストールして、これらのアダプターを構成する、いくつかのチュートリアルとシナリオの手順しのアーキテクチャを理解**です。 

## <a name="hl7"></a>HL7

[!INCLUDE[btaBTAHL7NoNumber_md](../includes/btabtahl7nonumber-md.md)]が付属して[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]との間の接続を提供し、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]と正常性レベル 7 (HL7) 標準に基づく医療コンピューター アプリケーションです。

**参照してください[HL7](../adapters-and-accelerators/accelerator-hl7/microsoft-biztalk-accelerator-for-hl7-documentation.md)インストールして、アダプターでは、いくつかのチュートリアルおよびシナリオでは、ステップを構成するには、アダプターの動作について説明し、スキーマ、受信確認をバッチ処理、検証、および複数をなど、さまざまな機能を使用**.

## <a name="rosettanet"></a>RosettaNet
BizTalk Accelerator for RosettaNet (BTARN) は BizTalk Server に付属し、開発と RosettaNet の標準ベースの統合ソリューションの展開を合理化します。 BTARN の RNIF RosettaNet Implementation Framework (); をサポートしていますこれは、ビジネス パートナーが共同作業して RosettaNet Partner Interface Process (Pip) を実行できるオープン ネットワーク アプリケーション フレームワークです。 

**参照してください[RosettaNet](../adapters-and-accelerators/accelerator-rosettanet/microsoft-biztalk-accelerator-for-rosettanet-documentation.md)をこのアクセラレータと、BizTalk Server ソリューションでの使用の詳細を参照してください。** 

## <a name="swift"></a>SWIFT
[!INCLUDE[btaA4SWIFTNoVersion_md](../includes/btaa4swiftnoversion-md.md)]が付属して[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]との間の接続を提供し、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]とメッセージ形式社会のワールドワイド銀行間財務通信 (SWIFT)。

アダプターを使用して[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]顧客、パートナー、およびシステム インテグレーターは、開発、配置、およびコア金融サービス アプリケーションのインフラストラクチャやビジネス プロセスの統合ソリューションのサポートを合理化できます。

**参照してください[SWIFT](../adapters-and-accelerators/accelerator-swift/microsoft-biztalk-accelerator-for-swift-documentation.md)をインストールして、アダプターを構成して、いくつかのチュートリアルでは、手順、および使用メッセージ修復 FIN 応答と FRR 成果物の詳細**です。

## <a name="get-some-help"></a>いくつかのヘルプを表示します。 
いくつかのヘルプを取得し、内の他のヘルプ、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]フォーラム[http://go.microsoft.com/fwlink/p/?LinkId=87695](http://go.microsoft.com/fwlink/p/?LinkId=87695)です。