---
title: XML 逆アセンブラー パイプライン コンポーネントにおける文字エンコーディング |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IBaseMessagePart.Charset property
- pipeline components, XML Disassembler
- XML Disassembler [pipeline component], character encoding
- XMLNorm.SourceCharset property
ms.assetid: 37962bdc-cbcb-4559-9ae8-6c4be49b4822
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6fee26bdab8566010981e72585358b060009785f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977579"
---
# <a name="character-encoding-in-xml-disassembler-pipeline-component"></a>XML 逆アセンブラー パイプライン コンポーネントでの文字エン コード
XML 逆アセンブラーでは、次のアルゴリズムに基づいて、受信メッセージを処理するためのエンコードを決定します。  
  
1. バイト順マークがデータ内に存在する場合、これによってエンコード情報が決定されます。  
  
2. の場合、 **IBaseMessagePart.Charset**プロパティが設定されて、が指定されてエンコードが使用されます。  
  
3. 上記のいずれにも該当せず、XML ドキュメント内に ANSI を指定する XML 宣言が存在する場合は、その宣言に指定されているエンコードが使用されます。  
  
4. 上記のいずれにも該当しない場合は、UTF-8 エンコードが使用されます。  
  
   メッセージ コンテキストに保存、上記の場合に 2、3、および 4、エンコーディング、XML 逆アセンブラーが決定した後の**XMLNorm.SourceCharset**プロパティ。 XML 逆アセンブラー パイプライン コンポーネントにより生成されるメッセージには、常に UTF-8 エンコードが使用されます。 バイト オーダー マークから取得されたエンコード (上記 1 のケース) は保持されません。  
  
## <a name="see-also"></a>参照  
 [XML 逆アセンブラー パイプライン コンポーネント](../core/xml-disassembler-pipeline-component.md)   
 [XML 逆アセンブラー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-xml-disassembler-pipeline-component.md)