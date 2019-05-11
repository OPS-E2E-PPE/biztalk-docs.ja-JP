---
title: メッセージ検証エンジン |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bd286de8a1f2b0d9947a87cedaafd2a0efbce976
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377193"
---
# <a name="message-validation-engine"></a>メッセージ検証エンジン
によって提供される最も重要な機能の 1 つ[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)](取引先によって送信されます)、SWIFT ネットワーク間で送受信を行う SWIFT ネットワーク宛てのバックエンド システムから受信した SWIFT のメッセージを完全に検証する機能です。 SWIFT メッセージの送信の検証、メッセージは、SWIFT 標準に準拠しているし、SWIFT ネットワークによって、メッセージは拒否されないことを保証します。  
  
 他の金融機関から受信したメッセージが特定の契約 (ビジネス ルール) リレーションシップに固有に従うことにより、SWIFT メッセージの受信を検証しています。 両方のシナリオでは、検証し、メッセージをコミットする前にエラーをトラップする機能により、トランザクションの費用と総保有コスト (tco) 削減します。  
  
 A4SWIFT 検証エンジンを構成する 4 つの部分は次のとおりです。  
  
-   フラット ファイル パーサーによって実行される構造の検証  
  
-   リーダーを検証する XML によって実行されるデータの検証  
  
-   ルールのビジネス ルール エンジン (BRE) で実行される検証を行う SWIFT ネットワークと使用状況  
  
-   メッセージのマーキングと「ベスト エフォート」のエラーの収集  
  
## <a name="structural-validation-parsing"></a>(解析) 構造の検証  
 A4SWIFT SWIFT 標準に従って各 SWIFT メッセージの種類に対して定義されている XSD スキーマに対して SWIFT のフラット ファイル メッセージを解析します。 XML を解析して、フラット ファイルは、フラット ファイルを構造的に正しいことを保証します。 解析も、読み取り、操作、またはその他の形式またはメッセージの種類に変換を簡単に XML を生成します。 データの有効性のスキーマに対して XML を検証しより複雑な評価のビジネス ルール エンジン (BRE) を使用できます。  
  
 SWIFT 逆アセンブラーは、SWIFT 逆アセンブラーによって呼び出される SWIFT のフラット ファイル メッセージを解析する BizTalk フラット ファイル パーサーを呼び出します。 SWIFT 逆アセンブラーでは、エラーのコレクションで、解析時に発生したエラーの詳細を記録、常に最初のパスでできるだけ多くの構造化エラーを収集するために、データの解析を続行しようとします。 ただし、ほとんどの解析エラーは致命的なものし、最初のエラーでメッセージの処理を停止します。  
  
 構造の検証の詳細については、次を参照してください。[スキーマ操作](../../adapters-and-accelerators/accelerator-swift/working-with-schemas.md)します。  
  
## <a name="data-validation-xml-validation"></a>データ検証 (XML の検証)  
 整形式 XML として XSD スキーマの定義に準拠している構造の検証に合格した SWIFT のメッセージを定義することができます。 A4SWIFT では、解析ステージ中に、SWIFT メッセージの構造上有効な XML を生成します。 A4SWIFT の対応する XSD スキーマで定義された制約に対してデータの正確さには、この XML を検証できます。  
  
 これらの制約には、データの型、長さ、および標準の SWIFT に従って定義されている値の範囲が含まれます。 SWIFT 逆アセンブラーは、データ検証を実行するにはリーダーを検証する XML を呼び出します。  
  
 SWIFT 逆アセンブラーは、XML の検証中に発生したエラーの詳細をエラー コレクションに記録し、最初のパスでできるだけ多くの XML 検証エラーを収集する残りのデータの検証を続行します。 (解析とは異なり XML 検証の継続が保証されます。)  
  
 データ検証の詳細については、次を参照してください。[スキーマ操作](../../adapters-and-accelerators/accelerator-swift/working-with-schemas.md)します。  
  
