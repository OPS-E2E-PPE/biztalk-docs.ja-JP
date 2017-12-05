---
title: "フラット ファイルの処理は BTAHL72X |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ACKs
- 2.X messages, disassembler
- property promotion, MSH-header schemas
- disassembler, validating messages
- HL7, errors
- 2.X messages, validating headers
- acknowledgements, generating
- assembler, validating messages
- messages, multi-part messages
- property promotion, property schemas
- generating aknowledgements
- messages, 2.X messages
- schemas, MSH-header schemas
- 2.X messages, validating message bodies
- 2.X messages
- schemas, property schemas
- message modes, 2.X messages
- errors, HL7 error format
- flat files
- validating, messages
- schemas, property promotion
- headers, validating
- 2.X messages, message modes
- 2.X messages, header validation
- 2.X messages, parsing flat files
ms.assetid: c92e2f70-0bfa-4bc8-8044-4a6e62cabee3
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bcd1afb4843f68b56228c8e9aaa655d83f70119e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="btahl72x-flat-file-processing"></a>BTAHL72X フラット ファイル処理
次のコンポーネントで[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) プロセス HL7 2.X (HL7 エンコード) メッセージ。  
  
-   パイプラインとコア ライブラリ:[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]です。PipelineCommon.dll と[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]です。PipelineMessageCore.dll  
  
-   アセンブラーおよび逆アセンブラーのライブラリ:[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]です。HL72fAsm.dll と[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]です。HL72fDAsm.dll  
  
-   送信アダプターを受信確認 (ACK) の検証用のライブラリ双方向の MLLP:[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]です。HL7ACKHelper.dll  
  
## <a name="hl7-message-modes"></a>HL7 メッセージ モード  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]2.X メッセージは、次のメッセージ モードをサポートしています。  
  
-   パブリッシャーとサブスクライバー (パブリッシュ サブスクライブ) モード  
  
     パブリッシャーのブロードキャストとして宣言的または要請されていないが、サブスクライバーのパーティに更新します。 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]および[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]デザイン時の後に、サブスクリプションとパーティを管理することができますので、このモードでは、柔軟性を提供します。  
  
-   要求-応答モード  
  
     Interrogative またはクエリ メッセージ交換を特定のエンティティからの特定の要求の結果、応答メッセージ。  
  
## <a name="flat-file-parsing"></a>フラット ファイル解析  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]解析 HL7 2.X マルチパート メッセージのハンドラーを次の 3 つの部分に:  
  
-   MSH ヘッダーの一部  
  
-   ボディ部  
  
-   Z の一部  
  
## <a name="hl7-header-validation"></a>HL7 ヘッダーの検証  
 HL7 逆アセンブラおよびアセンブラは、メッセージを処理できることを確認するために、2.X メッセージのヘッダーの構造とスキーマの検証を実行します。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]一般的なヘッダー スキーマ、MSH_25_GLO_DEF 概略図の検証を行います。  
  
 たとえば、パーサーは、MSH1 および MSH2 フィールドが整形を決定します。 MSH1 には、1 つだけの文字が必要です。 MSH2 は 2 ~ 4 文字である必要があり、文字を繰り返すことがありません。  
  
## <a name="hl7-body-validation"></a>HL7 本文の検証  
 HL7 逆アセンブラおよびアセンブラは、2.X メッセージの本文の基本的な構造検証とスキーマの検証を有効にする場合は、実行します。  
  
 本文の基本的な構造検証される[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]常に実行する、次の検証が含まれます。  
  
-   セグメントで 3 つの文字があること  
  
-   セグメント区切り記号がである\<CR\>または\<CR\>\<LF\> (最後のセグメントの省略可能)  
  
-   フィールドの区切り記号が適切であります。  
  
-   宣言されていない Z セグメント (定義済みの 3 文字セグメント タグ) で宣言されたセグメントがないこと  
  
 本文のスキーマの検証をより広範な次のとおりです。  
  
-   末尾のフィールドの区切り記号  
  
     MSH ヘッダー セグメントと本文セグメント  
  
-   Z セグメント  
  
-   XSD でサポートされているとカスタム データ型  
  
     サポートされている XSD および XSD 以外の型 (TS (タイムスタンプ)、DT (date)、TM (時間)、および TN (電話番号)  
  
-   列挙型  
  
     ID (HL7 定義テーブル) と IS (ユーザー定義テーブル)  
  
-   Optionality  
  
     必須およびオプション  
  
-   繰り返し  
  
     セグメントとフィールド  
  
-   エスケープ シーケンス  
  
     文字エン コード、書式、および文字セット  
  
 有効にするにまたはから受信した、または (送信元パーティの逆アセンブラー、アセンブラーの送信先パーティ) の特定のパーティに送信されるすべてのメッセージのスキーマの検証を無効にするとします。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]MSH9.3 メッセージ構造のヘッダー フィールド、MSH12 バージョン ID フィールド (2.3.1、2.4 または 2.5) と、名前空間での設定によって決定される、この処理に直接 2.X スキーマを使用して、HL7[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラー。  
  
## <a name="hl7-disassembler-processing"></a>HL7 逆アセンブラーの処理  
 HL7 逆アセンブラーは、処理のための XML セグメントに受信 HL7 メッセージを解析します。 メッセージを解析する際、逆アセンブラーは、次のタスクを実行します。  
  
-   ハンドルのエスケープ シーケンス  
  
-   必須/オプションのプロパティのチェックを処理します。  
  
-   ハンドルには、セグメントと未定義または予期しない Z セグメントが定義されている (Z セグメントの説明は、次を参照してください。 [Z オブジェクトを介してメッセージをカスタマイズする](../../adapters-and-accelerators/accelerator-hl7/customizing-messages-through-z-objects.md))。  
  
-   予期しないセグメント、インスタンスの最後 (宣言されていない Z セグメントになります) は無視されます。  
  
## <a name="error-reporting"></a>[エラー報告]  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]標準 HL7 エラー形式では、セグメント、シーケンス、フィールド、およびエラー コードが含まれているほとんどのエラーを報告します。 ただし、エラー条件がありますなるようなすべての利用可能なたとえば、スキーマが存在しない場合。 このようなケースを処理するために[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]、代替のエラーを報告することができます[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]エラー形式です。 メッセージのエラー セグメントには、2 つの部分が含まれています: HL7 エラーと別名のいずれかのいずれかの[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]エラーです。  
  
## <a name="ack-generation"></a>確認の生成  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]2.X メッセージの受信確認 (Ack) の次の種類をサポートします。 HL7 両方エラーの種類と[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)](代替) エラーの種類が使用されます。  
  
-   元のメッセージと ACK のマッピング  
  
-   HL7 元 Ack  
  
-   HL7 Ack の強化  
  
     コミットがそのまま使用し、アプリケーションの同意  
  
-   ACK の静的/プロキシ  
  
     ACK または NAK  
  
## <a name="property-promotion"></a>プロパティの昇格  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]次の 2.X プロパティの昇格をサポートします。  
  
-   プロパティ スキーマ  
  
-   MSH ヘッダー スキーマ  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [HL7 2.X 逆アセンブラーのスキーマ決定](../../adapters-and-accelerators/accelerator-hl7/schema-determination-in-the-hl7-2-x-disassembler.md)  
  
-   [HL7 2.X アセンブラーのスキーマ決定](../../adapters-and-accelerators/accelerator-hl7/schema-determination-in-the-hl7-2-x-assembler.md)  
  
## <a name="see-also"></a>参照  
 [メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/message-processing.md)   
 [HL7 メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md)   
 [HL7 2.X スキーマの使用](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)