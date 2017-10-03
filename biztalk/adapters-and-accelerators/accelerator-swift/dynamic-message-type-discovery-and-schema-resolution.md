---
title: "動的なメッセージの種類の探索とスキーマの解決 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- dynamic schema resolution
- disassembler, code sample
- schemas, dynamic resolution
- assembler, message types
- disassembler, message types
- code samples, disassembler
ms.assetid: 5f71d3df-a37e-4ef2-9055-b614656203e9
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 77e9a8949787fcd3c7e942c406c9f31470894a8d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="dynamic-message-type-discovery-and-schema-resolution"></a>動的なメッセージの種類の探索とスキーマの解決
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] SWIFT 逆アセンブラおよびアセンブラの両方での動的なメッセージの型の検出とスキーマの解決を有効にします。  
  
## <a name="swift-disassembler"></a>SWIFT 逆アセンブラー  
 SWIFT 逆アセンブラー (逆アセンブラー) を動的に受信したメッセージのメッセージの種類を検出して、メッセージを解析して必要な適切なスキーマを読み込む権限を持ちます。 この機能の最大のメリットは、すべて SWIFT メッセージの種類の SWIFT メッセージの処理に SWIFT の逆アセンブラーを使用して 1 つのパイプラインを構成することができます。 ネイティブの BizTalk フラット ファイル逆アセンブラーとは異なり、SWIFT の逆アセンブラーは必要ありません A4SWIFT が発生する可能性のあるメッセージの種類ごとに個別の受信パイプラインをビルドします。  
  
 ほとんどの場合、システムを受信するすべてのメッセージで始まります構造的に同種の見出しのデータと仮定した場合、動的なメッセージの種類の探索を使用することができます。 ヘッダー内では、データは、送信メッセージのメッセージの種類が表示されるフィールドです。 SWIFT のメッセージのヘッダーのデータで構成されます SWIFT メッセージ ブロック 1、2、3、ブロック (アプリケーション ヘッダーと呼ばれます) 2 に含まれるメッセージの種類の情報。  
  
 SWIFT 逆アセンブラー コンポーネントは、プロパティの設定のいずれかを必要とせずすべて「単一」(非バッチ) SWIFT からメッセージ ボックスを処理できます。 既定では、SWIFT インターチェンジのスキーマと SWIFT ヘッダー スキーマ設定されていません。ただし、SWIFT 逆アセンブラー コンポーネントはスキーマを使用、SWIFT ヘッダー Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.dll 内に存在を動的に SWIFT メッセージの種類を検出し、メッセージを処理します。 また、BRE および XML の検証は既定で有効に処理されるすべてのメッセージが完全に検証するためです。 RuntimeSchemas.dll に SWIFT ヘッダーをポイントする SWIFT ヘッダー スキーマ プロパティを設定が上記と同じ動作にも発生します。  
  
 SWIFT の逆アセンブラーの SWIFT ヘッダー スキーマ構成プロパティが「なし」(既定) に設定されている場合、逆アセンブラーは動的に解決し、次の手順を実行することによって、適切なスキーマを読み込みます。  
  
1.  (SWIFT ヘッダー スキーマ構成のプロパティで指定)、ユーザーが指定したヘッダー スキーマを使用して、受信メッセージの先頭 (ヘッダー) を解析します。  
  
2.  A4SWIFT_MessageType 昇格させたプロパティ フィールドの結果として得られる「ヘッダー XML」を検査します。 このフィールドが存在する場合は"メッセージの種類として"フィールドの値を使用し、手順 4. に進みます。 フィールドが存在しない場合は、手順 3. に進みます。  
  
3.  XML A4SWIFT_MessageType2 昇格させたプロパティ フィールドのヘッダーを検査 (逆アセンブラーが A4SWIFT_MessageType フィールドを検索していないかどうかを想定)。 "メッセージの種類として"A4SWIFT_MessageType2 フィールドの値を使用します。  
  
4.  手順 2 または 3 で識別される「メッセージ型」が「574」の場合は、SWIFT の逆アセンブラーは「574」が (つまり、逆アセンブラーのプロパティ) デュアル型メッセージの一覧の構成プロパティで指定されたメッセージの種類の一覧の場合は、メッセージの種類をチェックします。 場合は、手順 5. に進みます。 ない場合は、手順 6. に進みます。  
  
5.  ヘッダー XML A4SWIFT_SecondaryMessageType 昇格させたプロパティ フィールドを検査します。 このフィールドが存在する場合、逆アセンブラーは"メッセージのサブ種類として"フィールドの値 (たとえば、"IRSLST") を使用して、「メッセージの種類」、"574_IRSLST"などに追加します。  
  
    > [!IMPORTANT]
    >  手順 5. の説明は、SWIFT の逆アセンブラー実際の実行内容のメッセージのサブ型に評価する簡略化バージョンです。 実際には、SWIFT 逆アセンブラは、次のアルゴリズムおよびを判別メッセージの種類、サブタイプがある場合は、そのサブ型は、次のようにします。  
  
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
  
