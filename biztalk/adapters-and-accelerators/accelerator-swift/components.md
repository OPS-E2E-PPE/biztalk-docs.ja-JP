---
title: コンポーネント |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- architecture, components
ms.assetid: 8793534f-5bd7-4cd3-9a42-8f0895f91007
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6c8595aafb14b42240a5f781faf481977be2b821
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37014683"
---
# <a name="components"></a>Components
Microsoft を使用する[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]パートナー関係、エンタープライズ アプリケーション統合 (EAI)、およびアプリケーションとビジネス ワークフローの自動化の取引先を容易にする SWIFT 指向のミドルウェア ソリューションを実装するコンポーネント。 たとえば、次のようなコンポーネントがあります。  
  
- **SWIFT メッセージのスキーマです。** XML スキーマ定義言語 (XSD) を使用する-パイプライン コンポーネントに、SWIFT を使用して XML に、ネイティブ SWIFT フラット ファイル メッセージの解析を容易に準拠しているスキーマと[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]ランタイム。 SWIFT のデータを XML に変換した後、マップを使用して区切られたフラット ファイルまたは位置指定フラット ファイルなど、別の形式に変換します。 この変換では、既存のアプリケーションでこれらのファイルを使用することができます。 検証のみのシナリオのようにすべてのマッピングがない XML データを使用することもできます。 SWIFT スキーマでは、SWIFT 定義のデータと書式ルールも適用します。 このリリースで提供されるスキーマの完全な一覧を参照してください。[サポートされているメッセージ](../../adapters-and-accelerators/accelerator-swift/supported-messages.md)します。  
  
- **SWIFT 検証ポリシーとフレームワーク。** 使用する[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]ビジネス ルール エンジン (BRE) ポリシーを検証し、SWIFT 定義のデータ、形式、ネットワーク、および使用状況規則を適用します。 SWIFT 逆アセンブラーと[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]検証コンポーネントは、BRE を呼び出します。 検証エラーがエラー コレクション オブジェクトに収集され、エラーがあるメッセージはメッセージ ボックス データベースに公開する前に特別な昇格させたプロパティでマークされます。  
  
- **SWIFT パイプライン コンポーネント。** SWIFT メッセージを処理するのにには、BizTalk パイプラインの逆アセンブラーおよびアセンブラー コンポーネントを使用します。 SWIFT 逆アセンブラーに動的に SWIFT メッセージの型を解決、SWIFT メッセージのバッチを逆アセンブル、XML にメッセージを解析および SWIFT データ形式と規則をネットワークと使用状況に対してメッセージを検証します。 SWIFT アセンブラーでは、SWIFT のフラット ファイル形式に XML データをシリアル化します。  
  
- [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]  **検証コンポーネントです。** [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]アセンブリ クラス アプリケーション プログラミング インターフェイス (Api) BizTalk オーケストレーションの式図形で使用できるを提供します。 これらのクラスは、SWIFT 逆アセンブラーによって実行される同じ SWIFT メッセージの検証機能を提供します。 この機能は、オーケストレーションで行われます (たとえば後の変換や、SWIFT メッセージの変更) にメッセージの検証を使用します。  
  
- **Message Repair and New Submission します。** メッセージの修復 and New Submission の機能を使用するには検証に失敗すること、または SWIFT 逆アセンブラーを解析できません、メッセージを修復するか、作成して、新しいメッセージを送信します。 MrsrRepair オーケストレーション、MRSR SharePoint サイトでこの機能を実装し、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]フォーム。  
  
- **FRR Response Reconciliation します。** FRR Response Reconciliation は、結果として得られるメッセージ応答の相関関係のセットのカスタム処理を有効にすると、A4SWIFT によって最初に送信されたメッセージを FIN 応答を調整します。 FRR が FrrMain オーケストレーションを介して実装されますが、として FRR 受信場所と送信ポート、BizTalk Adapter for MQSeries します。  
  
- **ソフトウェア開発キット (SDK)。** SDK は、ツール、チュートリアル、および SWIFT ベースの BizTalk ソリューションの開発と展開を支援するためにサンプルを提供します。 これらのソリューションは次のとおりです。  
  
  -   [エンド ツー エンドのチュートリアル](../../adapters-and-accelerators/accelerator-swift/end-to-end-tutorial2.md)  
  
  -   [BRE 配置ユーティリティ](../../adapters-and-accelerators/accelerator-swift/bre-deployment-utility.md)  
  
  -   [SWIFT ヘッダーおよびトレーラー スキーマ](../../adapters-and-accelerators/accelerator-swift/swift-header-and-trailer-schemas.md)  
  
- **ドキュメントです。** [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] ヘルプでは、計画、開発、デプロイ、および、SWIFT ベースの BizTalk ソリューションを維持する必要がありますについて説明します。  
  
## <a name="see-also"></a>参照  
[ランタイム、メッセージの修復、FIN 応答、メッセージング](../../adapters-and-accelerators/accelerator-swift/runtime-message-repair-fin-response-and-messaging.md)