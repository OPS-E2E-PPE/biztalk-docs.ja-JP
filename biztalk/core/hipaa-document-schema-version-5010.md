---
title: "HIPAA ドキュメント スキーマ バージョン 5010 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 62e50964-66e1-4ed9-a1a1-68556b13b024
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 24d1528d5c35c15e777ce1540d42ea4b7066cea2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="hipaa-document-schema-version-5010"></a>HIPAA ドキュメント スキーマ バージョン 5010
言語設定が部門の保健福祉 (HHS) は、バージョン 5010 の現在の HIPAA バージョン 4010A1 に置換される 2009 年 1 月 16 日の最終規則を発表しました。 HIPAA 標準バージョン 5010 では、構造、序文、技術、およびデータ コンテンツの面で改良が加えられています。 その結果、データのあいまいさが減少し除去されています。また、それまでは満たされていなかったビジネス ニーズのいくつかについても満たされるようになっています。 [!INCLUDE[prague](../includes/prague-md.md)]HIPAA バージョン 5010 のサポートを提供します。  
  
> [!NOTE]
>  [!INCLUDE[prague](../includes/prague-md.md)] は引き続き、HIPAA バージョン 4010A1 もサポートします。  
  
## <a name="hipaa-5010-version-support"></a>HIPAA 5010 バージョンのサポート  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、HIPAA 5010 をサポートするために以下の点が変更されています。  
  
-   **新しい交換スキーマ**: HIPAA バージョン 5010 の以前のバージョン 4010A1 経由で、次の新しい交換スキーマが導入されています。 EDI スキーマは圧縮されており、実行可能ファイル [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI\MicrosoftEdiXSDTemplates.exe として配布されます。 MicrosoftEdiXSDTemplates.exe を実行すると、HIPAA 5010 のスキーマは [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI\HIPAA\5010 フォルダーに出力されます。  
  
    |GS08/ST03|セット ID (ST01)|Description|  
    |----------------|----------------------|-----------------|  
    |005010X279|270|資格、範囲、給付の問い合わせ - 要求|  
    |005010X279|271|資格、範囲、給付の情報 - 応答|  
    |005010X212|276|健康保険請求ステータス - 要求|  
    |005010X212|277|健康保険請求ステータス - 応答|  
    |005010X217|278|Health Care Services Review – Request and Response|  
    |005010X218|820|給料からの控除|  
    |005010X220|834|健康保険給付の登録と管理|  
    |005010X221|835|健康保険請求の支払い|  
    |005010X222|837|健康保険請求 - プロフェッショナル|  
    |005010X223A1|837|健康保険請求 - 機関|  
    |005010X224A1|837|健康保険請求 - 歯科|  
  
-   **ST03 フィールドのサポート**: バージョン 5010 では、835 (Health care Claim 以外のすべてのトランザクションの ST03 が存在する設定で必須します。 ST03 の用途は、トランザクション セットのバージョンを示すことです。 ST03 によって、バージョンが異なるトランザクション セットが同じグループ内に存在することが可能になります。 トランザクション セットのバージョンを特定するときに、ST03 は GS08 よりも優先されます。 ST03 は、EDI プロパティ スキーマ名前空間の下で、コンテキスト プロパティとして書き込みや昇格が可能です。また、ST03 に基づいてメッセージをルーティングすることが可能です。  
  
-   **グループ内の類似トランザクション セットのサポート**: X12 標準は、トランザクション セットおよび ST01 GS01 マッピングと呼ばれるグループの間のマッピングを提供します。 このマッピングは、1 つのグループ (GS-GE) として結合可能な、同種のトランザクション セットの集合を表すのに使用されます。 HIPAA に関しては、これによって Professional、Institutional、および Dental の 837 クレームを 1 つのグループの中に収容できるようになりました。  
  
-   **Icd-10 のサポート**: 電子トランザクション コード セットが医療保健データの転送を行うために使用します。 バージョン 5010 では、ICD-10 (International Classification of Diseases) コード セットを使用できるようになっています (バージョン 4010A1 ではサポートされていませんでした)。 ICD-10 は、医療費請求、関連トランザクション、および治療報告においてさまざまな診断および処置を表すのに使用されます。 ICD-10 を使用すると、患者サービス、診断、治療のデータの正確さが向上します。また、品質データのより包括的な報告が可能になります。  
  
-   **5010 997 の新しいフィールド**:、997 機能確認スキーマ標準の-、-、 [!INCLUDE[prague](../includes/prague-md.md)] 3 つの任意フィールド AK103、AK203、および AK41.3 つまりが導入されています。 EDI エンジンは、受信した 5010 997 メッセージにこれらのフィールドが含まれていても処理できますが、送信される 997 確認を新しいスキーマに基づいて生成する機能はありません。  
  
 HIPAA 4010A1 のスキーマには、X12_R データ型の要素を最小長/最大長と比較する検査が行われないという既知の問題がありました。 [!INCLUDE[prague](../includes/prague-md.md)] では、この問題は修正されており、HIPAA 5010 スキーマでは X12_R データ型の要素の最小長/最大長の検査が行われます。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server での HIPAA サポート](../core/hipaa-support-in-biztalk-server.md)   
 [HIPAA サブドキュメントの分割](../core/splitting-hipaa-subdocuments.md)