---
title: BizTalk エディターのエラー |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BizTalk Editor, error messages
- troubleshooting, BizTalk Editor
- BizTalk Editor, troubleshooting
- troubleshooting, error messages [BizTalk Editor]
- error messages, BizTalk Editor
ms.assetid: d044af11-708a-4365-a105-dd19a2c610a4
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 01ff3ace72d8a08a7d2c2613f44895a54b668529
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358107"
---
# <a name="biztalk-editor-errors"></a>BizTalk エディターのエラー
このセクションでは、BizTalk エディター関連のコンパイル メッセージについての補足情報を提供します。 Microsoft ではタスク一覧 ウィンドウで、関連するメッセージのいずれかを選択、F1 キーを使用してこの情報にアクセスすることができます[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]します。 概念と手順については BizTalk エディターについて、次を参照してください。 [BizTalk エディターを使用してスキーマを作成する](../core/creating-schemas-using-biztalk-editor.md)します。  
  
 次の表では、カテゴリで分類された、警告、エラー、および補足情報の使用可能な BizTalk エディターに関連するその他の情報を示します。  
  
|カテゴリ|メッセージ|  
|--------------|-------------|  
|警告|[ボディ XPath がいない子孫](../core/warning-body-xpath-not-a-descendent.md)<br /><br /> [ボディ XPath が無効です。](../core/warning-body-xpath-not-valid.md)<br /><br /> [識別フィールド XPath が見つかりません](../core/warning-distinguished-field-xpath-not-found.md)<br /><br /> [空のターゲット Namespace](../core/warning-empty-target-namespace.md)<br /><br /> [エンベロープ スキーマには、ルート レコード ノードが必要です。](../core/warning-envelope-schema-needs-root-record-node.md)<br /><br /> [フィールドのデータ型が一致しません](../core/warning-field-data-type-mismatch.md)<br /><br /> [昇格させたフィールド XPath が見つかりませんでした。](../core/warning-promoted-field-xpath-not-found.md)<br /><br /> [レコードのボディ XPath が見つかりません](../core/warning-record-body-xpath-not-found.md)|  
|[エラー]|[SchemaLocation 属性を解決することはできません。](../core/error-cannot-resolve-schemalocation-attribute.md)<br /><br /> [インスタンスの作成エラー](../core/error-create-instance-failure.md)<br /><br /> [識別フィールドの昇格が重複しています](../core/error-duplicate-distinguished-field-promotion.md)<br /><br /> [プロパティ フィールドの昇格が重複しています](../core/error-duplicate-property-field-promotion.md)<br /><br /> [入力インスタンス ファイルが見つかりません](../core/error-input-instance-file-missing.md)<br /><br /> [入力インスタンス ファイルが無効です。](../core/error-input-instance-file-not-valid.md)<br /><br /> [入れ子になったクラスの名前の競合](../core/error-nested-class-name-collision.md)<br /><br /> [ノードの識別フィールドの昇格が無効です。](../core/error-node-not-valid-for-distinguished-field-promotion.md)<br /><br /> [ノード プロパティ フィールドの昇格が無効です。](../core/error-node-not-valid-for-property-field-promotion.md)<br /><br /> [出力インスタンス ファイルが無効です。](../core/error-output-instance-file-not-valid.md)<br /><br /> [昇格させたプロパティ Max Occurs します。](../core/error-promoted-property-max-occurs.md)<br /><br /> [プロパティ フィールドが見つかりません](../core/error-property-field-missing.md)<br /><br /> [プロパティ スキーマ フィールドのデータ型が無効です。](../core/error-property-schema-field-data-type-not-valid.md)<br /><br /> [プロパティ スキーマの構造が無効です。](../core/error-property-schema-structure-not-valid.md)<br /><br /> [ルート ノードのクラス名が無効です。](../core/error-root-node-class-name-not-valid.md)<br /><br /> [ルート ノードの重複するクラス名](../core/error-root-node-duplicate-class-name.md)<br /><br /> [スキーマの依存関係が無効です。](../core/error-schema-dependency-not-valid.md)<br /><br /> [スキーマ ファイルの形式が無効です。](../core/error-schema-file-format-not-valid.md)<br /><br /> [スキーマ ファイル名が無効です。](../core/error-schema-file-name-not-valid.md)<br /><br /> [ビルドではなくスキーマ ファイル](../core/error-schema-file-not-in-build.md)<br /><br /> [スキーマ ルート参照が空です。](../core/error-schema-root-reference-empty.md)<br /><br /> [スキーマ ルート参照が存在しません](../core/error-schema-root-reference-nonexistent.md)<br /><br /> [型名が無効です。](../core/error-type-name-not-valid.md)<br /><br /> [特定できない致命的なエラー](../core/error-unspecified-fatal-error.md)<br /><br /> [インスタンスの検証エラー](../core/error-validate-instance-failure.md)<br /><br /> [スキーマの検証エラー](../core/error-validate-schema-failure.md)|  
|成功|[ネイティブ インスタンスを作成します。](../core/success-create-native-instance.md)<br /><br /> [XML インスタンスを作成します。](../core/success-create-xml-instance.md)<br /><br /> [インスタンスを検証します。](../core/success-validate-instance.md)<br /><br /> [検証のインスタンスには、XML 出力が生成されました。](../core/success-validate-instance-generated-xml-output.md)<br /><br /> [スキーマを検証します。](../core/success-validate-schema.md)|