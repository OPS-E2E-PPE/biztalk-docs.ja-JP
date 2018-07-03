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
ms.openlocfilehash: 7817e3b69edd0a34c13b92128f7ddba0f28a5586
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37014763"
---
# <a name="hipaa-support-in-biztalk-server"></a>BizTalk Server における HIPAA のサポート
このトピックでは、HIPAA の概要を示し、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] がどのようにして HIPAA をサポートしているかについて簡単に説明します。  
  
## <a name="introduction-to-hipaa"></a>HIPAA の概要  
 1996 年に施行された医療保険の携行性と責任に関する法律 (Health Insurance Portability and Accountability Act: HIPAA) では、適用対象事業者が医療保険の支払請求、送金、受給資格、支払請求の状況に関する要求や応答などのトランザクションを電子的に行うときに強制基準に従うことを義務付けています。 HIPAA の適用対象事業は、正常性の計画、クリアリング ハウス、およびほとんどの医療プロバイダーです。  
  
## <a name="hipaa-support-in-biztalk-server"></a>BizTalk Server での HIPAA サポート  
 Microsoft は、医療機関およびそれに準ずる組織が医療サービスの提供と資金調達の方法を向上させることができるように、力を注いでいます。 また、組織が HIPAA の規制に準拠するために費やす必要のある時間と費用を削減することを目指しています。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、多様な医療システムにまたがって接続および相互運用されるビジネス プロセスを自動化する課題に組織が対応することを支援します。 HIPAA が適用される組織は [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の機能を使用して、連邦法およびトランザクションに準拠したソリューションの開発、実装、および統合に役立てることができます。  
  
[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] には HIPAA をサポートするネイティブ機能が含まれています。 この機能は、アダプターやアクセラレータなどの製品へのアドインではなく、 製品自体に組み込まれています。 [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] は、HIPAA 規制に準拠すると共に、適切に管理および評価されたビジネス プロセスとしての HIPAA を導入するために必要な、EDI のコンポーネントと機能を備えています。  
  
> [!NOTE]
>  [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] は、HIPAA Version 5010 と 4010 をサポートしています。  
  
## <a name="hipaa-documentation-in-biztalk-server"></a>BizTalk Server の HIPAA ドキュメント  
 主要な EDI 標準は、X12 と EDIFACT です。X12 は ANSI によって標準化され、主に北米で使用されています。EDIFACT は国連によって標準化され、主に米国外で使用されています。 HIPAA は X12 から派生した標準です。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] はネイティブの X12 EDI 機能の一部として HIPAA サポートを提供します。 したがって、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のドキュメントで X12 処理のサポートについて記載されていれば、特に明記されていない限り、それは HIPAA 処理にも当てはまります。  
  
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