---
title: BizTalk Server1 における EDI のサポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7cddab7a-99ef-4dbb-bb74-9e3d03df3996
caps.latest.revision: 37
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1371d707729c6c0efbc8277dde671d353ab400aa
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979963"
---
# <a name="edi-support-in-biztalk-server"></a>BizTalk Server における EDI のサポート
このトピックでは、EDI および BizTalk Server が EDI をサポートする方法の簡単な概要を説明します。  
  
## <a name="introduction-to-edi"></a>EDI の概要  
 電子データ交換 (EDI) は、ビジネスの取引先間でデータを電子的に交換するために最も広く使用されている方法です。 EDI は、主としてメッセージ指向型のプロセスです。 ドキュメントは、バッチ処理されたトランザクション セットを含むことができるフラット ファイルとして実装されます。 バッチ インターチェンジには複数のグループを含むことができ、各グループには複数のトランザクション セットまたはメッセージを含むことができます。  
  
 EDI は、標準機関で合意された特定のデータ交換方式で構成されます。 主要な EDI 標準は、X12 と EDIFACT です。X12 は ANSI で標準化され、主に北米で使用されています。EDIFACT は国連で標準化され、主に米国以外で使用されています。 他の標準は、これらの標準から派生したものです。たとえば、HIPAA は X12 から派生し、韓国の KEDIFACT は EDIFACT から派生しました。 これらの標準は、メッセージ構造や受領確認スキームはきわめて似ていますが、明らかな違いがあります。  
  
 EDI 標準では、以下を規定しています。  
  
- ドキュメントの交換に使用する形式、文字セット、およびデータ要素  
  
- EDI トランザクションで使用するエンベロープ  
  
- 配信を確認するために受領確認が必要  
  
- 1 回限りの確実な配信を行う方法と、破損したデータや正しくないデータの自動検出および報告を行う方法  
  
  EDI 標準はドキュメント構造の規則を定めていますが、送信される具体的な情報およびその使用方法については取引先間で合意する必要があります。 2 つの取引先を接続する EDI システムの設計は、標準によって要求される内容と、取引先間で合意した内容に基づいて決まります。 EDI メッセージングの詳細については、[EDI メッセージング](../core/edi-messaging.md)を参照してください。  
  
> [!NOTE]
>  EDI メッセージは、トランスポートと区別されます。 EDI 標準では、メッセージ トランスポートについての規定はないため、EDI メッセージはさまざまな方法で送信できます。  
  
## <a name="how-edi-is-implemented-in-biztalk-server"></a>BizTalk Server での EDI の実装方法  
 BizTalk Server には、EDI のサポートを提供するネイティブな機能が含まれています。 EDI は製品に組み込まれています違いますが、アダプターやアクセラレータなど、アドイン。  
  
 **インターチェンジ処理**  
  
 次受信側の EDI 機能を実行し、ルールを適用するパイプラインで送信側の処理は EDI 標準によって決まります。  
  
- 受信 EDI メッセージの処理。これには、インターチェンジの検証および受信確認の生成が含まれます。  
  
- 送信 EDI メッセージの生成と送信。これには、インターチェンジの検証、および構成によっては受信した確認の処理が含まれます。  
  
  **バッチ処理**  
  
  バッチ処理は、受信パイプラインおよびオーケストレーションによって処理されます。  
  
- 受信したバッチ インターチェンジを分割する必要がある場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は構成要素であるトランザクション セットに分割して、各トランザクション セットに対して XML ファイルを生成し、送信側バッチの生成に必要なプロパティを昇格します。  
  
- 受信したバッチ インターチェンジを保持する場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]トランザクション セットと、バッチが受信したときに含まれているグループが保持されるように、バッチを処理します。  
  
- 受信したバッチ インターチェンジを構成する必要がある場合は、受信した複数の EDI トランザクション セットをバッチ処理し、1 つの送信インターチェンジとしてグループ化します。  
  
- 複数のパーティがバッチ インターチェンジをサブスクライブしている場合は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は各パーティにバッチのコピーを送信します。  
  
  **取引先契約**  
  
  取引先は、取引先とのアグリーメントを相互に定義します。このアグリーメントは、BizTalk Server 管理コンソールで定義された一連のプロパティです。 これらのパーティのプロパティと、送信と受信のポートおよび場所のプロパティによって、受信側と送信側の EDI 処理が決まります。 パートナー アグリーメントを取引先の詳細については、[取引先アグリーメント](../core/trading-partner-agreement.md)を参照してください。  
  
  **インターチェンジの状態**  
  
  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、EDI に固有の状態レポートを提供します。 これらの状態レポートには、インターチェンジに関連付けられた確認を含め、EDI ドキュメント交換トランザクションの包括的な状態が含まれます。  
  
