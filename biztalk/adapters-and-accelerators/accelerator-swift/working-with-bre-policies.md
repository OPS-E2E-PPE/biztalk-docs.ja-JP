---
title: BRE ポリシーの操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BRE policies, about BRE policies
- BRE policies
ms.assetid: 4470f2b3-6891-46d7-9ba1-848f90d0767d
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bdb05d6f11d0d4d4f4ef5fd990d05c51b5e0df64
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968955"
---
# <a name="working-with-bre-policies"></a>BRE ポリシーの操作
Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] SWIFT の検証」の説明に従って、ビジネス ルール エンジン (BRE) を使用してメッセージをポリシー、 *SWIFT リファレンス ガイド*します。 これらのポリシーを以下に示します。  

- 書式設定  

- 値の範囲  

- 有効なリストのエントリ  

- 対応するエラー コードとのネットワーク ルール  

- メッセージのコンテンツから検証可能な使用に関する規則  

  これらのポリシーは、メッセージの内容、または、メッセージのクロス検証に依存しない一般的なプラクティスを含めないでください。  

  メッセージ (とヘッダーおよびトレーラー) の XSD スキーマでは、基本的なフィールドの選択肢と SWIFT ベース Types.xsd スキーマの書式設定の参照を実装するメッセージ スキーマの中に、カーディナリティを実装します。 メッセージの種類ごとの 2 つの特定のポリシーは、各メッセージに関連付けられた規則を定義します。  

- マスターのポリシー (MT*xxx*_Master_Policy.xml)  

- 検証ポリシー (MT*xxx*_Validation_Policy.xml)  

  メッセージの種類ごとに、マスタ ポリシーは、そのメッセージの種類に適用される特定のポリシーを呼び出します。 これらの特定のポリシーには、特別なフィールドは、その一般的な関数の実装、ネットワーク ルール、および使用に関する規則を確認します。 メッセージのマスター ポリシーは、最初にそのメッセージの実行ポリシーです。 ポリシーの一覧には、メッセージの種類の検証ポリシーが含まれています。 各マスター ポリシーが、コンス トラクター「場合、このメッセージを入力し、実行ポリシーの一覧」です。  

  メッセージの種類ごとの検証ポリシーでは、フィールドのコードなど、他の外部のルールを実装する単一フィールドのチェックを一覧表示またはフィールドの特定の語彙を使用します。 フィールドに固有であるために、これら個々 のルールは一般に、2 つ以上のメッセージに共通です。 いないプログラミング コード、BRE のボキャブラリで A4SWIFT_Codelists は許可されているフィールドの値を提供します。  

  *SWIFT リファレンス ガイド*ネットワーク ルールの個別に実装します。 各ネットワーク規則のセットに対応するメッセージの種類、 *SWIFT リファレンス ガイド*を定義します。  

  A4SWIFT セットアップでは、A4SWIFT インストールするときの規則はインストールされません。 後、構築、スキーマを選択して、アセンブリをデプロイ、使えば BRE 配置ユーティリティを選択し、スキーマ セットの適切なルールを展開できます。 選択したメッセージの規則を展開するには、ユーティリティを実行し、関連するアセンブリを選択します。 このツールは、対応するマスター ポリシー、検証ポリシー、および任意の参照先のネットワークまたは他のルールを選択します。  

  A4SWIFT は、A4SWIFT ルールをボキャブラリの 2 つの種類を関連付けます。 最初のボキャブラリは、A4SWIFT_Codelist で、さまざまなコード リストの値が含まれています。 2 番目のボキャブラリは、A4SWIFT_Functions です。 これらのボキャブラリは[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]計算やロジックの検証の対象のクラス。  

  BRE の検証の構成パラメーターを true に設定して、受信パイプラインで A4SWIFT 逆アセンブラーがルールを呼び出すことができます。 オーケストレーションからルールを呼び出すこともできます。 A4SWIFT アセンブラー (ASM) でルールを呼び出すことはできません。 オーケストレーションを使用して、または、受信パイプラインをスキーマに対してインスタンスを検証し、規則を実行する必要があります。  

  メッセージには、スキーマの検証またはビジネス ルールのいずれかが失敗した場合、A4SWIFT は見つかったエラーの説明を含むエラーの収集とエラーにフィールドまたはエラーが発生したメッセージ内の位置を示す値を準備します。 詳細については、[メッセージ サブスクリプションの失敗の操作](../../adapters-and-accelerators/accelerator-swift/working-with-failed-message-subscriptions.md)を参照してください。  

  A4SWIFT を提供するセットには、追加の規則を追加できます。 たとえば、一連のメッセージに影響を与える市場プラクティス グループの規則を採用する場合は、必要に応じて、1 つまたは複数の新しい検証を含むマスター ポリシーの新しいバージョンを実装できます。 同様に、単一フィールドの追加チェックを適用する場合は、メッセージの検証ポリシーの新しいバージョンにこれらのチェックを追加できます。 新しいルールやボキャブラリ関数としては、新しい検証を実装することができます。  

  このセクションには、次のトピックが含まれています。  

- [銀行識別コードの検証の有効化](../../adapters-and-accelerators/accelerator-swift/enabling-validation-of-bank-identifier-codes.md)  

- [A4SWIFT データベース内の Bicplus テーブルを管理する](../../adapters-and-accelerators/accelerator-swift/managing-the-bicplus-table-in-the-a4swift-database.md)  

- [数値フィールドの検証時に先頭のゼロをサポートする](../../adapters-and-accelerators/accelerator-swift/supporting-leading-zeros-in-amount-field-validations.md)  

- [数値検証のオフセットを設定する](../../adapters-and-accelerators/accelerator-swift/setting-offsets-for-amount-validation.md)  

- [使用規則の検証の削除](../../adapters-and-accelerators/accelerator-swift/removing-usage-rule-validation.md)
