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
ms.openlocfilehash: e5d06842eab0def7846ab31419ce2feb0aeb2cd1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000875"
---
# <a name="character-encoding-in-the-xml-assembler-pipeline-component"></a>XML アセンブラー パイプライン コンポーネントでの文字エン コード
XML アセンブラー パイプライン コンポーネントでは、ユーザー指定の文字エンコード方法に基づいてメッセージを生成します。指定できるエンコード方法は、次の表に示す 2 つの方法があります。  
  
|エンコード レベル|エンコード方法|  
|--------------------|---------------------|  
|コンポーネント|設定、**ターゲット文字セット**パイプライン デザイナーでコンポーネントのプロパティ。|  
|メッセージ|設定、 **XMLNorm.TargetCharset**メッセージ コンテキストのプロパティ。 **注:** メッセージ コンテキスト プロパティは常にパイプライン デザイナーで設定されたコンテキスト プロパティをオーバーライドします。|  
  
 XML アセンブラーでは、次のアルゴリズムに基づいて、出力メッセージのエンコードを決定します。  
  
1. 場合、 **XMLNorm.TargetCharset**コンテキスト プロパティが設定されて、その値が使用されます。  
  
2. の場合、**ターゲット文字セット**その値が使用されるパイプライン デザイナーでプロパティを指定します。  
  
3. の場合、 **XMLNorm.SourceCharset**プロパティを指定すると、その値を使用します。  
  
4. 上記のいずれのプロパティも設定されていなかった場合は、UTF-8 エンコードが使用されます。  
  
   XML アセンブラーでは、BizTalk メッセージ オブジェクトのエンコード情報を保存する、`IBaseMessagePart.Charset`プロパティ。 Unicode または UTF-8 エンコードを使用する場合、送信メッセージには常にバイト オーダー マーク (BOM) が追加されます。  
  
   される XML 送信パイプラインで、XML アセンブラー コンポーネントが含まれている既定値を使用する場合、生成されるドキュメント可能性がありますエンコードされるとき、サーバーへの送信またはドキュメントが作成された場合は、utf-8 を使用してエンコードされますとして同じ文字セットを使用して、サーバー内で、 **XMLNorm.TargetCharset**が指定されていません。  
  
## <a name="see-also"></a>参照  
 [XML アセンブラー パイプライン コンポーネント](../core/xml-assembler-pipeline-component.md)   
 [XML アセンブラー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-xml-assembler-pipeline-component.md)   
 [Pipelines-AssemblerDisassembler (BizTalk Server サンプル フォルダー)](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)