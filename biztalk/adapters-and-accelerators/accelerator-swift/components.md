---
title: コンポーネント |Microsoft ドキュメント
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
ms.openlocfilehash: 6ca9c5fdb04ffd182a8c51963c1a5c7cf5e7f8c5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="components"></a>コンポーネント
使用する[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]リレーションシップ、エンタープライズ アプリケーション統合 (EAI) とアプリケーション、およびビジネス ワークフローの自動化 パートナー取引を容易に SWIFT 指向のミドルウェア ソリューションを実装するコンポーネントです。 たとえば、次のようなコンポーネントがあります。  
  
-   **SWIFT メッセージのスキーマです。** XML スキーマ定義言語 (XSD) を使用する、パイプライン コンポーネントに SWIFT を使用して XML に SWIFT ネイティブのフラット ファイル メッセージの解析を容易に準拠しているスキーマと[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]ランタイム。 迅速な対応データを XML に変換した後は、区切られたフラット ファイルまたは位置指定フラット ファイルなどの他の形式に変換するのにマップを使用する必要があります。 この変換では、既存のアプリケーションでこれらのファイルを使用することができます。 検証のみのシナリオなど、XML データのマッピングがないを使用することができますも。 SWIFT スキーマでは、SWIFT 定義のデータと書式指定規則を適用します。 このリリースで提供されたスキーマの一覧については、次を参照してください。[サポートされているメッセージ](../../adapters-and-accelerators/accelerator-swift/supported-messages.md)です。  
  
-   **SWIFT 検証ポリシーおよび Framework。** 使用する[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]ビジネス ルール エンジン (BRE) ポリシーを検証し、SWIFT 定義のデータ、形式、ネットワーク、および使用状況規則を適用します。 SWIFT の逆アセンブラーおよび[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]検証コンポーネントは、BRE を呼び出します。 エラー コレクション オブジェクトに検証エラーを収集し、エラーがあるメッセージはメッセージ ボックス データベースに公開する前に特別な昇格させたプロパティでマークされます。  
  
-   **SWIFT パイプライン コンポーネントです。** SWIFT メッセージを処理するのに BizTalk パイプラインの逆アセンブラおよびアセンブラ コンポーネントを使用するとします。 SWIFT の逆アセンブラー動的に SWIFT メッセージの型を解決、SWIFT メッセージのバッチを逆アセンブル、XML にメッセージを解析および SWIFT データ形式とネットワークと使用状況規則に対してメッセージを検証します。 SWIFT のアセンブラーは、SWIFT のフラット ファイル形式に戻し、XML データをシリアル化します。  
  
-   [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]  **検証コンポーネントです。** [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]アセンブリがクラス アプリケーション プログラミング インターフェイス (Api) BizTalk オーケストレーションの式図形で使用できるを提供します。 これらのクラスは、SWIFT の逆アセンブラーによって実行される同じ SWIFT メッセージの検証機能を提供します。 この機能は、メッセージの検証後に行うオーケストレーション内の場所 (たとえば、変換するか、SWIFT メッセージの変更) を使用します。  
  
-   **Message Repair and New Submission です。** メッセージの修復 and New Submission の機能を使用するには検証に失敗すること、または SWIFT の逆アセンブラーを解析できません、メッセージを修復するか作成して新しいメッセージを送信します。 MrsrRepair オーケストレーション、MRSR SharePoint サイトでこの機能を実装し、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]フォーム。  
  
-   **FRR 対応調整します。** FRR 対応調整は、結果として得られるメッセージ応答の相関関係のセットのカスタム処理を有効にすると、A4SWIFT によって最初に送信されたメッセージで FIN 応答を調整します。 FRR は FrrMain オーケストレーションによって実装され、FRR 受信場所と送信ポート、BizTalk Adapter for MQSeries です。  
  
-   **ソフトウェア開発キット (SDK)。** SDK は、ツール、チュートリアル、および SWIFT ベースの BizTalk ソリューションの開発と配置を支援するためにサンプルを提供します。 これらのソリューションは次のとおりです。  
  
    -   [エンド ツー エンドのチュートリアル](../../adapters-and-accelerators/accelerator-swift/end-to-end-tutorial2.md)  
  
    -   [BRE 配置ユーティリティ](../../adapters-and-accelerators/accelerator-swift/bre-deployment-utility.md)  
  
    -   [SWIFT ヘッダーおよびトレーラ スキーマ](../../adapters-and-accelerators/accelerator-swift/swift-header-and-trailer-schemas.md)  
  
-   **ドキュメントです。** [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]ヘルプでは、計画、開発、配置、および、SWIFT ベースの BizTalk ソリューションを維持する必要があるについて説明します。  
  
## <a name="see-also"></a>参照  
[実行時、メッセージの修復、FIN 応答、およびメッセージング](../../adapters-and-accelerators/accelerator-swift/runtime-message-repair-fin-response-and-messaging.md)