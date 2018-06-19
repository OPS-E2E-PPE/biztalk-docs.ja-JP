---
title: BizTalk Server に追加する BizTalk Accelerator 用 HL7 |Microsoft ドキュメント
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
ms.openlocfilehash: 7b9e9d1277c5d037a42fd85ca48ec13c8f1893a3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22209266"
---
# <a name="what-biztalk-accelerator-for-hl7-adds-to-biztalk-server"></a>BizTalk Server に追加する BizTalk Accelerator 用 HL7
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) を構築、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]医療統合システムにシステムを統合します。 医療組織を必要とする機能を追加します。  
  
 インストールする[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]の上に[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]機能が中核となる追加[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]エンジンです。 機能、ツール、およびユーティリティに追加する[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を提供します。 新機能にもアプリケーション プログラミング インターフェイス (Api) を追加、 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] SDK を提供します。  
  
## <a name="btahl72x-message-processing"></a>BTAHL72X メッセージの処理  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]さまざまな機能とカスタマイズの必要としないネイティブ、HL7 メッセージを処理するシステムを有効にするツールを追加します。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]すべてのドキュメントの仕様、アプリケーション、および開発および配置の全範囲の HL7 に固有のトランザクションを処理するために必要なコンポーネントが含まれます。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]サポートしている[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]2 倍のフラット ファイル スキーマです。 次[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]コンポーネントは実行[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]メッセージ処理の 2 倍にします。  
  
-   HL7 の逆アセンブラおよびアセンブラを解析し、ネイティブ HL7 メッセージをシリアル化可能にします。 逆アセンブラーまたはアセンブラーの一部である、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を一連のエンコードまたはメッセージの処理、XML からの変換を含む、デコードを実行するには、パイプライン、およびメッセージの検証。  
  
-   HL7 ベースのメッセージを送受信するシステムをできるようにする最小限の下位層プロトコル (MLLP) アダプターを[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]通常トランスポート MLLP のプロトコルを使用します。 MLLP アダプターにより[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]と[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]HL7 ベースのメッセージング アプリケーションと相互運用ができます。  
  
-   HL7 でエンコードされたメッセージを受信する、システムを有効にする HL7 メッセージ スキーマです。  
  
## <a name="btahl72xml-message-processing"></a>BTAHL72XML メッセージの処理  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]さまざまな機能と XML メッセージを処理するシステムを有効にするツールを追加します。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]HL7 メッセージを XML 形式を有効にするために変換します[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、する XML を使用して内部的には、メッセージに対して操作を実行します。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]HL7 V2 用のみには、XML への変換を実行します。ネイティブであるため、X メッセージはフラット ファイル形式です。 XML 形式では、2. XML メッセージの変換を行うことはできません。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]解析し、変換せずにこれらのメッセージを検証します。  
  
 サポートされている XML メッセージ スキーマは、 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]HL7 V2 の HL7 組織によって生成された 2XML スキーマです。XML バージョン、および[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]HL7 V2 に使用する 2 X スキーマです。X のバージョンのメッセージ (フラット ファイル形式)。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]ドキュメントの仕様、アプリケーション、および開発および配置のすべての範囲を処理するために必要なコンポーネントが含まれています[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]2XML トランザクションです。 次[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]コンポーネント実行[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]2XML メッセージの処理。  
  
-   XML 逆アセンブラおよびアセンブラを解析し、HL7 メッセージに対応する XML メッセージをシリアル化システムを有効にします。 XML 逆アセンブラーまたはアセンブラーの機能の強化が加えられて、 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] XML 逆アセンブラおよびアセンブラ、自動受信確認とメッセージの検証を追加します。  
  