6.  逆アセンブラーは今すぐ、メッセージの種類を認識し、インターチェンジのスキーマ名をプレフィックスとサフィックス ("MT"プレフィックス"MT574_IRSLST"を作成する) などの名前付けいくつかの固定スキーマを連結して形成できます。  
  
7.  (名) をインターチェンジのスキーマを読み込み、メッセージ全体を解析**先頭から開始**、読み込まれたスキーマを使用して (つまり、逆アセンブラーが 2 回の見出しのデータを解析しますヘッダー スキーマを使用すると、を使ってもう一度。インターチェンジのスキーマの先頭)。 インターチェンジのスキーマは、ヘッダーを含むメッセージ全体を解析できる必要があります。  
  
    > [!NOTE]
    >  逆アセンブラーは、A4SWIFT SWIFT メッセージのすべてのスキーマを使用して SWIFT インターチェンジ全体を解析することができます (SWIFT ブロック 1、2、3、4、および 5)。 逆アセンブラーでは、既定 SWIFT ヘッダーのスキーマを使用して、ブロック 1、2、3 のみを解析します。 詳細については、以下を参照してください。  
  
 上記で説明した、スキーマ解決アルゴリズムを意味する動的なメッセージ型探索が機能するためには、SWIFT ヘッダー スキーマ含める必要があります (、A4SWIFT で定義されている次の昇格させたプロパティを使用して、逆アセンブラーが昇格されるフィールドプロパティ スキーマ、Microsoft.Solutions.A4SWIFT.Property.PropertySchema):  
  
-   **A4SWIFT_MessageType**  
  
-   **A4SWIFT_MessageType2** (省略可能な場合**A4SWIFT_MessageTypes**を使用)  
  
-   **A4SWIFT_SecondaryMessageType** (省略可能)  
  
 これらおよびその他の昇格させたプロパティの詳細については、次を参照してください。 [A4SWIFT_ * 昇格されたプロパティ](../../adapters-and-accelerators/accelerator-swift/a4swift-promoted-properties.md)です。  
  
> [!NOTE]
>  SWIFT ヘッダー スキーマを設定すると**なし**、完全なインターチェンジのスキーマを指定する必要があります、 **SWIFT インターチェンジ スキーマ**プロパティ。 ここでは、逆アセンブラーは指定されたインターチェンジのスキーマを使用して、A4SWIFT を受信するすべてのメッセージを解析します。 つまり、動的スキーマの解決を無効にし、型が指定されたインターチェンジ スキーマに一致するメッセージのみを受信するパイプラインを構成します。  
  
 A4SWIFT は、SWIFT の標準ヘッダー データを解析することができますを動的スキーマの解決を容易にするために必要な昇格させたプロパティを持つ既定 SWIFT ヘッダー スキーマ (Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.HeaderSchema) をインストールします。  
  
 既定 SWIFT ヘッダーのスキーマには、次の昇格させたフィールドがあります。  
  
-   **SWIFTHeader/ApplicationHeaderBlock_Input/MessageType**です。 逆アセンブラーを推進これを使用して、 **A4SWIFT_MessageType**プロパティです。  
  
-   **SWIFTHeader/ApplicationHeaderBlock_Output/MessageType**です。 逆アセンブラーを推進これを使用して、 **A4SWIFT_MessageType2**プロパティです。  
  
-   **SWIFTHeader/UserHeaderBlock/ValidationFlag_119**です。 逆アセンブラーを推進これを使用して、 **A4SWIFT_MessageType**プロパティです。  
  
 逆アセンブラーを使用して**Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.HeaderSchema**に SWIFT ヘッダー スキーマと SWIFT インターチェンジのスキーマの両方の構成プロパティを設定した場合、ヘッダー スキーマとして既定では"None"です。  
  
## <a name="swift-assembler"></a>SWIFT アセンブラー  
 SWIFT 逆アセンブラーのようには、SWIFT、アセンブラーを動的に送信メッセージのメッセージの種類を検出して、メッセージをシリアル化するために必要な適切なスキーマを読み込む権限を持ちます。 この機能では、SWIFT アセンブラーを使用して、SWIFT メッセージの種類の SWIFT のメッセージを処理する 1 つのパイプラインを構成することができます。 ネイティブの BizTalk フラット ファイル アセンブラーとは異なり、SWIFT アセンブラーは必要ありません A4SWIFT が発生する可能性のあるメッセージの種類ごとに個別の送信パイプラインを構築します。  
  
 SWIFT アセンブラーで動的スキーマ解決は、アセンブラーは、ジョブに SWIFT のフラット ファイル形式の XML をシリアル化のために SWIFT の逆アセンブラーでより単純です。 XML を[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]SWIFT アセンブラーへのシリアル化には、メッセージ型とスキーマについてには、シリアル化のための適切なスキーマを読み込むには、直接使用できる、SWIFT アセンブラーが含まれていますを提供します。 そのため、SWIFT アセンブラーにはヘッダーとインターチェンジのスキーマのどの構成機能がありません: 指定されたスキーマを常に使用がシリアル化する XML のです。  
  
## <a name="see-also"></a>参照  
 [SWIFT 逆アセンブラおよびアセンブラの操作](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md)