---
title: "メッセージの検証エンジン |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- message validation engine
- errors, validating
- XML validation
- parsing validation
- BRE policies, validating
- errors, messages
- messages, errors
- validating, messages
- validating, BRE policies
- validating, XML
- messages, validating
- validating, errors
- validating, parsing
ms.assetid: 4ba0b75e-665b-4771-b04f-5bc3e90d83f0
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dbdcb375c04e4c9684b2a805c7a7a7315f46f83d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="message-validation-engine"></a>メッセージ検証エンジン
によって提供される最も重要な機能の 1 つ[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]SWIFT ネットワーク、または (取引先によって送信された) SWIFT ネットワークから受信したバックエンド システムから受信した SWIFT のメッセージを完全に検証する機能です。 送信 SWIFT メッセージの検証メッセージが SWIFT 標準に準拠していることと、SWIFT ネットワークは、メッセージを拒否していないことを保証します。  
  
 他の金融機関から受信したメッセージが特定の契約 (ビジネス ルールの場合)、リレーションシップに固有に従うことにより、SWIFT メッセージの受信を検証しています。 両方のシナリオでは、トランザクションのコストと総コスト (tco) を軽減する方法で検証し、メッセージをコミットする前にエラーをトラップする機能できます。  
  
 次に、A4SWIFT 検証エンジンを構成する 4 つの部分を説明します。  
  
-   フラット ファイル パーサーによって実行される構造の検証  
  
-   リーダーを検証する XML によって実行されるデータ検証  
  
-   ルールの検証ビジネス ルール エンジン (BRE) での実行に SWIFT ネットワークとの使用  
  
-   メッセージのマーキングと「最適な」のエラーの収集  
  
## <a name="structural-validation-parsing"></a>(解析) 構造の検証  
 A4SWIFT SWIFT 標準に従って各 SWIFT メッセージの種類に対して定義されている XSD スキーマに対して SWIFT のフラット ファイル メッセージを解析します。 XML に、フラット ファイルの解析は、フラット ファイルが構造的に正しいことを保証します。 解析は、XML を読み取り、操作、またはその他の形式またはメッセージの種類の変換を簡単にも生成します。 データの有効性のスキーマに対して XML を検証してより複雑な評価のビジネス ルール エンジン (BRE) を使用することができますも。  
  
 SWIFT の逆アセンブラーでは、SWIFT の逆アセンブラーによって呼び出された SWIFT のフラット ファイル メッセージを解析する、BizTalk フラット ファイル パーサーを呼び出します。 SWIFT の逆アセンブラーでは、エラーのコレクションで、解析時に発生したエラーの詳細を記録、常に最初のパスでできるだけ多くの構造エラーを収集するために、データの解析を続行しようとします。 ただし、ほとんどの解析エラーは致命的なものし、最初のエラーでメッセージの処理を停止します。  
  
 構造の検証の詳細については、次を参照してください。[スキーマの操作](../../adapters-and-accelerators/accelerator-swift/working-with-schemas.md)です。  
  
## <a name="data-validation-xml-validation"></a>データ検証 (XML の検証)  
 整形式 XML として定義された XSD スキーマに準拠している構造の検証に合格した SWIFT のメッセージを定義することができます。 A4SWIFT には、解析ステージ中に SWIFT メッセージの構造上有効な XML が生成されます。 A4SWIFT の対応する XSD スキーマで定義された制約に対してデータの正確性は、この XML を検証できます。  
  
 これらの制約には、入力データ、長さ、および値の範囲は標準の SWIFT に従って定義が含まれます。 SWIFT の逆アセンブラーでは、データの検証を実行するリーダーを検証する XML を呼び出します。  
  
 SWIFT の逆アセンブラーは、XML の検証中に発生したエラーの詳細をエラー コレクションに記録し、最初のパスでできるだけ多くの XML 検証エラーを収集する残りのデータの検証を続行します。 (解析とは異なり XML 検証の継続が保証されます。)  
  
 データの検証の詳細については、次を参照してください。[スキーマの操作](../../adapters-and-accelerators/accelerator-swift/working-with-schemas.md)です。  
  