-   HL7 と互換性のある XML スキーマ (V2 両方の HL7 メッセージを受信する、システムを有効にするには。X と V2 です。XML メッセージの場合)。 システムでは、V2 に変換します。メッセージを XML メッセージ (V2 x。XML メッセージは既に XML で)、および XML が有効になっている別のシステムに送信します。 同様に、 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] XML メッセージの受信し、送信用 HL7 に変換することができます。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]と共に HL7 パーサー、マップ、およびその他の XML ベースのドキュメントの仕様を使用して、HL7 に固有のデータから、または別の形式を変換[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ツール スキーマとマップを呼び出すことです。 たとえば、標準 HL7 V2.0 の形式または V2.5 形式でインターチェンジを受信し、そのデータを既存の医療アプリケーションが使用できる別の形式に変換する可能性があります。  
  
## <a name="validation"></a>検証  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]HL7 V2 の検証を実行します。メッセージの X[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を実行できません。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]HL7 メッセージのヘッダーの構文とスキーマの検証が自動的に実行し、自動的に HL7 メッセージの本文の一部の構造の検証を実行します。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]その機能を有効にする場合、HL7 メッセージの本文のスキーマの検証を実行 (を参照してください[検証の設定](../../adapters-and-accelerators/accelerator-hl7/validation-settings.md))。  
  
 HL7 でエンコードされたメッセージの本文の検証には、スキーマ、データ形式、いくつかのヘッダーと本文フィールド、および列挙値が含まれています。 2. XML メッセージの検証には、標準の XML 検証である、そのスキーマに対する検証が含まれています。 詳細については、次を参照してください。 [BTAHL72X フラット ファイル処理](../../adapters-and-accelerators/accelerator-hl7/btahl72x-flat-file-processing.md)と[BTAHL72XML 処理](../../adapters-and-accelerators/accelerator-hl7/btahl72xml-processing.md)です。  
  
## <a name="auto-acknowledgment"></a>自動受信確認  
 メッセージング システムの信頼性を確保する HL7 に受信確認 (ACK) メッセージを要求するように[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成設定に基づいて自動的に生成されます。  
  
 元のモードの Ack では、メッセージ ヘッダーと本文の検証を確認します。 強化されたモードで[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]Ack の 2 つの型を生成: accept ヘッダーの検証に送信される確認とアプリケーション ACK メッセージ全体の検証に送信します。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]メッセージを受信する基幹業務アプリケーションによって遅延確認を生成[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。  
  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]双方向メッセージのトランスポートをサポートする受信確認の処理を容易になります。  
  
## <a name="batching"></a>バッチ処理  
 保存処理のオーバーヘッドをバッチ モードでドキュメントを処理することができます。 バッチへの応答をバッチすることも可能です。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]HL7 のバッチ処理の 3 種類を有効に 2.X メッセージ。  
  
-   システムが、バッチとしてメッセージを受信し、し、個別のメッセージにフラグメント、バッチを受信します。  
  
-   バッチ/バッチ out, をシステム両方を受け取るし、バッチとしてメッセージを送信します。  
  
-   システムが個別のメッセージとして受信したメッセージのバッチを送信する、バッチを作成します。  
  
    > [!NOTE]
    >  [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]V2 のバッチ処理の機能を提供しません。XML メッセージです。  
  
## <a name="logging"></a>ログ記録  
 トラブルシューティングを強化するために[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]エラーまたはシステム コンポーネントによって通知する警告の報告を有効にします。 このようなイベントをフィルター処理、いずれかの 3 つのログ ストアに保存できます ([!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]イベント ログ、WMI、または[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)][!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]ログ ストア)、またはを使用してそれらをカスタマイズする、 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] SDK。  
  
## <a name="configuration-explorer"></a>エクスプ ローラーの構成  
 構成することができます[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]パーティ、バッチ、受信確認、および、ログに格納[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラーで、ツールには追加の管理ツールを[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を提供します。 このツールでは、バッチはパーティ レベルで処理を開始することもできます。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] SDK では、これらの設定をカスタマイズできます。 プログラムでします。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server がビジネス ニーズを解決する方法](../../adapters-and-accelerators/accelerator-hl7/how-biztalk-server-solves-the-business-need2.md)