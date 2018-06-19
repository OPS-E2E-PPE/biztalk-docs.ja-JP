---
title: SWIFT スキーマ |Microsoft ドキュメント
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
ms.openlocfilehash: 1b4bac26d99fb3282650c20381bbc18237f8908a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214922"
---
# <a name="swift-schemas"></a>SWIFT スキーマ
[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]送信し、非常に高速ネットワーク経由で個々 のフラット ファイルとして SWIFT の財務 (FIN) メッセージを受け取ります。 各メッセージは、定義済みの一連のラベルの付いたフィールドと位置指定引数または順序付けられたサブフィールド、およびトレーラーをトレーラ ブロック内の一連の構成のテキスト ブロック ヘッダー ブロックのセットで構成されます。 テキスト ブロックの内容は、メッセージの種類によって異なります。  
  
 SWIFT の財務 (FIN) メッセージのバッチを交換する多くのアプリケーションもあります: 1 つのファイルに含まれるメッセージのセット。 ファイルがローカルで配信される可能性がありますか、FileAct を介して送信される可能性があります (SWIFT IP ネットワーク経由で — SIPN)、または FTP を使用します。  
  
 バッチ処理や、個別に送信されるのかどうかに関係なく、これらのメッセージに関連付けられているデータの操作を簡単に[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]各メッセージの種類を定義する XSD スキーマを提供します。 このスキーマは、メッセージを適切なスキーマに自動的に関連付けられているし、SWIFT ネットワークは、XML との間で使用される、外部のフラット ファイル表記の間で自動的に変換できるように、メッセージの種類を昇格させます。  
  
 スキーマには、すべてのヘッダー、テキスト、およびトレーラーを含むブロックが含まれます。 このスキーマは、十分に総合的 FIN メッセージ レベルのプロトコルを使用して、SWIFT ネットワーク経由でメッセージを送信して、すべての SWIFT ネットワーク経由で受信したメッセージに関連付けられている情報を格納するために、インターチェンジのスキーマはします。  
  
 各メッセージの種類のスキーマは、全体的な形式とそのメッセージの種類のコンテキストを定義します。 A4SWIFT では、各ブロックを定義します。 各ブロック内のフィールドおよびサブフィールド レイアウトされます。必要に応じて、フィールドおよびサブフィールドが別のスキーマで定義されている一般的な基本または複合型から構築されます。 スキーマ レベルの検証には、形式、文字セット、設定値、範囲、必須/オプション、再現性、位置、および必要に応じて、長さが含まれています。 ビジネス ルールは、クロス フィールド検証およびその他の論理チェックを実行します。  
  
 このセクションには、次のトピックが含まれています。  
  
-   [サンプル メッセージ プレゼンテーション](../../adapters-and-accelerators/accelerator-swift/sample-message-presentation.md)  
  
-   [サンプル スキーマ プレゼンテーション](../../adapters-and-accelerators/accelerator-swift/sample-schema-presentation.md)  
  
-   [SWIFT ヘッダー](../../adapters-and-accelerators/accelerator-swift/swift-headers.md)  
  
-   [SWIFT テキスト](../../adapters-and-accelerators/accelerator-swift/swift-text.md)  
  
-   [SWIFT は、トレーラー](../../adapters-and-accelerators/accelerator-swift/swift-trailers.md)  
  
-   [SWIFT メッセージ標準を更新](../../adapters-and-accelerators/accelerator-swift/updating-swift-messaging-standards.md)