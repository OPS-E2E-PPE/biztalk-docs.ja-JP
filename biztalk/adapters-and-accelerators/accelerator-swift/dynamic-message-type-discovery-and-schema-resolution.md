---
title: 動的メッセージ型の探索とスキーマの解決 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- dynamic schema resolution
- disassembler, code sample
- schemas, dynamic resolution
- assembler, message types
- disassembler, message types
- code samples, disassembler
ms.assetid: 5f71d3df-a37e-4ef2-9055-b614656203e9
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a0bb060a903eae06b4014100cac4e8c7bdc4a1ef
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377937"
---
# <a name="dynamic-message-type-discovery-and-schema-resolution"></a>動的メッセージ型の探索とスキーマの解決
Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] SWIFT 逆アセンブラーおよびアセンブラーの両方で動的メッセージ型の検出とスキーマ解決できます。  
  
## <a name="swift-disassembler"></a>SWIFT 逆アセンブラー  
 SWIFT 逆アセンブラー (逆アセンブラー) は、動的に受信したメッセージのメッセージの種類を検出し、メッセージを解析するために必要な適切なスキーマを読み込む権限を持ちます。 この機能の最大のメリットは、SWIFT 逆アセンブラーを使用して任意の SWIFT メッセージの種類の SWIFT のメッセージを処理する 1 つのパイプラインを構成することができます。 ネイティブの BizTalk フラット ファイル逆アセンブラーとは異なり、SWIFT 逆アセンブラー A4SWIFT が発生する可能性のあるメッセージの種類ごとに個別の受信パイプラインを作成することはありません。  
  
 ほとんどの場合、システムが受信したすべてのメッセージはで始まるヘッダーの構造的に同種のデータと仮定した場合は、動的メッセージ型の探索を使用することができます。 ヘッダー内では、データは、メッセージのメッセージの種類を表示するフィールドです。 SWIFT のメッセージのヘッダーのデータで構成されます SWIFT メッセージ ブロック 1、2、3、ブロック (アプリケーションのヘッダーと呼ばれます) 2 に含まれるメッセージ型情報。  
  
 SWIFT 逆アセンブラー コンポーネントは、プロパティの設定のいずれかを必要とせずすべて"single"(非バッチ) SWIFT のメッセージ ボックスを処理できます。 既定では、SWIFT インターチェンジ スキーマと SWIFT ヘッダー スキーマは設定されていません。ただし、SWIFT 逆アセンブラー コンポーネントは動的に SWIFT メッセージの種類を検出して、メッセージを処理する Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.dll に存在する SWIFT ヘッダー スキーマを使用します。 また、BRE および XML の検証は、処理されるすべてのメッセージが完全に検証するように既定で有効は。 RuntimeSchemas.dll で SWIFT ヘッダーをポイントする SWIFT ヘッダー スキーマ プロパティの設定が上記と同じ動作にも発生します。  
  
 SWIFT 逆アセンブラーの SWIFT ヘッダー スキーマ構成プロパティが"None"(既定値) に設定されている場合、逆アセンブラーは動的に解決し、次の手順を実行することによって、適切なスキーマを読み込みます。  
  
1. 受信メッセージの先頭 (ヘッダー) を解析する (SWIFT ヘッダー スキーマ構成のプロパティで指定)、ユーザーが指定したヘッダー スキーマを使用します。  
  
2. A4SWIFT_MessageType 昇格させたプロパティ フィールドに、結果として得られる"header XML"を検査します。 このフィールドが存在する場合は、「メッセージの種類」としてフィールドの値を使用して、手順 4. に進みます。 フィールドが存在しない場合は、手順 3. に進みます。  
  
3. A4SWIFT_MessageType2 昇格させたプロパティ フィールドの XML ヘッダーの検査 (逆アセンブラー A4SWIFT_MessageType フィールドが見つからないかどうかは必要です)。 「メッセージの種類」として A4SWIFT_MessageType2 フィールドの値を使用します。  
  
4. 手順 2 または 3 で識別される「メッセージ型」が「574」の場合は、メッセージ型「574」の (つまり、逆アセンブラーのプロパティ) デュアル型メッセージの一覧の構成プロパティで指定されたメッセージの種類の一覧で、SWIFT 逆アセンブラーを確認します。 はいの場合は、手順 5. に進みます。 ない場合は、手順 6. に進みます。  
  
5. ヘッダー XML A4SWIFT_SecondaryMessageType 昇格させたプロパティ フィールドを検査します。 このフィールドが存在する場合、逆アセンブラーはフィールド値 (たとえば、"IRSLST")「メッセージ サブ型」として使用し、「メッセージの種類」、たとえば、"574_IRSLST"に追加します。  
  
   > [!IMPORTANT]
   >  手順 5. の説明は、SWIFT 逆アセンブラー実際の実行内容のメッセージのサブ型を評価する簡略化したものです。 SWIFT 逆アセンブラーで実際には、メッセージの種類、サブタイプがある場合とそうである場合を判断する、次のアルゴリズムを使用してそのサブタイプのとおりです。  
  
   ```  
   Given MT type number nxx ...  
   if nxx is in the Dual-Type list {  
     if field 119 exists AND field 119 is NOT null/empty {  
       if n == 1 {  
         if field 119 == "STP" {  
           Use MTnxxPLUS schema  
         } else if field 119 == "REMIT" {  
           Use MTnxx schema  
         } else {  
           Use MTnxx_<field 119> schema  
         }   
       } else {  
         // n != 1  
         Use MTnxx_<field 119> schema  
       }  
     } else {  
       // field 119 does not exist or 119 does exist but is null/empty  
       Use MTnxx schema  
     }  
   } else {  
     // nxx is not a dual-type message  
     Use MTnxx schema  
   }  
   ```  
  