## <a name="swift-network-and-usage-rule-validation-bre-validation"></a>SWIFT ネットワークと使用量ルールの検証 (BRE 検証)  
 A4SWIFT は、ビジネス ルール エンジン (BRE) ポリシーと照らしてビジネス レベルの正確性の構造上有効な SWIFT メッセージの XML を検証します。 これらのポリシーには、SWIFT ネットワークと使用状況規則と、SWIFT 標準に従って定義されている他の複雑なクロス フィールド規則の適用が含まれます。 SWIFT の逆アセンブラーでは、ビジネス レベルの検証を実行する、BRE を呼び出します。  
  
 SWIFT の逆アセンブラーは、BRE の検証中に発生したエラーの詳細をエラー コレクションに記録し、最初のパスでできるだけ多くの BRE 検証エラーを収集する残りのデータの検証を続行します。 (XML 検証のように BRE 検証の継続が保証されます。)  
  
 SWIFT ネットワークと使用量ルールの検証の詳細については、次を参照してください。 [BRE ポリシーの扱い](../../adapters-and-accelerators/accelerator-swift/working-with-bre-policies.md)です。  
  
## <a name="validation-failures-and-message-marking"></a>検証エラーとメッセージのマーク付け  
 A4SWIFT が検証エラーとメッセージの検証の各段階の詳細情報を収集: 構造的な解析、XML の検証、および BRE です。 A4SWIFT は、可能なメッセージについて多くのエラー情報を収集する「最適な」ヒューリスティックを使用してこれらのエラーを収集します。 この機能は、キャッチされたすべてのエラーが発生し、submit の複数のイテレーションを必要するのではなく、1 つのパスで報告される検証、失敗、修正、再送信に失敗したメッセージを使用します。  
  
 エラーのコレクション内のいずれかの検証段階中には、少なくとも 1 つのエラーがあるメッセージは、無効と見なされは失敗しました。 A4SWIFT がこれらのメッセージをメッセージ ボックス データベースに発行しますが、メッセージの検証が失敗したことを示すために昇格させたプロパティ、および各検証ステージのレポート エラー カウントにマークされています。  
  
 昇格させたプロパティに加えて、A4SWIFT は XML に、エラーのコレクションをシリアル化し、"エラー"、マルチパート メッセージの部分としてコレクションをアタッチします。 最後のメッセージから成る本文部分に失敗したメッセージとエラー コレクション XML エラーの部分でとエラー状態を示す A4SWIFT 昇格させたプロパティを持つ拡張します。 SWIFT の逆アセンブラーは、このマルチパート メッセージをメッセージ ボックス データベースに発行します。  
  
 BizTalk 送信ポートまたはオーケストレーションから取得できます失敗したメッセージ、メッセージ ボックス データベース昇格 A4SWIFT の特殊なプロパティをサブスクライブすることで。 特定の検証段階からすべての失敗したメッセージまたはエラーの特定の数のメッセージだけを取得するサブスクリプションを行うことができます。  
  
 失敗したメッセージが取得された後は、レポート作成アプリケーション、修復アプリケーションまたはプロセス、または障害リポジトリに送信することができます。 または破棄できます。  
  
 この機能に失敗したメッセージに、サブスクリプションでのエラーの種類を区別する) を購読、多くの情報がエラーのコレクションと組み合わせると、失敗した各メッセージにアタッチされている XML フォームの単純なエラーを開発するための強力なフレームワークレポートなど、メッセージの修復が提供する、アプリケーションと A4SWIFT セットアップによってインストールされている新しい送信機能。  
  
 検証の失敗とマーク付けはメッセージの詳細については、次を参照してください。[メッセージ サブスクリプションの失敗の操作](../../adapters-and-accelerators/accelerator-swift/working-with-failed-message-subscriptions.md)です。  
  
## <a name="see-also"></a>参照  
 [BizTalk Accelerator for SWIFT のランタイム](../../adapters-and-accelerators/accelerator-swift/biztalk-accelerator-for-swift-runtime.md)