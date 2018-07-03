---
title: BizTalk Server に追加する BizTalk Accelerator 用 HL7 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- batching, documents
- BTAHL7, batching
- messages, acknowledgements
- messages, auditing
- Configuration Explorer
- BTAHL7, message validation
- BTAHL7, Configuration Explorer
- messages, processing
- BTAHL7, BizTalk Server
- BTAHL7, message processing
- auditing, messages
- BTAHL7, auditing
- validating, messages
- acknowledgements, messages
- BTAHL7, logging
- BizTalk Server, BTAHL7
- messages, validating
- logging
- BTAHL7, acknowledgements
- errors, logging
ms.assetid: 862e9f26-588a-4e91-8ebc-f53aab6f46c2
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1ab7cd2d5abe126cc246be678c192c037ee48c90
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980059"
---
# <a name="what-biztalk-accelerator-for-hl7-adds-to-biztalk-server"></a>BizTalk Server に追加する BizTalk Accelerator 用 HL7
Microsoft BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) ビルドを[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]医療の統合システムにシステムを統合します。 医療の組織に必要な機能を追加します。  
  
 インストールする[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]の上に[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] コア機能が追加されます[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]エンジン。 機能、ツール、およびユーティリティに追加する[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を提供します。 何にもアプリケーション プログラミング インターフェイス (Api) を追加、 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] SDK を提供します。  
  
## <a name="btahl72x-message-processing"></a>BTAHL72X メッセージの処理  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] さまざまな機能とカスタマイズを必要としないネイティブ、HL7 メッセージを処理するシステムを有効にするツールを追加します。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] すべてのドキュメントの仕様、アプリケーション、および完全な範囲の HL7 に固有のトランザクションの処理の開発および展開する必要があるコンポーネントが含まれています。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] サポート[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]2 倍のフラット ファイル スキーマ。 次[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]コンポーネントの実行[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]メッセージ処理の 2 倍にします。  
  
- HL7 の逆アセンブラーとアセンブラーを解析し、ネイティブ HL7 メッセージをシリアル化システムを有効にします。 逆アセンブラーとアセンブラーの一部である、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]パイプラインで、一連のメッセージの処理、XML の変換など、デコードまたはエンコードを実行して、メッセージの検証。  
  
- HL7 ベースのメッセージを送受信するシステムをできるようにするための最小限の下位レイヤー プロトコル (MLLP) アダプターが[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]MLLP プロトコルを使用して通常転送します。 MLLP アダプターにより[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]と[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]は HL7 ベースのメッセージング アプリケーションと相互運用できます。  
  
- HL7 でエンコードされたメッセージを受信するシステムを有効にする HL7 メッセージ スキーマです。  
  
## <a name="btahl72xml-message-processing"></a>BTAHL72XML メッセージの処理  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] さまざまな機能と XML メッセージを処理するシステムを有効にするツールを追加します。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 有効にするには、HL7 メッセージを XML 形式に変換[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、この XML を使用して内部的には、メッセージに対して操作を実行します。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] HL7 V2 ののみ、XML への変換を実行します。ネイティブであるため、X メッセージはフラット ファイル形式です。 XML 形式である 2. XML メッセージの場合も、変換は実行されません。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 解析し、変換せずにこれらのメッセージを検証します。  
  
 サポートされている XML メッセージ スキーマは、 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]HL7 V2 の HL7 組織で生成された 2XML スキーマ。XML バージョン、および[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]2 X スキーマが HL7 V2 に使用します。X のバージョンは、(フラット ファイル形式) でメッセージです。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] ドキュメントの仕様、アプリケーション、および開発し、デプロイの完全な範囲を処理するために必要なコンポーネントが含まれています[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]2XML トランザクション。 次[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]コンポーネント実行[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]2XML メッセージの処理。  
  
- XML 逆アセンブラーとアセンブラーを解析し、HL7 メッセージに対応する XML メッセージをシリアル化システムを有効にします。 XML 逆アセンブラーおよびアセンブラーの機能強化の機能以外にも、 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] XML 逆アセンブラーとアセンブラー、自動受信確認とメッセージの検証を含めます。  
  
