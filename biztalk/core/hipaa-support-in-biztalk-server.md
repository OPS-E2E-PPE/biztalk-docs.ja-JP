---
title: BizTalk Server での HIPAA サポート |Microsoft ドキュメント
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
ms.openlocfilehash: c34dd17ed875c5927b7a10d8238ec7828ab96c79
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247410"
---
# <a name="hipaa-support-in-biztalk-server"></a>BizTalk Server での HIPAA サポート
このトピックでは、HIPAA の概要を示し、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] がどのようにして HIPAA をサポートしているかについて簡単に説明します。  
  
## <a name="introduction-to-hipaa"></a>HIPAA の概要  
 1996 年に施行された医療保険の携行性と責任に関する法律 (Health Insurance Portability and Accountability Act: HIPAA) では、適用対象事業者が医療保険の支払請求、送金、受給資格、支払請求の状況に関する要求や応答などのトランザクションを電子的に行うときに強制基準に従うことを義務付けています。 HIPAA の適用対象事業は正常性の計画、クリアリング ハウス、および大部分の医療機関です。  
  
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
  
-   [HIPAA トランザクション セット](../core/hipaa-transaction-sets.md)  
  
 **計画とアーキテクチャ**  
  
-   [HIPAA ドキュメント スキーマ バージョン 5010](../core/hipaa-document-schema-version-5010.md)  
  
-   [HIPAA スキーマのトリガー フィールドの注釈](../core/hipaa-schema-trigger-field-annotations.md)  
  
-   [HIPAA サブドキュメントの分割](../core/splitting-hipaa-subdocuments.md)  
  
 **開発**  
  
-   [EDI スキーマを変更します。](../core/modifying-edi-schemas.md) 

- [エンベロープ スキーマで列挙をカスタマイズします。](../core/customizing-enumerations-in-the-envelope-schema.md)

- [クロス フィールド検証の構成](../core/configuring-cross-field-validation.md)

  
 **トラブルシューティング**  
  
-   [受信処理の EDI の既知の問題](../core/known-issues-with-edi-receive-processing.md)  
  
-   [EDI ソリューションで使用される XML ツールに関する既知の問題](../core/known-issues-with-xml-tools-used-with-edi-solutions.md)  
  
## <a name="more-information-about-hipaa"></a>HIPAA の詳細について  
  
-   American National Standards Institute 詳細については、電子データ交換用の Accredited Standards Committee を参照してください[ASC X12 ホーム](http://www.x12.org/)です。  
  
-   については、X12 の保険小委員会について、および実装ガイドで採用されている HIPAA を参照してください。 [Washington Publishing Company の HIPAA EDI ガイド](http://www.wpc-edi.com/)です。
  
-   電子データ交換のワークグループについてを参照してください[Workgroup for Electronic Data Interchange ホーム ページ](http://www.wedi.org/)です。