## <a name="swift-network-and-usage-rule-validation-bre-validation"></a>SWIFT ネットワークと使用量ルールの検証 (BRE の検証)  
 A4SWIFT のビジネス ルール エンジン (BRE) ポリシーに対するビジネス レベルの正確性の SWIFT メッセージの構造上有効な XML を検証します。 これらのポリシーには、SWIFT ネットワークと使用状況規則と SWIFT の標準に従って定義されているその他の複雑なクロス フィールド規則の適用が含まれます。 SWIFT 逆アセンブラーは、ビジネス レベルの検証を実行する、BRE を呼び出します。  
  
 SWIFT 逆アセンブラーは、BRE の検証中に発生したエラーの詳細をエラー コレクションに記録し、最初のパスでできるだけ多くの BRE 検証エラーを収集する残りのデータの検証を続行します。 (XML の検証などの BRE 検証の継続が保証されます。)  
  
 SWIFT ネットワークと使用量ルールの検証の詳細については、次を参照してください。[の BRE ポリシーを操作](../../adapters-and-accelerators/accelerator-swift/working-with-bre-policies.md)します。  
  
## <a name="validation-failures-and-message-marking"></a>検証エラーおよびメッセージのマーキング  
 A4SWIFT は検証エラーおよびメッセージの検証の各段階の詳細を収集します。 構造解析、XML の検証、および BRE 検証します。 A4SWIFT できるだけメッセージに関する多くのエラー情報を収集するために、「ベスト エフォート」ヒューリスティックを使用してこれらのエラーを収集します。 この機能は、キャッチされたすべてのエラーが発生し、submit の複数のイテレーションを移動するのではなく、1 つのパスで報告される検証、失敗、修正、再送信に失敗したメッセージを使用します。  
  
 エラーのコレクション内のいずれかの検証段階中に発生した 1 つ以上のエラー メッセージでは、無効と見なされが失敗しました。 A4SWIFT、MessageBox データベースにこれらのメッセージを発行するが、メッセージの検証が失敗したことを示すために昇格させたプロパティと各検証ステージのエラー数をレポートにマークされています。  
  
 だけでなく、昇格されたプロパティは、A4SWIFT は XML にエラーのコレクションをシリアル化し、マルチパート メッセージの「エラー一部」としてコレクションをアタッチします。 最後のメッセージ、失敗したメッセージのボディ部から成るとエラー コレクションの XML では、エラー、およびエラー状態を示す A4SWIFT 昇格させたプロパティを持つが強化されています。 SWIFT 逆アセンブラーは、このマルチパート メッセージをメッセージ ボックス データベースに発行します。  
  
 BizTalk 送信ポートまたはオーケストレーションから取得できます失敗したメッセージ、メッセージ ボックス データベース、特別な昇格 A4SWIFT プロパティをサブスクライブしています。 特定の検証段階からすべての失敗したメッセージまたはエラーの特定数のメッセージだけを取得するサブスクリプションを行うことができます。  
  
 失敗したメッセージが取得された後は、レポート作成アプリケーション、修復アプリケーションまたはプロセス、またはエラーのリポジトリに送信することができます。 または破棄できます。  
  
 この機能に失敗したメッセージ (および、サブスクリプションで失敗の種類を区別) を購読、情報豊富なエラーのコレクションと組み合わせると、失敗した各メッセージにアタッチされている XML フォームの単純なエラーを開発するための強力なフレームワークなど、メッセージの修復が提供する、アプリケーションと A4SWIFT セットアップによってインストールされている新しい送信機能を報告します。  
  
 検証エラーとメッセージ的なマーキングの詳細については、次を参照してください。[メッセージ サブスクリプションの失敗の操作](../../adapters-and-accelerators/accelerator-swift/working-with-failed-message-subscriptions.md)します。  
  
## <a name="see-also"></a>参照  
 [BizTalk Accelerator for SWIFT ランタイム](../../adapters-and-accelerators/accelerator-swift/biztalk-accelerator-for-swift-runtime.md)