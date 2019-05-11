---
title: フラット ファイル アセンブラー パイプライン コンポーネントにおける文字エンコーディング |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6b97a92ed1dd842f6b65b49d1c312ffd84eb8dac
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357487"
---
# <a name="character-encoding-in-the-flat-file-assembler-pipeline-component"></a>フラット ファイル アセンブラー パイプライン コンポーネントでの文字エン コード
フラット ファイル アセンブラーでは、ユーザー指定の文字のエンコードでのメッセージを生成できます。 さまざまなレベルで文字エン コードを指定できます。  
  
- **スキーマです。** 設定、**コードページ**ドキュメントのフラット ファイル スキーマのプロパティ。  
  
- **コンポーネント。** 設定、**ターゲット文字セット**パイプライン デザイナーでコンポーネントのプロパティ。  
  
- **メッセージ。** 設定、 **XMLNorm.TargetCharset**メッセージ コンテキストのプロパティ。  
  
  常にメッセージ コンテキストに設定するプロパティの値は、パイプライン デザイナーで 1 つのセットを上書きします。 また、常にパイプライン デザイナーで設定された値として設定された値を上書き、**コードページ**フラット ファイル ドキュメント スキーマ内のプロパティ。  
  
  フラット ファイル アセンブラーでは、次のアルゴリズムを使って、出力メッセージに使用するエンコードを決定します。  
  
- 場合、 **XMLNorm.TargetCharset**コンテキスト プロパティが設定されて、その値がエンコードに使用します。  
  
- の場合、**ターゲット文字セット**パイプライン デザイナーでプロパティを指定すると、その値を使用します。  
  
- の場合、**コードページ**フラット ファイル スキーマのプロパティを指定すると、その値を使用します。  
  
- の場合、 **XMLNorm.SourceCharset**プロパティを指定すると、その値を使用します。  
  
- それ以外の場合、"utf-8"が使用されます。 Utf-8 エンコードを使用する場合、フラット ファイル アセンブラー パイプライン コンポーネントであることに注意してくださいは送信メッセージにバイト オーダー マークを配置できません。  
  
  フラット ファイル アセンブラーでは、BizTalk メッセージ オブジェクトのボディ部のエンコード情報を保存、 **IBaseMessagePart.Charset**プロパティ。  
  
## <a name="see-also"></a>参照  
 [フラット ファイル アセンブラー パイプライン コンポーネント](../core/flat-file-assembler-pipeline-component.md)   
 [フラット ファイル アセンブラー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-flat-file-assembler-pipeline-component.md)   
 [Pipelines-AssemblerDisassembler (BizTalk Server サンプル フォルダー)](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)