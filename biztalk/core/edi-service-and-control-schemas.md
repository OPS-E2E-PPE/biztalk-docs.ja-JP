---
title: EDI サービスと管理スキーマ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4866571b-b12d-446c-8d27-a72fe7e479ef
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9b12bdee5fd1e29e1f65fa709612cceb729e2cd7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389599"
---
# <a name="edi-service-and-control-schemas"></a>EDI サービスと管理スキーマ
メッセージ エンベロープおよび受信確認を処理するには、管理スキーマが必要です (メッセージ エンベロープの処理にはヘッダー管理スキーマが必要です)。 これらのスキーマは、セットアップ プログラムにより Microsoft.BizTalk.Edi.BaseArtifacts.dll に展開されます。 BaseArtifacts.dll に展開済みなので、これらのスキーマを BizTalk プロジェクトに追加する必要はありません。 これらのスキーマを使用するには、スキーマを組み込むプロジェクトに BaseArtifacts.dll アセンブリへの参照を追加する必要があります。  

## <a name="envelope-service-schemas"></a>エンベロープ サービス スキーマ  
 EDI インターチェンジのエンベロープ内にあるインターチェンジ、グループ、およびトランザクション セット ヘッダーおよびトレーラーの検証には、サービス スキーマ X12ServiceSchema および EdifactServiceSchema が使用されます。 すべての EDI インターチェンジ (バッチ処理されていないインターチェンジ、分割対象のバッチ処理済みインターチェンジ、保存対象のバッチ処理済みインターチェンジ) が、これらのサービス スキーマにより検証されます。 これらのスキーマの名前空間は http://schemas.microsoft.com/Edi/X12ServiceSchema と http://schemas.microsoft.com/Edi/EdifactServiceSchema します。  

 EDI インターチェンジが保存されたバッチ インターチェンジの場合、サービス スキーマに加えて、バッチ スキーマ X12_BatchSchema および Edifact_BatchSchema が BizTalk ランタイムにより使用されます。 詳細については、次を参照してください。 [EDI のバッチ スキーマ](../core/edi-batch-schemas.md)します。  

 これらのスキーマの ID フィールドの列挙をカスタマイズできます。 その他の変更は許可されていません。 詳細については、次を参照してください。[エンベロープ スキーマで列挙型をカスタマイズする](../core/customizing-enumerations-in-the-envelope-schema.md)します。  

## <a name="acknowledgment-control-schemas"></a>受信確認管理スキーマ  
 EDI 受信パイプラインは、受信確認スキーマを使用して、送信する受信確認を生成します。EDI 送信パイプラインは、受信確認スキーマを使用して、受信した受信確認を処理します。 これらのスキーマには、次の表に示されているように、997 機能確認スキーマ、X12 エンコード用の TA1 インターチェンジ受信確認スキーマ、EDIFACT エンコード用の CONTRL スキーマなどがあります。 これらのスキーマは変更できません。  


|      ACK       |     [スキーマ名]      |             [ターゲットの名前空間]             |                               Root                                |
|----------------|----------------------|------------------------------------------|-------------------------------------------------------------------|
|    X12 TA1     |    X12_TA1Schema     |   http://schemas.microsoft.com/Edi/X12   |                   TA1<br /><br /> X12_TA1_Root                    |
|    X12 997     |    X12_997Schema     |   http://schemas.microsoft.com/Edi/X12   |            ST<br /><br /> SE<br /><br /> X12_997_Root             |
| EDIFACT CONTRL | Edifact_ContrlSchema | http://schemas.microsoft.com/Edi/Edifact | Efact_Contrl_Root<br /><br /> UCD<br /><br /> UCM<br /><br /> UCS |

 X12 エンコードの場合、997 機能確認スキーマにより、メッセージのエンベロープで使用されるインターチェンジ、グループ、およびトランザクション セット/メッセージ ヘッダーおよびトレーラーと、本文の検証結果を報告する AK1、AK2、AK3、AK4、AK5、および AK9 の各セグメントが定義されます。 TA1 技術確認スキーマにより、インターチェンジのヘッダーおよびトレーラーと、ヘッダーの検証結果を報告する TA1 受信確認セグメントが定義されます。 これらのスキーマの名前付け規則では、x12 _\<バージョン番号\>*997. xsd および X12\\*\<バージョン番号\>>_ta1.xsd です。 これらのスキーマのターゲット名前空間は http://schemas.microsoft.com/BizTalk/EDI/X12/2006 します。  

 EDIFACT は、2 段階の受信確認パラダイムをサポートしています。 1 番目の受信確認は、CONTRL スキーマの 3 つのセグメントを使用して構築されるインターチェンジ受信確認です。 この技術確認では、ヘッダーの検証結果が報告されます。 2 番目の受信確認では、CONTRL スキーマの残りのセグメントが使用されます。 このスキーマの名前付け規則には、efact _\<バージョン番号\>>_contrl.xsd です。 このスキーマのターゲット名前空間は http://schemas.microsoft.com/BizTalk/EDI/EDIFACT/2006 します。  

## <a name="see-also"></a>参照  
 [BizTalk Server が EDI メッセージを受信する方法](../core/how-biztalk-server-receives-edi-messages.md)   
 [BizTalk Server が EDI メッセージを送信する方法](../core/how-biztalk-server-sends-edi-messages.md)