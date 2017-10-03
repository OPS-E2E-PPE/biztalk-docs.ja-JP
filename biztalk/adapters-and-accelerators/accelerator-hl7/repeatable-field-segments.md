---
title: "セグメントを反復可能なフィールド |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- segments, repeatable fields
- QPD
- Table Row Data (RDT)
- Query Parameter Definition (QPD)
- Segments table
- RDT
ms.assetid: 4c31cb56-21e5-4918-aaf6-67e8ceddd74f
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a801e39fac0e0bdf0cfb9ee88811703fd1c4373d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="repeatable-field-segments"></a>反復可能なフィールド セグメント
HL7 Access データベース内のセグメント テーブル (ADD、RDT、および QPD) セグメントの最後のフィールドの列を格納する[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 反復可能として定義 (**Last_field_repeatable**  = **True**)。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]追加はサポートされません。 ただし、RDT と QPD の両方がテーブルをクエリに存在し、テーブルの値で応答します。 次のサンプルでどのように[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]これらの列を処理します。  
  
 クライアントは、次のクエリを送信しを設定して、すぐに応答がクライアントが要求していることを示します**RCP-1-応答の優先度**に"**すれば**"。  
  
```  
MSH|^&~\|PCR|Gen Hosp|PIMS||199811201400-0800||QBP^Q42^QBP_Q13|ACK9901|P|2.4||||||||  
QPD|Q42^Tabular Dispense History^HL7nnn|Q0010|555444222111^^^MPI^MR| |19980531|19990531|  
RCP|I|999^RD|  
RDF|3|PatientList^ST^20~PatientName^XPN^48~MedicationDispensed^ST^40~RXD.3^TS^26  
```  
  
 サーバーには、1 分後で、次のメッセージが返されます。  
  
```  
MSH|^&~\|PIMS|Gen Hosp|PCR||199811201401-0800||RTB^K42^RTB_K13|8858|P|2.3||||||||  
MSA|AA|8699|  
QAK|Q010|OK|Q42^Tabular Dispense History^HL7nnn|4  
QPD|Q42^Tabular Dispense History^HL7nnn|Q0010|555444222111^^^MPI^MR||19980531|19990531|  
RDF|7|PatientId^CX^20~PatientName^XPN^48~OrderControlCode^ID^2~ MedicationDispensed^CE^100~DispenseDate^TS^26~QuantityDispensed^NM^20~ OrderingProvider^XCN^120  
RDT|555444222111^^^MPI^MR|Everyman^Adam|RE|525440345^Verapamil Hydrochloride 120 mg TAB^NDC |199805291115-0700|100|77^Hippocrates^Harold^H^III^DR^MD  
RDT|555444222111^^^MPI^MR|Everyman^Adam|RE|00182196901^VERAPAMIL HCL ER TAB 180MG ER^NDC |19980821-0700|100|77^Hippocrates^Harold^H^III^DR^MD  
RDT|555444222111^^^MPI^MR|Everyman^Adam|RE|00172409660^BACLOFEN 10MG TABS^NDC |199809221415-0700|10|88^Semmelweis^Samuel^^^DR^MD  
RDT|555444222111^^^MPI^MR|Everyman^Adam|RE|00054384163^THEOPHYLLINE 80MG/15ML SOLN^NDC|199810121145-0700|10|99^Lister^Lenora^^^DR^MD  
```  
  
 例から QPD と RDT が定義されたカスタム/サイトであるを参照してください。 HL7 仕様では、次のように QPD および RDT セグメントを定義します。  
  
## <a name="qpd---query-parameter-definition"></a>QPD - クエリ パラメーターの定義  
 次の表では、HL7 仕様が QPD を定義する方法を示します。  
  
|SEQ|LEN|DT|オプトイン|RP/#|TBL #|アイテム番号|要素名|  
|---------|---------|--------|---------|------------|-----------|------------|------------------|  
|1|250|CE|R||0471|01375|メッセージ クエリ名|  
|2|32|ST|C|||00696|クエリのタグ|  
|3-n|256|異なります||||01435|ユーザー パラメーターを連続するフィールド|  
  
## <a name="rdt---table-row-data"></a>RDT - テーブルの行のデータ  
 次の表では、HL7 仕様が RDT を定義する方法を示します。  
  
|SEQ|LEN|DT|オプトイン|RP/#|TBL #|アイテム番号|要素名|  
|---------|---------|--------|---------|------------|-----------|------------|------------------|  
|1 ~ n|変数|変数|R|||00703|列の値|  
  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]QPD と RDT を繰り返すことができますをサイト定義の値として解釈します。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]データ型およびその他の詳細が解消されない[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]QPD.3 および RDT.1 スキーマ内の文字列データ型として扱われます。 独自のサイトの条件によってこれらのスキーマを変更する必要があります。  
  
## <a name="see-also"></a>参照  
 [HL7 2.X スキーマの使用](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)