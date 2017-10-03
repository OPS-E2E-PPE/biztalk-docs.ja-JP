---
title: "コンテキスト プロパティを使用して |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, context properties
- messages, promoted properties
- promoted properties, context properties
- context properties, messages
ms.assetid: 306127a9-df03-4aaf-8dd8-76df51eb193d
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bc82cc75df5d8b73e3780e451b1c380e08ef1cec
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="using-context-properties"></a>コンテキスト プロパティを使用します。
BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) メッセージング エンジンとそのコンポーネントのコンテキスト プロパティを内部的に使用します。 エンジンの実行ロジックに影響を与えるため、いくつかのコンテキスト プロパティ、エンジンによって設定された値の変更はお勧めできません。 ただし、多くのエンジンによって設定されていないプロパティを変更できます。 送信ポートのフィルター式を作成するため、コンテキスト プロパティを使用することができます (詳細については、次を参照してください。[送信ポートのフィルター式を設定](../../adapters-and-accelerators/accelerator-hl7/setting-filter-expressions-on-send-ports.md))。 オーケストレーションのフィルター式のコンテキスト プロパティを使用することもできます。 プロパティは、プロジェクトのグローバル プロパティ スキーマを参照している限り、フィルター式の使用可能な (これ[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]一般的なテンプレートのいずれかを使用するときに作成) します。  
  
 次の表の一覧を含む[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]メッセージ コンテキスト プロパティ、メッセージング エンジンを使用します。 エンジンは、ルーティングにこれらのプロパティの多くを使用します。 シリアライザーは、その処理を他のユーザーを使用します。 これらのプロパティのプレフィックスがある[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]です。  
  
 詳細については[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)](BTS プリフィックスでフィルター式で識別される)、それらのコンテキスト プロパティの「メッセージ コンテキスト プロパティ」を参照してください[!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]ヘルプ。 **BTS です。SchemaStrongName**と**BTS です。MessageType** 2 つのプロパティを[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]エンジンを使用します。  
  
 次の表に、昇格するには、必要な列は、次の影響を及ぼします。  
  
-   IsPromoted の場合は"N"、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]昇格ではなく、コンテキストに値を書き込みます。  
  
-   IsRequired の場合はブール型の場合に、"N"[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]これが true のかどうか、値のみを書き込みます。  
  
-   IsRequired の場合は文字列型の場合は、"N"[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]が空白でない場合、または既定値が存在する場合、値を書き込みます。  
  
|プロパティ名|昇格するには|必要|注|  
|-------------------|-----------------|-----------------|-----------|  
|BatchDateTime|Y|×|[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]バッチ メッセージを処理するときは、このプロパティを昇格させます。|  
|[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]MessageType|Y|Y|シリアライザーは、1 つとバッチのメッセージを区別するためにこのプロパティを使用します。 HL7 逆アセンブラーは、バッチのメッセージに対してのみ設定されます。 プロパティは、メッセージが 1 つのメッセージ、受信バッチ メッセージの場合、または送信バッチ メッセージかどうかを示します。 シリアライザーがこれにも見つからない場合は、メッセージが 1 つのメッセージであると見なします。|  
|FHS10|Y|×|[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]バッチ メッセージを処理するときは、このプロパティを昇格させます。|  
|FHS3|Y|×|[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]バッチ メッセージを処理するときは、このプロパティを昇格させます。|  
|FHS4|Y|×|[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]バッチ メッセージを処理するときは、このプロパティを昇格させます。|  
|FHS5|Y|×|[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]バッチ メッセージを処理するときは、このプロパティを昇格させます。|  
|FHS6|Y|×|[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]バッチ メッセージを処理するときは、このプロパティを昇格させます。|  
|FileDateTime|Y|×|[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]バッチ メッセージを処理するときは、このプロパティを昇格させます。|  
|LastSegmentDelimiter がありません。|×|×|[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]バッチ メッセージを処理するときは、このプロパティを昇格させます。|  
|MessageClass|Y|Y|いずれかが含まれています**MessageClass2X**または**MessageClass2Xml**メッセージの 2 つのクラスを区別するためにします。|  
|MSA1|Y|Y|ACK メッセージに対してのみ適用できます。|  
|MSH1|×|Y|フィールドの区切り記号が含まれているフィールドです。 シリアライザーは、このプロパティを使用します。|  
|MSH2|×|Y|シリアライザーは、このプロパティを使用します。 (コンポーネントの区切り記号、繰り返し区切り記号、エスケープ文字、およびサブコンポーネントの区切り記号) エンコード文字を含んでいるフィールドです。|  
|MSH3_1|Y|×|送信側のアプリケーションのフィールドの最初のコンポーネントです。|  
|MSH3_2|Y|×|送信側のアプリケーションのフィールドの 2 番目のコンポーネントです。|  
|MSH3_3|Y|×|送信側のアプリケーションのフィールドの 3 番目のコンポーネントです。|  
|MSH5_1|Y|×|受信側のアプリケーションのフィールドの最初のコンポーネントです。|  
|MSH5_2|Y|×|受信側のアプリケーションのフィールドの 2 番目のコンポーネントです。|  
|MSH5_3|Y|×|受信側のアプリケーションのフィールドの 3 番目のコンポーネントです。|  
|ParseError|Y|Y|解析中にエラーが発生したことを示します。|  
|SegmentDelimiter2Char|×|×|セグメントを区切る文字です。|  
|ToBeBatched|Y|×|False に設定すると[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]は後で、それ以外のバッチ処理対象メッセージ、バッファーしない[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]バッチの一部としてメッセージを送信します。|  
|ZPartPresent|Y|×|宣言されていない Z セグメントが存在するかどうかを示します。|  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [送信ポートのフィルター式を設定](../../adapters-and-accelerators/accelerator-hl7/setting-filter-expressions-on-send-ports.md)