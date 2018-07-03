---
title: コンテキスト プロパティの使用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, context properties
- messages, promoted properties
- promoted properties, context properties
- context properties, messages
ms.assetid: 306127a9-df03-4aaf-8dd8-76df51eb193d
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b13af4b6325cddb4a642a24bcd61c42a102531e1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980683"
---
# <a name="using-context-properties"></a>コンテキスト プロパティの使用
BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) メッセージング エンジンとそのコンポーネントのコンテキスト プロパティを内部的に使用します。 エンジンの実行ロジックに影響を与えるため、一部のコンテキスト プロパティのエンジンによって設定された値の変更はお勧めできません。 ただし、多くのエンジンによって設定されていないプロパティを変更できます。 送信ポートのフィルター式の作成のコンテキスト プロパティを使用することができます (詳細については、次を参照してください。[送信ポートのフィルター式の設定](../../adapters-and-accelerators/accelerator-hl7/setting-filter-expressions-on-send-ports.md))。 オーケストレーションのフィルター式のコンテキスト プロパティを使用することもできます。 プロパティは、プロジェクトのグローバル プロパティ スキーマを参照している限り、フィルター式の使用可能な (が[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]いずれかの一般的なテンプレートを使用するときに作成します)。  
  
 次の表には一覧が含まれています[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]メッセージ コンテキスト プロパティ、メッセージング エンジンを使用します。 エンジンは、ルーティングにこれらのプロパティの多くを使用します。 シリアライザーは、他のユーザーがその処理を使用します。 これらのプロパティのプレフィックスがある[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]します。  
  
 詳細については[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)](BTS プレフィックスでフィルター式で識別される)、それらのコンテキスト プロパティは、BizTalk Server ヘルプの「メッセージ コンテキスト プロパティ」を参照してください。 **BTS します。SchemaStrongName**と**BTS します。MessageType** 2 つのプロパティを[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]エンジンを使用します。  
  
 次の表は昇格され、必要な列は、次の影響を与えます。  
  
- IsPromoted の場合は"N"[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]昇格ではなく、コンテキストに値を書き込みます。  
  
- IsRequired の場合はブール型の場合に、"N"[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]これが true のかどうか、値だけを書き込みます。  
  
- IsRequired がある場合、文字列型の"N"[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]が空白でない場合、または既定値が存在する場合に、値を書き込みます。  
  
|                                           プロパティ名                                            | 昇格します。 | 必要です。 |                                                                                                                                                                      注                                                                                                                                                                       |
|----------------------------------------------------------------------------------------------------|-------------|-------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                           BatchDateTime                                            |      Y      |      ×      |                                                                                                [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] バッチ メッセージを処理するときは、このプロパティを昇格させます。                                                                                                 |
| [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]メッセージの種類 |      Y      |      Y      | シリアライザーでは、このプロパティを使用して、1 つとバッチのメッセージを区別します。 HL7 の逆アセンブラーは、バッチのメッセージに対してのみこれを設定します。 プロパティは、メッセージが 1 つのメッセージ、受信バッチ メッセージの場合、または送信バッチ メッセージかどうかを示します。 シリアライザーがこれにも見つからない場合は、メッセージが 1 つのメッセージであると仮定します。 |
|                                               FHS10                                                |      Y      |      ×      |                                                                                                [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] バッチ メッセージを処理するときは、このプロパティを昇格させます。                                                                                                 |
|                                                FHS3                                                |      Y      |      ×      |                                                                                                [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] バッチ メッセージを処理するときは、このプロパティを昇格させます。                                                                                                 |
|                                                FHS4                                                |      Y      |      ×      |                                                                                                [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] バッチ メッセージを処理するときは、このプロパティを昇格させます。                                                                                                 |
|                                                FHS5                                                |      Y      |      ×      |                                                                                                [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] バッチ メッセージを処理するときは、このプロパティを昇格させます。                                                                                                 |
|                                                FHS6                                                |      Y      |      ×      |                                                                                                [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] バッチ メッセージを処理するときは、このプロパティを昇格させます。                                                                                                 |
|                                            FileDateTime                                            |      Y      |      ×      |                                                                                                [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] バッチ メッセージを処理するときは、このプロパティを昇格させます。                                                                                                 |
|                                    LastSegmentDelimiter がありません。                                    |      ×      |      ×      |                                                                                                [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] バッチ メッセージを処理するときは、このプロパティを昇格させます。                                                                                                 |
|                                            MessageClass                                            |      Y      |      Y      |                                                                                                                  いずれかが含まれています**MessageClass2X**または**MessageClass2Xml**メッセージの 2 つのクラスを区別します。                                                                                                                  |
|                                                MSA1                                                |      Y      |      Y      |                                                                                                                                                        ACK メッセージに対してのみ適用されます。                                                                                                                                                         |
|                                                MSH1                                                |      ×      |      Y      |                                                                                                                                   フィールドの区切り記号を含むフィールド。 シリアライザーは、このプロパティを使用します。                                                                                                                                   |
|                                                MSH2                                                |      ×      |      Y      |                                                                                    シリアライザーは、このプロパティを使用します。 (コンポーネントの区切り記号、繰り返し区切り記号、エスケープ文字、およびサブコンポーネントの区切り記号) エンコード文字を含むフィールドです。                                                                                    |
|                                               MSH3_1                                               |      Y      |      ×      |                                                                                                                                              送信側のアプリケーションのフィールドの最初のコンポーネント。                                                                                                                                               |
|                                               MSH3_2                                               |      Y      |      ×      |                                                                                                                                              送信側のアプリケーションのフィールドの 2 番目のコンポーネント。                                                                                                                                              |
|                                               MSH3_3                                               |      Y      |      ×      |                                                                                                                                              送信側のアプリケーションのフィールドの 3 番目のコンポーネント。                                                                                                                                               |
|                                               MSH5_1                                               |      Y      |      ×      |                                                                                                                                             受信側のアプリケーションのフィールドの最初のコンポーネント。                                                                                                                                              |
|                                               MSH5_2                                               |      Y      |      ×      |                                                                                                                                             受信側のアプリケーションのフィールドの 2 番目のコンポーネント。                                                                                                                                             |
|                                               MSH5_3                                               |      Y      |      ×      |                                                                                                                                             受信側のアプリケーションのフィールドの 3 番目のコンポーネント。                                                                                                                                              |
|                                             ParseError                                             |      Y      |      Y      |                                                                                                                                                 解析中にエラーが発生したことを示します。                                                                                                                                                 |
|                                       SegmentDelimiter2Char                                        |      ×      |      ×      |                                                                                                                                                      セグメントを区切る文字。                                                                                                                                                       |
|                                            ToBeBatched                                             |      Y      |      ×      |                       False に設定すると[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]は後で。 そうしないと、バッチ処理するメッセージ、バッファーしない[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]バッチの一部としてメッセージを送信します。                       |
|                                            ZPartPresent                                            |      Y      |      ×      |                                                                                                                                              未宣言の Z セグメントが存在するかどうかを示します。                                                                                                                                               |
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [送信ポートのフィルター式の設定](../../adapters-and-accelerators/accelerator-hl7/setting-filter-expressions-on-send-ports.md)