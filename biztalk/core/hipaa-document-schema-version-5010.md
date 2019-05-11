---
title: HIPAA ドキュメント スキーマ バージョン 5010 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 62e50964-66e1-4ed9-a1a1-68556b13b024
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0a3d1aafd346a75c4968f436b2d04f12ae987d2b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65344376"
---
# <a name="hipaa-document-schema-version-5010"></a>HIPAA ドキュメント スキーマ バージョン 5010
米国Department of Health and Human Services (HHS) は、バージョン 5010 で現在の HIPAA バージョン 4010A1 を置き換える 2009 年 1 月 16 日の最後のルールを発表しました。 HIPAA 標準バージョン 5010 では、構造、序文、技術、およびデータ コンテンツが含まれています。 これらの機能強化が削減され、いくつかの前に満たされていないビジネス ニーズにも対応しながらデータのあいまいさが排除されます。 BizTalk Server では、HIPAA バージョン 5010 のサポートを提供します。  

> [!NOTE]
>  BizTalk Server は、HIPAA バージョン 4010a1 もサポートするために続行します。  

## <a name="hipaa-5010-version-support"></a>HIPAA 5010 バージョンのサポート  
 一部として、次の変更が導入されて[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]の HIPAA 5010 をサポートします。  

- **新しい交換スキーマ**:HIPAA バージョン 5010 では、以前のバージョン 4010A1 経由で、次の新しい交換スキーマについて説明します。 EDI スキーマは圧縮され、実行可能ファイルで提供される[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI\MicrosoftEdiXSDTemplates.exe します。 MicrosoftEdiXSDTemplates.exe 預金に HIPAA 5010 スキーマで実行すると、 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\edi\hipaa\5010 フォルダー。  


  |  GS08/ST03   | セット Id (ST01) |                       説明                       |
  |--------------|----------------|---------------------------------------------------------|
  |  005010X279  |      270       |   資格、範囲、給付金に関する問い合わせ - 要求    |
  |  005010X279  |      271       | 資格、範囲、給付の情報 - 応答 |
  |  005010 X 212  |      276       |           健康保険請求ステータス - 要求            |
  |  005010 X 212  |      277       |           健康保険請求ステータス - 応答           |
  |  005010 X 217  |      278       |   Health Care Services Review – 要求と応答    |
  |  005010X218  |      820       |                    給与控除                    |
  |  005010X220  |      834       |    健康保険給付の登録と管理    |
  |  005010 X 221  |      835       |              医療保険請求 Payment(s)               |
  |  005010X222  |      837       |           健康保険請求 - プロフェッショナル           |
  | 005010X223A1 |      837       |          健康保険請求 - 機関           |
  | 005010X224A1 |      837       |              健康保険請求 - 歯科              |


- **ST03 フィールドのサポート**:バージョン 5010 では 835 (Health Care 要求 Payment(s)) 以外のすべてのトランザクション セットの ST03 の存在。 ST03 は、トランザクション セットのバージョンを識別するために使用されます。 ST03 は、1 つのグループ内のトランザクション セットの異なるバージョンをできます。 ST03 は、トランザクション セットのバージョンを識別するときに、GS08 よりも優先します。 記述し、コンテキスト プロパティとして EDI のプロパティ スキーマの名前空間の下の ST03 の昇格し、ST03 に基づいてメッセージをルーティングできます。  

- **グループ内の類似トランザクション セットのサポート**:X12 標準のトランザクション セットと ST01 GS01 マッピングと呼ばれる、グループ間のマッピングを提供します。 このマッピングは、1 つのグループ (GS-GE) として結合可能な同種のトランザクション セットの検証に使用されます。 Hipaa に関しては、Professional、Institutional、および Dental の 837 クレームが 1 つのグループ内で発生することが今すぐこのことを意味します。  

- **Icd-10 のサポート**:医療保健データの転送には、電子トランザクション コード セットが使用されます。 バージョン 5010 ではバージョン 4010A1 でサポートされていない国際分類の病名 (icd-10) コード セットを使用します。 Icd-10 は、さまざまな診断および請求、要求の関連トランザクション、および治療報告の手順を識別するために使用されます。 Icd-10 を使用する利点には、患者サービス、診断、治療および品質のデータのより包括的なレポートをより正確なデータが含まれます。  

- **5010 997 の新しいフィールド**:997 機能確認スキーマには、-、-インボックス BizTalk Server によって次の 3 つの新しい省略可能なフィールド AK103、AK203、および AK41.3 namely が導入されていますが用意されています。 EDI エンジンは、受信した 5010 997 のメッセージが、これらのフィールドが含まれていますが、送信 997 受信確認は生成されませんが、新しいスキーマに基づく処理できます。  

  それらの最小値と最大の長さに対してチェックされなかった X12_R データ型の要素を HIPAA 4010A1 のスキーマに関する既知の問題が発生しました。 BizTalk Server でこの問題が修正されましたし、HIPAA 5010 のスキーマは、最小値と最大の長さの X12_R データ型の要素を検証します。  

## <a name="see-also"></a>参照  
 [BizTalk Server における HIPAA のサポート](../core/hipaa-support-in-biztalk-server.md)   
 [HIPAA サブドキュメントの分割](../core/splitting-hipaa-subdocuments.md)