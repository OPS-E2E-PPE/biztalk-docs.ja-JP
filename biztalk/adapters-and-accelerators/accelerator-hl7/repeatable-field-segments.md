---
title: 反復可能なフィールド セグメント |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- segments, repeatable fields
- QPD
- Table Row Data (RDT)
- Query Parameter Definition (QPD)
- Segments table
- RDT
ms.assetid: 4c31cb56-21e5-4918-aaf6-67e8ceddd74f
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9651b8d3414f792b81633cafbe41dd66559df04c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981979"
---
# <a name="repeatable-field-segments"></a>反復可能なフィールド セグメント
HL7 の Access データベース内のセグメント テーブルの列が格納 (ADD、RDT、および QPD) セグメントの最後のフィールドを Microsoft BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 反復可能として定義されています (**Last_field_repeatable**  =  **True**)。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 追加はサポートされません。 ただし、RDT と QPD の両方がクエリのテーブルに存在して、テーブルの値で応答します。 次のサンプルではどのように[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]これらの列を処理します。  
  
 クライアントは、次のクエリを送信して、クライアントが設定して、即座に応答を要求することを示します**RCP-1-応答の優先順位**に"**は**"。  
  
```  
MSH|^&~\|PCR|Gen Hosp|PIMS||199811201400-0800||QBP^Q42^QBP_Q13|ACK9901|P|2.4||||||||  
QPD|Q42^Tabular Dispense History^HL7nnn|Q0010|555444222111^^^MPI^MR| |19980531|19990531|  
RCP|I|999^RD|  
RDF|3|PatientList^ST^20~PatientName^XPN^48~MedicationDispensed^ST^40~RXD.3^TS^26  
```  
  
 1 分後、次のメッセージで応答します。  
  
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
  
 例から QPD と RDT が定義されているカスタム サイトを参照してください。 HL7 仕様では、次のように QPD と RDT のセグメントを定義します。  
  
## <a name="qpd---query-parameter-definition"></a>QPD - クエリ パラメーターの定義  
 次の表では、HL7 仕様が QPD を定義する方法を示します。  
  
|SEQ|LEN|DT|オプトイン|RP/#|TBL #|項目番号|要素名|  
|---------|---------|--------|---------|------------|-----------|------------|------------------|  
|1|250|CE|R||0471|01375|メッセージ クエリ名|  
|2|32|ST|c|||00696|クエリのタグ|  
|3-n|256|異なります||||01435|ユーザーのパラメーターを連続するフィールド|  
  
## <a name="rdt---table-row-data"></a>RDT - テーブルの行データ  
 次の表では、HL7 仕様が RDT を定義する方法を示します。  
  
|SEQ|LEN|DT|オプトイン|RP/#|TBL #|項目番号|要素名|  
|---------|---------|--------|---------|------------|-----------|------------|------------------|  
|1 ~ n|変数|変数|R|||00703|列の値|  
  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] QPD と RDT を繰り返すことができるサイト定義の値として解釈されます。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]データ型およびその他の詳細が解決しない[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]QPD.3 および RDT.1、スキーマ内の文字列データ型として扱われます。 サイトの条件によってこれらのスキーマを変更する必要があります。  
  
## <a name="see-also"></a>参照  
 [HL7 2.X スキーマの使用](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)