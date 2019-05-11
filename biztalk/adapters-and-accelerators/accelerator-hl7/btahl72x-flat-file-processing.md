---
title: BTAHL72X フラット ファイル処理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bd0755b31e56474a4cfde05264b0e1696d3aece7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65251489"
---
# <a name="btahl72x-flat-file-processing"></a>BTAHL72X フラット ファイル処理
Microsoft BizTalk Accelerator for HL7 の次のコンポーネント ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) プロセス HL7 2.X (HL7 でエンコードされた) メッセージ。  
  
- パイプラインとコア ライブラリ:[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]します。PipelineCommon.dll と[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]します。PipelineMessageCore.dll  
  
- アセンブラーおよび逆アセンブラー ライブラリ:[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]します。HL72fAsm.dll と[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]します。HL72fDAsm.dll  
  
- 送信アダプターのための双方向の MLLP 受信確認 (ACK) 検証ライブラリ:[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]します。HL7ACKHelper.dll  
  
## <a name="hl7-message-modes"></a>HL7 メッセージ モード  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 2.X のメッセージを次のメッセージ モードをサポートしています。  
  
- パブリッシャーとサブスクライバー (パブリッシュ-サブスクライブ) モード  
  
   パブリッシャーにブロードキャストする宣言型または要請されていないが、サブスクライバーのパーティを更新します。 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]デザイン時後のサブスクリプションとパーティを管理できるため、このモードでは、柔軟性を提供します。  
  
- 要求-応答モード  
  
   Interrogative またはクエリ メッセージ交換を特定のエンティティから特定の要求の結果、応答メッセージ。  
  
## <a name="flat-file-parsing"></a>フラット ファイル解析  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 解析 HL7 2.X を 3 つの部分にマルチパート メッセージ:  
  
-   ヘッダー MSH パーツ  
  
-   ボディ部  
  
-   Z の一部  
  
## <a name="hl7-header-validation"></a>HL7 ヘッダーの検証  
 HL7 の逆アセンブラーとアセンブラーは、メッセージを処理できることを確認するには、2.X のメッセージのヘッダーの構造とスキーマの検証を実行します。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 一般的なヘッダー スキーマ、MSH_25_GLO_DEF の概略図の検証を行います。  
  
 たとえば、MSH1 と MSH2 フィールドが整形パーサーを決定します。 MSH1 には、1 つだけの文字が必要です。 文字を繰り返すことがないと、2 ~ 4 つの文字、MSH2 があります。  
  
## <a name="hl7-body-validation"></a>HL7 の本文の検証  
 HL7 の逆アセンブラーとアセンブラーは、2.X のメッセージの本文の基本的な構造の検証とスキーマの検証を有効にした場合実行します。  
  
 本文の基本的な構造検証を[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]常に実行する、次の検証が含まれます。  
  
- セグメントで 3 つの文字があること  
  
- セグメント区切り記号が\<CR\>または\<CR\>\<LF\> (最後のセグメントは省略可能)  
  
- フィールド区切り記号が適切であります。  
  
- 未宣言の Z セグメント (定義済みの 3 文字セグメント タグ) で宣言されたセグメントがないこと  
  
  本文のスキーマ検証がより広範な次のとおりです。  
  
- 末尾のフィールドの区切り記号  
  
   ヘッダー MSH セグメントとセグメントの本文  
  
- Z セグメント  
  
- XSD でサポートされていると、カスタムのデータ型  
  
   サポートされている XSD と XSD 以外の型 (TS (タイムスタンプ)、DT (date)、TM (時間)、および TN (電話番号)  
  
- 列挙  
  
   ID (HL7 定義テーブル) とは (ユーザー定義テーブル)  
  
- Optionality  
  
   必須およびオプション  
  
- 繰り返し  
  
   セグメントとフィールド  
  
- エスケープ シーケンス  
  
   文字エン コード、書式、および文字セット  
  
  有効またはから受信した、または (送信元パーティの逆アセンブラー、アセンブラーの送信先パーティ) の特定のパーティに送信されるすべてのメッセージの概略図の検証を無効にするとします。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] MSH9.3 メッセージ構造のヘッダー フィールド (2.3.1、2.4、または 2.5)、MSH12 バージョン ID フィールドおよび設定名前空間によって決定される、この処理を直接使用して、HL7 2.X スキーマ[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラー。  
  
## <a name="hl7-disassembler-processing"></a>HL7 の逆アセンブラーの処理  
 HL7 の逆アセンブラーでは、HL7 メッセージの受信を処理するための XML セグメントに解析します。 メッセージを解析する際、逆アセンブラーは、次のタスクを実行します。  
  
-   ハンドルのエスケープ シーケンス  
  
-   必須/任意のプロパティのチェックを処理します。  
  
-   Z セグメントで未定義または予期しないセグメントをハンドルが定義されている (Z セグメントの説明は、次を参照してください。 [Z オブジェクト経由でメッセージをカスタマイズする](../../adapters-and-accelerators/accelerator-hl7/customizing-messages-through-z-objects.md))。  
  
-   (なる Z セグメントが宣言されていない) インスタンスの末尾に予期しないセグメントを無視します。  
  
## <a name="error-reporting"></a>[エラー報告]  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 標準 HL7 エラー形式では、セグメント、シーケンス、フィールド、およびエラー コードを含むほとんどのエラーを報告します。 ただし、エラー条件がありますなどすべての使用できるようにする、たとえば、スキーマが存在しない場合。 、このようなケースを処理する[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]代替でエラーが報告できる[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]エラー形式。 メッセージのエラー セグメントに 2 つの部分が含まれています: 1 つは HL7 エラー、1 つの別名[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]エラー。  
  
## <a name="ack-generation"></a>確認の生成  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 2.X のメッセージの受信確認 (Ack) の次の種類をサポートしています。 HL7 両方エラーの種類と[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)](代替) エラーの種類が使用されます。  
  
-   元のメッセージと ACK のマッピング  
  
-   HL7 の元の確認  
  
-   HL7 の Ack を強化します。  
  
     コミットがそのまま使用し、アプリケーションの同意  
  
-   静的/プロキシの確認  
  
     ACK または NAK  
  
## <a name="property-promotion"></a>プロパティの昇格  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 2.X の次のプロパティの昇格をサポートしています。  
  
-   プロパティ スキーマ  
  
-   MSH ヘッダー スキーマ  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [HL7 2.X 逆アセンブラーのスキーマ決定](../../adapters-and-accelerators/accelerator-hl7/schema-determination-in-the-hl7-2-x-disassembler.md)  
  
-   [HL7 2.X アセンブラーのスキーマ決定](../../adapters-and-accelerators/accelerator-hl7/schema-determination-in-the-hl7-2-x-assembler.md)  
  
## <a name="see-also"></a>参照  
 [メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/message-processing.md)   
 [HL7 メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md)   
 [HL7 2.X スキーマの使用](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)