## <a name="edi-components-in-biztalk-server"></a>BizTalk Server の EDI コンポーネント  
 EDI 処理に使用される Microsoft BizTalk Server コンポーネントを以下に示します。  
  
- EDI ドキュメントの処理に必要なアイテム (パイプライン、オーケストレーション、スキーマなど) を含む BizTalk EDI アプリケーション。  
  
  > [!NOTE]
  >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で EDI 機能を構成すると、構成プログラムによってこのアプリケーションが作成されます。 EDI インターチェンジを処理するアプリケーションを作成する場合は、アプリケーションから BizTalk EDI アプリケーションへの参照を追加する必要があります。 詳細については、[、BizTalk Server EDI アプリケーションへの参照を追加する方法](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782)を参照してください。  
  
- BizTalk EDI 受信パイプライン (EdiReceive パイプライン) では、EDI でエンコードされたドキュメントの解析、EDI バッチの分割、EDI でエンコードされたドキュメントの XML エンコードへの変換、EDI および XSD 検証、HIPAA X12 サブドキュメントの分割を行います。 詳細については、[EDI の受信コンポーネント](../core/edi-receive-components.md)を参照してください。  
  
- BizTalk EDI 送信パイプライン (EdiSend パイプライン) では、XML ドキュメントの X12 または EDIFACT エンコードへの変換、EDI でエンコードされたドキュメントのシリアル化、EDI および XSD 検証を行います。 詳細については、[EDI 送信コンポーネント](../core/edi-send-components.md)を参照してください。  
  
- 取引先管理 (TPM) ユーザー インターフェイスを使用すると、EDI ドキュメントの交換および AS2 ドキュメントのトランスポートに関与する取引先の処理プロパティを設定できます。 詳細については、[EDI 処理におけるアグリーメントのロール](../core/the-role-of-agreements-in-edi-processing.md)と**EDI および AS2 UI** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]を参照してください。
  
- バッチ処理オーケストレーションでは、バッチ インターチェンジの送信のために、EDI インターチェンジのバッチ処理を行い、コンテキスト プロパティを設定します。 ルーティング オーケストレーションは、メッセージが複数のバッチに一致する状況に対処し、メッセージのコピーを必要な数だけ作成します。 詳細については、[着信バッチの処理](../core/processing-incoming-batches.md)と[送信 EDI メッセージのバッチ処理](../core/batching-outgoing-edi-messages.md)を参照してください。  
  
- 状態レポートのユーザー インターフェイスでは、EDI インターチェンジおよび関連する確認の包括的な状態を把握できます。 詳細については、[EDI および AS2 状態レポート](../core/edi-and-as2-status-reporting.md)を参照してください。  
  
- Visual Studio のデザイン時ツールでは、インスタンスの生成、インスタンスの検証、スキーマの検証、マップのテスト、およびマップの検証を行うことができます。 詳細については、[デザイン時 XML ツールを使用して](../core/using-design-time-xml-tools.md)を参照してください。  
  
- スキーマ リポジトリには、X12、EDIFACT、HIPAA X12N 4010A XSD、EANCOM、および管理スキーマがあります。 詳細については、[EDI ドキュメント スキーマのサポート](../core/edi-document-schema-support.md)を参照してください。  
  
- 移行ツール (パーティ移行ツール) では、EDI パーティ データを BizTalk Server 2006 R2 または BizTalk Server 2009 から BizTalk Server まで移行することができます。 詳細については、[EDI アイテムを BizTalk Server の以前のバージョンから移行](http://msdn.microsoft.com/library/b956a97e-03d0-47ea-a2ce-c07a339c0f2c)を参照してください。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server での EDI 処理](../core/edi-processing-in-biztalk-server.md)   
 [BizTalk Server における HIPAA のサポート](../core/hipaa-support-in-biztalk-server.md)   
 [EDI のサポートの問題](../core/edi-support-issues.md)   
 [EDI ソリューションのアーキテクチャ](../core/edi-solution-architecture.md)   
 [EDI および AS2 状態レポート](../core/edi-and-as2-status-reporting.md)   
 [BizTalk Server EDI ソリューションの開発と構成](../core/developing-and-configuring-biztalk-server-edi-solutions.md)