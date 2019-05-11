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
ms.openlocfilehash: d299ac6a1261160cbd3844c3f0201e55affa5655
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391673"
---
# <a name="character-encoding-in-xml-disassembler-pipeline-component"></a>XML 逆アセンブラー パイプライン コンポーネントでの文字エン コード
XML 逆アセンブラーは、受信メッセージを処理するために使用するのにエンコードを決定するのに、次のアルゴリズムを使用します。  
  
1. データのバイト順マークが存在する場合、そこからはエンコード情報が判断されます。  
  
2. の場合、 **IBaseMessagePart.Charset**プロパティが設定されて、が指定されてエンコードが使用されます。  
  
3. それ以外の場合、XML 宣言が XML ドキュメント内にある場合が指定されてエンコードされる、指定された XML 宣言が ANSI。  
  
4. それ以外の場合、utf-8 エンコードが使用されます。  
  
   メッセージ コンテキストに保存、上記の場合に 2、3、および 4、エンコーディング、XML 逆アセンブラーが決定した後の**XMLNorm.SourceCharset**プロパティ。 常に、XML 逆アセンブラー パイプライン コンポーネントによって生成されたメッセージは、utf-8 エンコードを使用します。 1 の場合、バイト オーダー マークから取得されたエンコードは保持されません。  
  
## <a name="see-also"></a>参照  
 [XML 逆アセンブラー パイプライン コンポーネント](../core/xml-disassembler-pipeline-component.md)   
 [XML 逆アセンブラー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-xml-disassembler-pipeline-component.md)