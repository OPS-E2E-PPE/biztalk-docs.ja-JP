---
title: BizTalk マッパー エラー |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.intro
helpviewer_keywords:
- troubleshooting, BizTalk Mapper
- BizTalk Mapper, troubleshooting
- troubleshooting, error messages [BizTalk Mapper]
- error messages, BizTalk Mapper
- BizTalk Mapper, error messages
ms.assetid: 6aefa7ca-56ba-4c3f-aae6-6d98d891079c
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 51721ea47beef364df8313914ef7ab8dafebf19c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22234082"
---
# <a name="biztalk-mapper-errors"></a>BizTalk マッパーのエラー
ここでは、BizTalk マッパー関連のコンパイル メッセージについての補足情報を提供します。 この情報にアクセスするには、Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] のタスク一覧ウィンドウで、関連するメッセージの 1 つを選択して F1 キーを押します。 BizTalk マッパーの概念と手順については、次を参照してください。 [BizTalk マッパーを使用してマップを作成する](../core/creating-maps-using-biztalk-mapper.md)です。  
  
 次の表に、補足情報のある BizTalk マッパーに関連する警告、エラー、およびその他の情報を種類別に記載します。  
  
|カテゴリ|メッセージ|  
|--------------|-------------|  
|警告|[カスタム拡張 XML がないカスタム xslt は上書き](../core/warning-custom-extension-xml-but-no-custom-xslt.md)<br /><br /> [カスタム XSLT はカスタム拡張 XML は上書きされません。](../core/warning-custom-xslt-but-no-custom-extension-xml.md)<br /><br /> [インライン スクリプト](../core/warning-inline-script.md)<br /><br /> [カスタム XSLT およびカスタム拡張 XML を使用します。](../core/warning-using-custom-xslt-and-extension-xml.md)|  
|[エラー]|[一括コピー Functoid の子では、コードを生成します。](../core/error-children-of-mass-copy-functoid-generate-code.md)<br /><br /> [XSLT スクリプト Functoid の子では、コードを生成します。](../core/error-children-of-xslt-scripting-functoid-generate-code.md)<br /><br /> [複数の Choice 子が生成されました](../core/error-could-generate-multiple-choice-children.md)<br /><br /> [複数の同レベルの子を生成する可能性があります。](../core/error-could-generate-multiple-equivalent-children.md)<br /><br /> [例外がキャッチされました](../core/error-exception-caught.md)<br /><br /> [スクリプト Functoid の外部アセンブリを呼び出すことができません。](../core/error-external-assembly-for-scripting-functoid-cannot-be-invoked.md)<br /><br /> [拡張 XML ファイルの書き込みに失敗しました](../core/error-failed-write-extension-xml-file.md)<br /><br /> [XML へのネイティブな書き込みに失敗しました](../core/error-failed-write-native-to-xml.md)<br /><br /> [XSLT ファイルを書き込めませんでした。](../core/error-failed-write-xslt-file.md)<br /><br /> [有効でないインデックス Functoid への最初の入力](../core/error-first-input-to-index-functoid-not-valid.md)<br /><br /> [有効でないテーブル抽出 Functoid への最初の入力](../core/error-first-input-to-table-extractor-functoid-not-valid.md)<br /><br /> [最初の入力をテーブル ループ Functoid は無効です。](../core/error-first-input-to-table-looping-functoid-not-valid.md)<br /><br /> [値抽出 Functoid が有効でないへの最初の入力](../core/error-first-input-to-value-extractor-functoid-not-valid.md)<br /><br /> [Functoid の固定入力が一致しません](../core/error-functoid-fixed-input-mismatch.md)<br /><br /> [Functoid に入力がありません。](../core/error-functoid-has-no-input.md)<br /><br /> [Functoid の出力がありません。](../core/error-functoid-has-no-output.md)<br /><br /> [Functoid 変数の入力が一致しません](../core/error-functoid-variable-input-mismatch.md)<br /><br /> [汎用は、XML インスタンスを生成します。](../core/error-generic-generate-xml-instance.md)<br /><br /> [汎用入力の検証](../core/error-generic-input-validation.md)<br /><br /> [ネイティブ解析のジェネリック](../core/error-generic-native-parsing.md)<br /><br /> [ジェネリックのネイティブ シリアル化](../core/error-generic-native-serialization.md)<br /><br /> [汎用の出力の検証](../core/error-generic-output-validation.md)<br /><br /> [インデックス Functoid に負のインデックス](../core/error-index-functoid-has-negative-index.md)<br /><br /> [インデックス Functoid にインデックスがありません。](../core/error-index-functoid-has-no-index.md)<br /><br /> [インデックス Functoid にインデックスが多すぎます](../core/error-index-functoid-has-too-many-indexes.md)<br /><br /> [インライン スクリプト](../core/error-inline-script.md)<br /><br /> [スクリプト Functoid が有効でない XSLT 呼び出しテンプレートの入力数](../core/error-input-count-for-xslt-call-template-scripting-functoid-not-valid.md)<br /><br /> [入力ファイルが存在しません](../core/error-input-file-does-not-exist.md)<br /><br /> [有効でない一括コピー Functoid の入力](../core/error-input-for-mass-copy-functoid-not-valid.md)<br /><br /> [テーブル ループ Functoid が無効の入力パラメーター数](../core/error-input-parameter-count-for-table-looping-functoid-not-valid.md)<br /><br /> [入力の検証](../core/error-input-validation.md)<br /><br /> [異なる親レコードから累積 Functoid への入力](../core/error-inputs-to-cumulative-functoid-from-different-parent-records.md)<br /><br /> [リンク オプション競合しています](../core/error-link-option-conflict.md)<br /><br /> [マップを移行する必要があります。](../core/error-map-needs-to-be-migrated.md)<br /><br /> [マップにリンクまたは定数](../core/error-map-without-any-links-or-constants.md)<br /><br /> [複数のノードと等しい同じ対象します。](../core/error-multiple-equivalent-node-same-target.md)<br /><br /> [ループしない入力が複数あります。](../core/error-multiple-inputs-without-looping.md)<br /><br /> [複数のループ パス](../core/error-multiple-loop-paths.md)<br /><br /> [ネイティブの入力ファイルが存在しません](../core/error-native-input-file-does-not-exist.md)<br /><br /> [ネイティブ解析](../core/error-native-parsing.md)<br /><br /> [ネイティブ シリアル化](../core/error-native-serialization.md)<br /><br /> [スクリプト Functoid のアセンブリが存在しません](../core/error-no-assembly-for-scripting-functoid.md)<br /><br /> [スクリプト Functoid のクラスが存在しません](../core/error-no-class-for-scripting-functoid.md)<br /><br /> [スクリプト Functoid のメソッドが存在しません](../core/error-no-method-for-scripting-functoid.md)<br /><br /> [スクリプト Functoid のスクリプトの種類はありません。](../core/error-no-script-type-for-scripting-functoid.md)<br /><br /> [XSLT スクリプト Functoid が無効の出力リンク](../core/error-output-link-for-xslt-scripting-functoid-not-valid.md)<br /><br /> [出力検証](../core/error-output-validation.md)<br /><br /> [必須フィールドに入力がありません。](../core/error-required-field-has-no-input.md)<br /><br /> [必須ターゲットに選択ノードのソースがあります。](../core/error-required-target-has-choice-node-source.md)<br /><br /> [必須ターゲットに省略可能なソース](../core/error-required-target-with-optional-source.md)<br /><br /> [有効でないテーブル抽出 Functoid への 2 番目の入力](../core/error-second-input-for-table-extractor-functoid-not-valid.md)<br /><br /> [テーブル ループ Functoid が無効の 2 番目の入力](../core/error-second-input-for-table-looping-functoid-not-valid.md)<br /><br /> [有効でない累積 Functoid への 2 番目の入力](../core/error-second-input-to-cumulative-functoid-not-valid.md)<br /><br /> [テーブル ループ データが有効ではありません。](../core/error-table-looping-data-not-valid.md)<br /><br /> [テーブル ループ Functoid に送信先スキーマへのリンクがありません。](../core/error-table-looping-functoid-without-link-to-destination-schema.md)<br /><br /> [マップのテスト エラー](../core/error-test-map-failure.md)<br /><br /> [マップのテスト用の入力が有効ではありません。](../core/error-test-map-inputs-not-valid.md)<br /><br /> [Database Lookup Functoid Must の 3 番目と 4 番目のパラメーターは定数にします。](../core/third-and-fourth-parameters-of-the-database-lookup-functoid-must-be-constants.md)<br /><br /> [ノードへのデータ入力が多すぎます](../core/error-too-many-data-inputs-to-node.md)<br /><br /> [ノードの論理入力が多すぎます](../core/error-too-many-logical-inputs-to-node.md)<br /><br /> [参照されていない送信先スキーマ](../core/error-unreferenced-destination-schema.md)<br /><br /> [送信元スキーマ](../core/error-unreferenced-source-schema.md)<br /><br /> [XML 入力ファイルが存在しません](../core/error-xml-input-file-does-not-exist.md)<br /><br /> [XSL 変換エラー](../core/error-xsl-transformation-failure.md)|  
|情報および成功|[XSLT ファイルの表示](../core/information-display-xslt-file.md)<br /><br /> [拡張 XML ファイルの表示](../core/information-display-extension-xml-file.md)<br /><br /> [カスタム拡張 XML の使用](../core/information-using-custom-extension-xml.md)<br /><br /> [マップのテスト](../core/success-test-map.md)|