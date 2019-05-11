---
title: BizTalk Server における HIPAA のサポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d1ad8c64-6375-4364-80ce-440db943c222
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 06d59b485553f2a994dc3dcc47ce14f58a469735
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65344355"
---
# <a name="hipaa-support-in-biztalk-server"></a>BizTalk Server における HIPAA のサポート
このトピックでは、HIPAA の概要を提供します。 どのように[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]HIPAA をサポートしています。  
  
## <a name="introduction-to-hipaa"></a>HIPAA の概要  
 Health Insurance Portability と Accountability Act of 1996 (HIPAA) など、要求、送金、適格性、要求の状態の要求および応答のトランザクションを電子的に行うときに、必須の標準を使用する管理対象のエンティティが必要ですし、その他。 HIPAA の適用対象事業は、正常性の計画、クリアリング ハウス、およびほとんどの医療プロバイダーです。  
  
## <a name="hipaa-support-in-biztalk-server"></a>BizTalk Server における HIPAA のサポート  
 マイクロソフトは医療を支援して、準ずる組織が医療が配信され、機関の効率を向上します。 Microsoft は、時間と HIPAA の規制を遵守する必要がありますの組織で費やすコストを削減する予定です。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] により組織が対応する自動化されたビジネス プロセスを作成するという課題は、接続し、多様な医療システム間で相互運用。 HIPAA 影響を受けた組織を使用して[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]の開発、実装、および連邦法とも準拠しているトランザクションに準拠したソリューションの統合に役立つ機能です。  
  
[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] HIPAA のサポートを提供するネイティブ機能が含まれています。 この機能は、アダプターやアクセラレータなどの製品へのアドインではなく、 これは、製品に組み込まれています。 [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] EDI を含むコンポーネントとするために必要な機能に準拠すると共に、HIPAA 規制を適切に管理および評価されたビジネス プロセスとしての HIPAA を導入します。  
  
> [!NOTE]
>  [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] HIPAA version 5010 と 4010 をサポートしています。  
  
## <a name="hipaa-documentation-in-biztalk-server"></a>BizTalk Server の HIPAA ドキュメント  
 主要な EDI 標準は、(ANSI によって標準化され、主に北米で使用)、X12 と EDIFACT (国連によって標準化されていると、主に米国外で使用)。 HIPAA は X12 から派生した標準です。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ネイティブの X12 の一部として HIPAA サポートを提供します。 EDI 機能。 そのため、サポート、X12 への参照を表示場所、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ドキュメントについては、このサポートにも当てはまります HIPAA 処理、特に明示しない限り、します。  
  
 次のセクションは[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]HIPAA に関する具体的な情報があります。  
  
 **作業の開始**  
  
- [HIPAA トランザクション セット](../core/hipaa-transaction-sets.md)  
  
  **計画および設計**  
  
- [HIPAA ドキュメント スキーマ バージョン 5010](../core/hipaa-document-schema-version-5010.md)  
  
- [HIPAA スキーマのトリガー フィールドの注釈](../core/hipaa-schema-trigger-field-annotations.md)  
  
- [HIPAA サブドキュメントの分割](../core/splitting-hipaa-subdocuments.md)  
  
  **開発**  
  
- [EDI スキーマの変更](../core/modifying-edi-schemas.md) 

- [エンベロープ スキーマでの列挙のカスタマイズ](../core/customizing-enumerations-in-the-envelope-schema.md)

- [クロスフィールド検証の構成](../core/configuring-cross-field-validation.md)

  
 **トラブルシューティング**  
  
-   [EDI 受信処理に関する既知の問題](../core/known-issues-with-edi-receive-processing.md)  
  
-   [EDI ソリューションで使用される XML ツールに関する既知の問題](../core/known-issues-with-xml-tools-used-with-edi-solutions.md)  
  
## <a name="more-information-about-hipaa"></a>HIPAA の詳細について  
  
-   移動するための電子データ交換 Accredited Standards Committee American National Standards Institute については、 [ASC X12 ホーム](http://www.x12.org/)します。  
  
-   X12 の保険小委員会についてとその実装については、HIPAA で採用されているガイドを参照してください[Washington Publishing Company の HIPAA EDI ガイド](http://www.wpc-edi.com/)します。
  
-   電子データ交換のワークグループについてを参照してください[Workgroup for Electronic Data Interchange ホーム ページ](http://www.wedi.org/)します。