---
title: XML 逆アセンブラー パイプライン コンポーネントにおける文字エンコーディング |Microsoft ドキュメント
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
ms.openlocfilehash: 2b0e307f2f608cde266e7a566fb3005bde048c31
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22231666"
---
# <a name="character-encoding-in-xml-disassembler-pipeline-component"></a>XML 逆アセンブラー パイプライン コンポーネントでの文字エン コード
XML 逆アセンブラーでは、次のアルゴリズムに基づいて、受信メッセージを処理するためのエンコードを決定します。  
  
1.  バイト順マークがデータ内に存在する場合、これによってエンコード情報が決定されます。  
  
2.  それ以外の場合、 **IBaseMessagePart.Charset**プロパティが設定されてがあります指定されたエンコーディングを使用します。  
  
3.  上記のいずれにも該当せず、XML ドキュメント内に ANSI を指定する XML 宣言が存在する場合は、その宣言に指定されているエンコードが使用されます。  
  
4.  上記のいずれにも該当しない場合は、UTF-8 エンコードが使用されます。  
  
 メッセージ コンテキストに保存前、場合によっては 2、3、および 4 では、XML 逆アセンブラーは、エンコーディングを決定した後の**XMLNorm.SourceCharset**プロパティです。 XML 逆アセンブラー パイプライン コンポーネントにより生成されるメッセージには、常に UTF-8 エンコードが使用されます。 バイト オーダー マークから取得されたエンコード (上記 1 のケース) は保持されません。  
  
## <a name="see-also"></a>参照  
 [XML 逆アセンブラー パイプライン コンポーネント](../core/xml-disassembler-pipeline-component.md)   
 [XML 逆アセンブラー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-xml-disassembler-pipeline-component.md)