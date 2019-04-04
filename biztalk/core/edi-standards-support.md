---
title: EDI 標準のサポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c2ef14c5-5f12-40e2-93d7-59b5c5a0d641
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ebb4d85b4972991054914baea2014b6d268a24eb
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007131"
---
# <a name="edi-standards-support"></a>EDI 標準のサポート
BizTalk Server は、4 つのエンコード標準のデザインと実行時サポートを提供します。 次の表に、詳細情報へのリンクを含むエンコード標準の一覧を示します。  
  
|エンコード標準|業界セグメント|References|  
|-----------------------|----------------------|----------------|  
|UN/EDIFACT|一般産業|[標準の web サイト](http://go.microsoft.com/fwlink/?LinkId=77532)(ペイロードへの参照)<br /><br /> [エンコード規則](http://go.microsoft.com/fwlink/?LinkId=77534)ISO 9735-4.1 ごと|  
|X12|一般産業|[標準の web サイト](http://go.microsoft.com/fwlink/?LinkID=28673)<br /><br /> [仕様開発](http://go.microsoft.com/fwlink/?LinkId=77535)|  
|EANCOM|小売|[標準の web サイト](http://go.microsoft.com/fwlink/?LinkId=92861)|  
|HIPAA X12N|医療|[HIPAA 実装ガイド](http://go.microsoft.com/fwlink/?LinkId=77541)<br /><br /> [HIPAA 仕様](http://go.microsoft.com/fwlink/?LinkId=77542)|  
  
> [!NOTE]
>  EANCOM スキーマは EDIFACT のサブセットです。 EANCOM は、EDIFACT と同じエンコード規則に準拠します。  
  
> [!NOTE]
>  KEDIFACT は、独立した標準ですが、EDIFACT に基づいて設計され、密接に関連しています。  
  
## <a name="x12-and-edifact"></a>X12 および EDIFACT  
 全世界で交換されている EDI メッセージの 90% に、ANSI X12 と UN/EDIFACT の 2 つの標準が使用されています。  
  
- UN/EDIFACT EDI 国際メッセージ標準 (EDI for Administration, Commerce, and Trade) は、United Nations Economic Commission for Europe (UN/ECE) によって開発され、維持されています。 EDIFACT と呼ばれる場合もあります。  
  
- X12 EDI U.S. メッセージ標準は、American National Standards Institute (ANSI) によって設立された Accredited Standards Committee (ASC) X12 委員会によって開発され、維持されています。  
  
  EDIFACT は主に米国ベースします。X12 標準。 2 つの EDI 標準は、構造面において非常に似ています。 相違点は次のとおりです。  
  
- 2 つの標準では、構造体要素の名前の付け方が異なります。 たとえば、インターチェンジ制御ヘッダーは、X12 では ISA データ要素ですが、EDIFACT では UNB データ要素です。  
  
- 多くのトランザクション セットが 2 つの標準の間でマッピングを行いますが、2 つの標準ではトランザクション セットの名前の付け方が異なります。 たとえば、注文書は、X12 では 850 トランザクション セットですが、EDIFACT では ORDERS トランザクション セットです。  
  
- EDIFACT には、区切り記号や小数点表示などの構造体要素を設定するオプションのヘッダー セグメント UNA があり、パイプラインで定義されている既定の値がオーバーライドされます。  
  
- X12 が 2 つの受信確認 (TA1 と呼ばれる技術確認とという 997 機能確認)、EDIFACT CONTRL と呼ばれる 1 つの包括的な受信確認があるときにします。  
  
- X12 では ASCII エンコードが推奨されますが、EDIFACT では UTF8 エンコードが推奨されます。  
  
  BizTalk Server では、KEDIFACT (Korea EDIFACT) 標準をサポートします。 KEDIFACT は、UN/EDIFACT の Message Implementation Guide に準拠し、EDIFACT に基づいて設計され、密接に関連しています。 しかし、KEDIFACT と X12/EDIFACT には違いがあります。 KEDIFACT は、KEDIFACT 固有の EDI スキーマをいくつか使用し、KECA コード ページを使用します。  
  
## <a name="hipaa"></a>HIPAA  
 BizTalk Server が X12 処理をサポートし、HIPAA 処理は、X12 処理の派生クラスであるために、BizTalk Server では、HIPAA 処理をサポートしています。 このドキュメントでのサポート、X12 への参照では、HIPAA 処理にも適用されます。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、HIPAA 固有の追加サポートを提供します。  
  
- バージョン 4010A1 HIPAA ドキュメント スキーマのセット。 BizTalk Server での EDI および HIPAA ドキュメント スキーマの詳細については、[EDI ドキュメント スキーマ](../core/edi-document-schemas.md)を参照してください。  
  
- バージョン 5010 HIPAA ドキュメント スキーマのセット。 詳細については、[HIPAA ドキュメント スキーマ バージョン 5010](../core/hipaa-document-schema-version-5010.md)を参照してください。  
  
- HIPAA サブドキュメントの分割。 詳細については、[HIPAA サブドキュメントの分割](../core/splitting-hipaa-subdocuments.md)を参照してください。  
  
- WEDI SNIP テストの最初の 2 つのレベルのサポート: X12 構文整合性およびの要件、 [HIPAA 実装ガイド](http://go.microsoft.com/fwlink/?LinkId=77541)します。  
  
  BizTalk Server は、ネイティブの BizTalk Server の EDI 機能の一部として HIPAA サポートを提供します。 詳細については、[BizTalk Server における EDI のサポート](../core/edi-support-in-biztalk-server2.md)を参照してください。  
  
## <a name="eancom"></a>EANCOM  
 BizTalk Server は、EDIFACT 処理をサポートし、EANCOM 処理は、EDIFACT 処理の派生クラスであるために、BizTalk Server では、EANCOM 処理をサポートしています。 このドキュメントで EDIFACT 処理のサポートについて記載されていれば、それは EANCOM 処理にも当てはまります。  
  
 BizTalk Server は、EANCOM 固有の追加サポートを提供します。  
  
-   バージョン EAN94、EAN97、および EAN02 EANCOM ドキュメント スキーマのセット。 BizTalk Server での EDI および EANCOM ドキュメント スキーマの詳細については、[EDI ドキュメント スキーマ](../core/edi-document-schemas.md)を参照してください。  
  
## <a name="see-also"></a>参照  
 [EDI メッセージの構造](../core/edi-message-structure.md)   
 [EDI ドキュメント スキーマ](../core/edi-document-schemas.md)