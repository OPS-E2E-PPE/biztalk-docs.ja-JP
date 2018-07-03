---
title: SWIFT スキーマ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SWIFT, SWIFT messages
- schemas, SWIFT
- SWIFT messages, SWIFT schemas
- SWIFT, schemas
ms.assetid: 53017a56-a718-4577-a08c-9c92d9a54e7a
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f749a06c694007008f3d8138b2b087b77b2c4f03
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996115"
---
# <a name="swift-schemas"></a>SWIFT スキーマ
[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] 送信し、SWIFT ネットワーク経由で個々 のフラット ファイルとして SWIFT の財務 (FIN) メッセージを受け取ります。 各メッセージは、一連のヘッダーのブロックの定義済みの一連のラベル付きのフィールドと位置指定または順序付きのサブフィールドとトレーラーのブロック内でトレーラーのセットから成るテキスト ブロックで構成されます。 テキスト ブロックの内容は、メッセージの種類によって異なります。  
  
 SWIFT の財務 (FIN) メッセージのバッチを交換する多くのアプリケーションもあります: 1 つのファイルに含まれるメッセージのセット。 ファイルがローカルに配信される可能性がありますまたは FileAct を介して送信される可能性があります (SWIFT IP ネットワーク経由で — SIPN)、または FTP を使用します。  
  
 データの操作を簡略化するに関連付けられているバッチ処理や、個別に送信されるのかどうかに関係なく、これらのメッセージ Microsoft[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]各メッセージの種類を定義する XSD スキーマを提供します。 このスキーマは、メッセージを適切なスキーマに自動的に関連付けられているし、XML との間は、SWIFT ネットワークで使用される、外部のフラット ファイル表記の間で自動的に変換できるように、メッセージの種類を昇格させます。  
  
 スキーマには、すべてのヘッダー、テキスト、およびトレーラーを含むブロックが含まれます。 このスキーマは、総合的なのに十分な FIN メッセージ レベルのプロトコルを使用して行う SWIFT ネットワーク経由でメッセージを送信して、すべての SWIFT ネットワーク経由で受信したメッセージに関連付けられた情報を格納するために、インターチェンジのスキーマは。  
  
 各メッセージの種類のスキーマは、全体的な形式とそのメッセージの種類のコンテキストを定義します。 A4SWIFT では、各ブロックを定義します。 各ブロック内では、フィールドとサブフィールド配置されます。必要に応じて、フィールドとサブフィールドが個別のスキーマで定義されている一般的な基本または複合型から構築されます。 スキーマ レベルの検証には、形式、文字セット、設定値、範囲、必須/任意、再現性、位置、および必要に応じて、長さが含まれています。 ビジネス ルールでは、クロス フィールド検証やその他の論理チェックを実行します。  
  
 このセクションには、次のトピックが含まれています。  
  
-   [サンプル メッセージ プレゼンテーション](../../adapters-and-accelerators/accelerator-swift/sample-message-presentation.md)  
  
-   [サンプル スキーマ プレゼンテーション](../../adapters-and-accelerators/accelerator-swift/sample-schema-presentation.md)  
  
-   [SWIFT ヘッダー](../../adapters-and-accelerators/accelerator-swift/swift-headers.md)  
  
-   [SWIFT テキスト](../../adapters-and-accelerators/accelerator-swift/swift-text.md)  
  
-   [SWIFT トレーラー](../../adapters-and-accelerators/accelerator-swift/swift-trailers.md)  
  
-   [SWIFT メッセージ規格の更新](../../adapters-and-accelerators/accelerator-swift/updating-swift-messaging-standards.md)