- HL7 と互換性のある XML スキーマ (V2 両方の HL7 メッセージを受信するシステムを有効にします。X と V2 の場合は。XML メッセージの場合)。 システムでは、V2 に変換します。メッセージを XML メッセージ (V2 x。XML メッセージは既に xml 形式で)、および XML が有効な別のシステムに送信します。 同様に、 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 、XML メッセージを受信し、送信するため HL7 に変換できます。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] と共に HL7 パーサー、マップ、およびその他の XML ベースのドキュメント仕様を使用して、HL7 に固有のデータから、または別の形式を変換[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]スキーマとマップを呼び出すツール。 たとえば、標準 HL7 V2.0 形式または V2.5 形式でインターチェンジを受信し、既存の医療アプリケーションが使用できる別の形式に変換する可能性があります。  
  
## <a name="validation"></a>検証  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] HL7 V2 の検証を実行します。メッセージの X[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を実行できません。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] HL7 メッセージのヘッダーの構文とスキーマの検証を自動的に実行し、自動的に HL7 メッセージの本文の一部の構造の検証を実行します。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] その機能を有効にした場合に、HL7 メッセージの本文のスキーマの検証を実行します (を参照してください[検証の設定](../../adapters-and-accelerators/accelerator-hl7/validation-settings.md))。  
  
 HL7 でエンコードされたメッセージの本文の検証には、スキーマ、データ形式、いくつかのヘッダーと本文フィールド、および列挙値が含まれています。 2. XML メッセージの検証には、標準の XML 検証である、そのスキーマに対して検証が含まれています。 詳細については、次を参照してください。 [BTAHL72X フラット ファイル処理](../../adapters-and-accelerators/accelerator-hl7/btahl72x-flat-file-processing.md)と[BTAHL72XML 処理](../../adapters-and-accelerators/accelerator-hl7/btahl72xml-processing.md)します。  
  
## <a name="auto-acknowledgment"></a>自動受信確認  
 HL7 に受信確認 (ACK) メッセージを要求するメッセージング システムの信頼性を確保することがあります[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成設定に基づいて自動的に生成されます。  
  
 元のモードの Ack では、メッセージ ヘッダーと本文の検証を確認します。 強化されたモードで[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]Ack の 2 つの型を生成します: accept ヘッダーの検証に送信される確認とアプリケーションの完全なメッセージの検証に送信される確認します。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] メッセージを受信する基幹業務アプリケーションによって遅延確認を生成します。[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。  
  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 双方向メッセージのトランスポートをサポートしている受信確認の処理を容易になります。  
  
## <a name="batching"></a>バッチ処理  
 保存処理のオーバーヘッドがバッチ モードでドキュメントを処理することができます。 バッチへの応答をバッチすることも可能です。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] HL7 のバッチ処理の 3 つの種類により、2.X のメッセージ。  
  
- システムは、バッチとしてメッセージを受信し、し、個別のメッセージにフラグメントが、バッチ処理を受信します。  
  
- バッチ処理/、バッチ処理をシステムは受信し、メッセージをバッチとして送信します。  
  
- 作成、バッチ処理システムが個別のメッセージとして受信したメッセージのバッチを送信します。  
  
  > [!NOTE]
  >  [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] V2 のバッチ処理機能を提供しません。XML メッセージです。  
  
## <a name="logging"></a>ログ記録  
 トラブルシューティングを強化するために[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]エラーまたはシステム コンポーネントによって通知する警告の報告を有効にします。 このようなイベントをフィルター処理、任意の 3 つのログ ストアに格納できます ([!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]イベント ログ、WMI、または[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)][!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]ログ ストア)、またはを使用してそれらをカスタマイズ、 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] SDK。  
  
## <a name="configuration-explorer"></a>エクスプ ローラーの構成  
 構成できる[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]パーティ、バッチ、受信確認、および、ログに格納[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラー、ツールには追加の管理ツールを[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を提供します。 このツールでは、バッチはパーティ レベルで処理を開始することもできます。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] SDK では、これらの設定をカスタマイズできます。 プログラムを使用します。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server がビジネス ニーズを解決するしくみ](../../adapters-and-accelerators/accelerator-hl7/how-biztalk-server-solves-the-business-need2.md)