6. 逆アセンブラーは今すぐ、メッセージの種類を知っているし、インターチェンジのスキーマ名をプレフィックスとサフィックス ("MT"プレフィックス"MT574_IRSLST"にする) などの名前を付けるいくつかの固定スキーマを連結して形成できます。  
  
7. (名前) をインターチェンジのスキーマを読み込み、メッセージ全体を解析**最初から開始**、読み込まれたスキーマを使用して (つまり、逆アセンブラーが 2 回の見出しのデータを解析: ヘッダー スキーマを使用すると、使用してもう一度インターチェンジのスキーマの先頭)。 インターチェンジのスキーマは、ヘッダーを含むメッセージ全体を解析できる必要があります。  
  
   > [!NOTE]
   >  逆アセンブラーは、A4SWIFT SWIFT メッセージのすべてのスキーマを使用して SWIFT インターチェンジ全体を解析することができます (SWIFT ブロック 1、2、3、4、および 5)。 逆アセンブラーは、ブロック 1、2、3 のみを解析するのに既定の SWIFT ヘッダー スキーマを使用します。 詳細については、以下を参照してください。  
  
   上記で説明したスキーマの解決のアルゴリズムを意味する動的メッセージ型の検出が機能するためには、SWIFT ヘッダー スキーマ含める必要があります (、A4SWIFT で定義されている次の昇格させたプロパティを使用して、逆アセンブラーが昇格されるフィールドプロパティ スキーマ、Microsoft.Solutions.A4SWIFT.Property.PropertySchema):  
  
- **A4SWIFT_MessageType**  
  
- **A4SWIFT_MessageType2** (省略可能な場合**A4SWIFT_MessageTypes**使用)  
  
- **A4SWIFT_SecondaryMessageType** (省略可能)  
  
  これらおよびその他の昇格させたプロパティの詳細については、次を参照してください。 [a4swift _ * 昇格プロパティ](../../adapters-and-accelerators/accelerator-swift/a4swift-promoted-properties.md)します。  
  
> [!NOTE]
>  SWIFT ヘッダーのスキーマに設定する場合**None**、完全なインターチェンジのスキーマを指定する必要があります、 **SWIFT インターチェンジ スキーマ**プロパティ。 ここでは、逆アセンブラーは、A4SWIFT を受信するすべてのメッセージを解析するのに指定されたインターチェンジ スキーマを使用します。 つまり、動的スキーマの解決を無効にして、型を持つ指定されたインターチェンジ スキーマに一致するメッセージのみを受信するパイプラインを構成します。  
  
 A4SWIFT では、標準ヘッダーを SWIFT データを解析できますで動的スキーマの解決を容易にするために必要な昇格させたプロパティを備えた既定 SWIFT ヘッダー スキーマ (Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.HeaderSchema) をインストールします。  
  
 SWIFT ヘッダーの既定のスキーマでは、次の昇格させたフィールドがあります。  
  
- **SWIFTHeader/ApplicationHeaderBlock_Input/MessageType**します。 逆アセンブラーを推進これを使用して、 **A4SWIFT_MessageType**プロパティ。  
  
- **SWIFTHeader/ApplicationHeaderBlock_Output/MessageType**します。 逆アセンブラーを推進これを使用して、 **A4SWIFT_MessageType2**プロパティ。  
  
- **SWIFTHeader/UserHeaderBlock/ValidationFlag_119**します。 逆アセンブラーを推進これを使用して、 **A4SWIFT_MessageType**プロパティ。  
  
  逆アセンブラは、 **Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.HeaderSchema** SWIFT ヘッダーのスキーマと SWIFT のインターチェンジのスキーマの両方の構成プロパティを設定する場合は、ヘッダー スキーマとして既定で"None"です。  
  
## <a name="swift-assembler"></a>SWIFT アセンブラー  
 SWIFT アセンブラーでは、SWIFT 逆アセンブラーなどを動的に、送信メッセージのメッセージの種類を検出して、メッセージをシリアル化するために必要な適切なスキーマを読み込む機能があります。 この機能では、SWIFT アセンブラーを使用して任意の SWIFT メッセージの種類の SWIFT のメッセージを処理する 1 つのパイプラインを構成することができます。 ネイティブの BizTalk フラット ファイル アセンブラーとは異なり、SWIFT アセンブラーは必要ありません A4SWIFT が発生する可能性のあるメッセージの種類ごとに別の送信パイプラインを作成します。  
  
 SWIFT アセンブラーの動的なスキーマ解決は、アセンブラーは、ジョブの SWIFT のフラット ファイル形式に XML をシリアル化するために SWIFT 逆アセンブラーでよりずっとシンプルです。 XML を[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]にシリアル化には、メッセージ型とスキーマについてには、シリアル化のための適切なスキーマを直接使用できる、SWIFT アセンブラーが含まれています、SWIFT アセンブラーを提供します。 そのため、SWIFT アセンブラーにはヘッダーやインターチェンジ スキーマのすべての構成機能はありません: 指定されたスキーマが常に使用で XML シリアル化されます。  
  
## <a name="see-also"></a>参照  
 [SWIFT 逆アセンブラーおよびアセンブラーの操作](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md)