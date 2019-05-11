---
title: XML アセンブラー パイプライン コンポーネントにおける文字エンコーディング |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IBaseMessagePart.Charset property
- XMLNorm.SourceCharset property
- pipeline components, XML Assembler
- XMLNorm.TargetCharset property
- Target Charset property
- XML Assembler [pipeline component], character encoding
ms.assetid: c031fbbf-f00f-41ba-8ac9-cec7d625cef6
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1e01bbf7224da9abda8700721c1de3dd7efefb8f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357477"
---
# <a name="character-encoding-in-the-xml-assembler-pipeline-component"></a>XML アセンブラー パイプライン コンポーネントでの文字エン コード
XML アセンブラー パイプライン コンポーネントは、次の表に示すように、ユーザー指定の文字の 2 つの方法でのエンコードでメッセージを生成できます。  
  
|エンコード レベル|エンコード方式|  
|--------------------|---------------------|  
|コンポーネント|設定、**ターゲット文字セット**パイプライン デザイナーでコンポーネントのプロパティ。|  
|メッセージ|設定、 **XMLNorm.TargetCharset**メッセージ コンテキストのプロパティ。 **注:** メッセージ コンテキスト プロパティは、常にパイプライン デザイナーで設定されたコンテキスト プロパティをオーバーライドします。|  
  
 XML アセンブラーでは、次のアルゴリズムを使って、出力メッセージのエンコードを決定します。  
  
1. 場合、 **XMLNorm.TargetCharset**コンテキスト プロパティが設定されて、その値が使用されます。  
  
2. の場合、**ターゲット文字セット**その値が使用されるパイプライン デザイナーでプロパティを指定します。  
  
3. の場合、 **XMLNorm.SourceCharset**プロパティを指定すると、その値を使用します。  
  
4. 前のプロパティを設定すると、utf-8 エンコードが使用されます。  
  
   XML アセンブラーでは、BizTalk メッセージ オブジェクトのエンコード情報を保存する、`IBaseMessagePart.Charset`プロパティ。 Unicode または utf-8 エンコードを使用する場合、XML アセンブラーは常に、バイト順マーク (BOM) を送信メッセージに追加します。  
  
   される XML 送信パイプラインで、XML アセンブラー コンポーネントが含まれている既定値を使用する場合、生成されるドキュメント可能性がありますエンコードされるとき、サーバーへの送信またはドキュメントが作成された場合は、utf-8 を使用してエンコードされますとして同じ文字セットを使用して、サーバー内で、 **XMLNorm.TargetCharset**が指定されていません。  
  
## <a name="see-also"></a>参照  
 [XML アセンブラー パイプライン コンポーネント](../core/xml-assembler-pipeline-component.md)   
 [XML アセンブラー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-xml-assembler-pipeline-component.md)   
 [Pipelines-AssemblerDisassembler (BizTalk Server サンプル フォルダー)](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)