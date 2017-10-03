---
title: "BRE ポリシーの扱い |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BRE policies, about BRE policies
- BRE policies
ms.assetid: 4470f2b3-6891-46d7-9ba1-848f90d0767d
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 624af2a9c05e1a419acac66eeb6a1aea8d29d695
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="working-with-bre-policies"></a>BRE ポリシーの扱い
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] SWIFT の検証」の説明に従って、ビジネス ルール エンジン (BRE) を使用してメッセージのポリシー、 *SWIFT リファレンス ガイド*です。 これらのポリシーを以下に示します。  
  
-   書式設定  
  
-   値の範囲  
  
-   有効なリストのエントリ  
  
-   対応するエラー コードを持つネットワーク ルール  
  
-   メッセージ コンテンツから検証可能な使用に関する規則  
  
 これらのポリシーは、メッセージの内容、またはなメッセージのクロス検証に依存していない一般的なプラクティスを含めないでください。  
  
 メッセージ (とヘッダーとトレーラー) の XSD スキーマでは、基本的なフィールドの選択肢と書式設定の参照を SWIFT ベース Types.xsd スキーマを実装するメッセージ スキーマ中に、基数を実装します。 メッセージの種類ごとに 2 つの個別のポリシーは、各メッセージに関連付けられているルールを定義します。  
  
-   マスターのポリシー (MT*xxx*_Master_Policy.xml)  
  
-   検証ポリシー (MT*xxx*_Validation_Policy.xml)  
  
 メッセージの種類ごとに、マスター ポリシーでは、そのメッセージの種類に適用される特定のポリシーを呼び出します。 これらの特定のポリシーには、特別なフィールドは、その共通機能を実装、ネットワーク ルール、および使用状況規則を確認します。 マスターのポリシー メッセージは、最初のポリシー メッセージに対して実行します。 ポリシーの一覧には、メッセージの種類の検証ポリシーが含まれています。 各マスターのポリシーには、コンストラクト「場合は、このメッセージを入力し、実行ポリシーの一覧」です。  
  
 各メッセージの種類の検証ポリシーは、フィールド コードなど、他の外部の規則を実装する単一フィールドのチェックを一覧表示またはフィールドの特定のボキャブラリを使用します。 これら個別のルールは、フィールドに固有であるため 2 つまたは複数のメッセージ全体で一般に共通です。 いないプログラミング コード、BRE ボキャブラリに A4SWIFT_Codelists は許可されているフィールドの値を提供します。  
  
 *SWIFT リファレンス ガイド*ネットワーク ルールの個別に実装します。 各ネットワーク ルールのセットに対応するメッセージの種類、 *SWIFT リファレンス ガイド*を定義します。  
  
 A4SWIFT セットアップでは、A4SWIFT インストールするときの規則はインストールされません。 した後、スキーマを選択し、ビルド アセンブリを展開することができますを使用して BRE 配置ユーティリティを選択し、スキーマ セットの適切なルールを展開します。 選択したメッセージの規則を展開するには、ユーティリティを実行し、関連するアセンブリを選択します。 このツールは、対応するマスター ポリシー、検証ポリシーと、参照先のネットワークまたはその他の規則を選択します。  
  
 A4SWIFT は、A4SWIFT ルールをボキャブラリの 2 種類に関連付けます。 最初のボキャブラリは、さまざまなコード リストの値を含む A4SWIFT_Codelist です。 2 番目のボキャブラリは、A4SWIFT_Functions です。 これらのボキャブラリは[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]ロジックの検証と計算のためのクラスです。  
  
 受信パイプラインで A4SWIFT 逆アセンブラーがルールの呼び出しには、BRE の検証の構成パラメーターを true に設定できます。 オーケストレーションからルールを呼び出すこともできます。 A4SWIFT アセンブラー (ASM) でルールを呼び出すことはできません。 オーケストレーションを使用するか、受信パイプライン、スキーマに対してインスタンスを検証し、ルールを起動する必要があります。  
  
 メッセージには、スキーマの検証またはビジネス ルールのいずれかが失敗すると、A4SWIFT は、検出されたエラーの説明を表すエラーの収集とエラーのフィールドまたはエラーが発生したメッセージ内の位置を示す値を準備します。 詳細については、次を参照してください。[メッセージ サブスクリプションの失敗の操作](../../adapters-and-accelerators/accelerator-swift/working-with-failed-message-subscriptions.md)です。  
  
 A4SWIFT を提供するセットに追加の規則を追加できます。 たとえば、一連のメッセージに影響を与える市場プラクティス グループの規則を採用している場合、マスターを含むポリシーを必要に応じて、1 つまたは複数の新しい検証の新しいバージョンを実装できます。 同様に、単一フィールドの追加のチェックを適用する場合は、メッセージ検証ポリシーの新しいバージョンにこれらのチェックを追加できます。 新しいルール、またはボキャブラリ関数としては、新しい検証を実装することができます。  
  
 このセクションには、次のトピックが含まれています。  
  
-   [銀行識別コードの検証を有効にします。](../../adapters-and-accelerators/accelerator-swift/enabling-validation-of-bank-identifier-codes.md)  
  
-   [A4SWIFT データベース内の Bicplus テーブルを管理します。](../../adapters-and-accelerators/accelerator-swift/managing-the-bicplus-table-in-the-a4swift-database.md)  
  
-   [先行する量フィールドの検証時にゼロをサポートします。](../../adapters-and-accelerators/accelerator-swift/supporting-leading-zeros-in-amount-field-validations.md)  
  
-   [時間検証のためのオフセットを設定します。](../../adapters-and-accelerators/accelerator-swift/setting-offsets-for-amount-validation.md)  
  
-   [使用量ルールの検証を削除します。](../../adapters-and-accelerators/accelerator-swift/removing-usage-rule-validation.md)