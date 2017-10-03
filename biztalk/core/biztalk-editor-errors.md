---
title: "BizTalk エディター エラー |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BizTalk Editor, error messages
- troubleshooting, BizTalk Editor
- BizTalk Editor, troubleshooting
- troubleshooting, error messages [BizTalk Editor]
- error messages, BizTalk Editor
ms.assetid: d044af11-708a-4365-a105-dd19a2c610a4
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a6a74490561c3ecb31cef956b73892449b629de5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="biztalk-editor-errors"></a>BizTalk エディター エラー
ここでは、BizTalk エディター関連のコンパイル メッセージについての補足情報を提供します。 この情報にアクセスするには、Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] のタスク一覧ウィンドウで、関連するメッセージの 1 つを選択して F1 キーを押します。 概念と手順については BizTalk エディターについて、次を参照してください。 [BizTalk エディターを使用してスキーマを作成する](../core/creating-schemas-using-biztalk-editor.md)です。  
  
 次の表に、補足情報のある BizTalk エディターに関連する警告、エラー、およびその他の情報を種類別に記載します。  
  
|カテゴリ|メッセージ|  
|--------------|-------------|  
|警告|[ボディ XPath が子孫ではありません。](../core/warning-body-xpath-not-a-descendent.md)<br /><br /> [ボディ XPath が無効です。](../core/warning-body-xpath-not-valid.md)<br /><br /> [識別フィールド XPath が見つかりません](../core/warning-distinguished-field-xpath-not-found.md)<br /><br /> [空のターゲット Namespace](../core/warning-empty-target-namespace.md)<br /><br /> [エンベロープ スキーマには、ルート レコード ノードが必要です。](../core/warning-envelope-schema-needs-root-record-node.md)<br /><br /> [フィールド データ型が一致しません](../core/warning-field-data-type-mismatch.md)<br /><br /> [昇格させたフィールド XPath が見つかりません。](../core/warning-promoted-field-xpath-not-found.md)<br /><br /> [レコードのボディ XPath が見つかりません](../core/warning-record-body-xpath-not-found.md)|  
|[エラー]|[SchemaLocation 属性を解決できません。](../core/error-cannot-resolve-schemalocation-attribute.md)<br /><br /> [インスタンスの作成エラー](../core/error-create-instance-failure.md)<br /><br /> [識別フィールドの昇格を複製します。](../core/error-duplicate-distinguished-field-promotion.md)<br /><br /> [プロパティ フィールドの昇格を複製します。](../core/error-duplicate-property-field-promotion.md)<br /><br /> [入力インスタンス ファイルが見つかりません](../core/error-input-instance-file-missing.md)<br /><br /> [入力インスタンス ファイルが有効ではありません。](../core/error-input-instance-file-not-valid.md)<br /><br /> [入れ子になったクラス名の競合](../core/error-nested-class-name-collision.md)<br /><br /> [ノードの識別フィールドの昇格では無効です。](../core/error-node-not-valid-for-distinguished-field-promotion.md)<br /><br /> [ノードのプロパティ フィールドの昇格では無効です。](../core/error-node-not-valid-for-property-field-promotion.md)<br /><br /> [出力インスタンス ファイルが有効ではありません。](../core/error-output-instance-file-not-valid.md)<br /><br /> [昇格させたプロパティ Max Occurs します。](../core/error-promoted-property-max-occurs.md)<br /><br /> [プロパティ フィールドが見つかりません](../core/error-property-field-missing.md)<br /><br /> [プロパティ スキーマ フィールドのデータ型が有効ではありません。](../core/error-property-schema-field-data-type-not-valid.md)<br /><br /> [プロパティ スキーマの構造が無効です。](../core/error-property-schema-structure-not-valid.md)<br /><br /> [ルート ノードのクラス名が有効ではありません。](../core/error-root-node-class-name-not-valid.md)<br /><br /> [ルート ノードの重複するクラス名](../core/error-root-node-duplicate-class-name.md)<br /><br /> [スキーマの依存関係が有効ではありません。](../core/error-schema-dependency-not-valid.md)<br /><br /> [スキーマ ファイルの形式が有効ではありません。](../core/error-schema-file-format-not-valid.md)<br /><br /> [スキーマ ファイル名が有効ではありません。](../core/error-schema-file-name-not-valid.md)<br /><br /> [ビルド内にありませんスキーマ ファイル](../core/error-schema-file-not-in-build.md)<br /><br /> [スキーマ ルート参照が空です。](../core/error-schema-root-reference-empty.md)<br /><br /> [スキーマ ルート参照が存在しません](../core/error-schema-root-reference-nonexistent.md)<br /><br /> [型名が無効](../core/error-type-name-not-valid.md)<br /><br /> [特定できない致命的なエラー](../core/error-unspecified-fatal-error.md)<br /><br /> [インスタンスの検証エラー](../core/error-validate-instance-failure.md)<br /><br /> [スキーマの検証エラー](../core/error-validate-schema-failure.md)|  
|Success|[ネイティブ インスタンスを作成します。](../core/success-create-native-instance.md)<br /><br /> [XML インスタンスを作成します。](../core/success-create-xml-instance.md)<br /><br /> [インスタンスを検証します。](../core/success-validate-instance.md)<br /><br /> [検証のインスタンスには、XML 出力が生成されます。](../core/success-validate-instance-generated-xml-output.md)<br /><br /> [スキーマを検証します。](../core/success-validate-schema.md)|