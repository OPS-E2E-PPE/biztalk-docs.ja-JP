---
title: "フラット ファイル アセンブラー パイプライン コンポーネントでの文字エン コード |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Flat File Assembler [pipeline component], character encoding
- IBaseMessagePart.Charset property
- pipeline components, Flat File Assembler
- Codepage property
- XMLNorm.SourceCharset property
- XMLNorm.TargetCharset property
- Target Charset property
ms.assetid: 0cf3c0fd-f036-4190-83ce-9064ef4e823c
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: af38855c81129cd4bafff50544f2aee15e6f3fab
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="character-encoding-in-the-flat-file-assembler-pipeline-component"></a>フラット ファイル アセンブラー パイプライン コンポーネントでの文字エン コード
フラット ファイル アセンブラーを使用すると、ユーザーが指定する文字エンコードでメッセージを生成できます。 文字エンコードは複数のレベルで指定できます。  
  
-   **スキーマです。** 設定、**コードページ**ドキュメントのフラット ファイル スキーマのプロパティです。  
  
-   **コンポーネント。** 設定、**表せない**パイプライン デザイナーでコンポーネントのプロパティです。  
  
-   **メッセージ。** 設定、 **XMLNorm.TargetCharset**メッセージ コンテキストのプロパティです。  
  
 メッセージ コンテキストに設定されたプロパティ値は、パイプライン デザイナーで設定されたプロパティ値よりも常に優先されます。 また、常にパイプライン デザイナーで設定された値として設定された値を上書き、**コードページ**フラット ファイル ドキュメント スキーマ内のプロパティです。  
  
 フラット ファイル アセンブラーでは、次のアルゴリズムに基づいて、出力メッセージのエンコードに使用する文字セットを決定します。  
  
-   場合、 **XMLNorm.TargetCharset**コンテキスト プロパティが設定されて、その値はエンコードするために使用します。  
  
-   それ以外の場合、**表せない**パイプライン デザイナーでプロパティを指定すると、その値を使用します。  
  
-   それ以外の場合、**コードページ**フラット ファイル スキーマのプロパティを指定すると、その値を使用します。  
  
-   それ以外の場合、 **XMLNorm.SourceCharset**プロパティを指定すると、その値を使用します。  
  
-   上記のいずれにも該当しない場合は、"UTF-8" が使用されます。 UTF-8 エンコードを使用する場合、フラット ファイル アセンブラー パイプライン コンポーネントでは、送信メッセージにバイト順マークが付加されないことに注意してください。  
  
 フラット ファイル アセンブラーでは、BizTalk メッセージ オブジェクトのボディ部のエンコード情報を保存、 **IBaseMessagePart.Charset**プロパティです。  
  
## <a name="see-also"></a>参照  
 [フラット ファイル アセンブラー パイプライン コンポーネント](../core/flat-file-assembler-pipeline-component.md)   
 [フラット ファイル アセンブラー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-flat-file-assembler-pipeline-component.md)   
 [パイプライン AssemblerDisassembler (BizTalk Server Samples フォルダ)](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)