---
title: 文字のエスケープ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3af800b9-d31b-487a-9a06-6eda47d1574e
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5f6f1ff202c1ffa96bc696415ab7ec1024ae57e9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970651"
---
# <a name="escape-characters"></a>エスケープ文字

## <a name="overview"></a>概要
エスケープ文字とは、特殊な意味を持つ文字の前に置くことによって、その意味を無効化させることのできる単一の文字のことです。 たとえば、次のような特性を持つフラット ファイル レコードを定義したとします。  
  
- 名前 = Record1  
  
- [区切り記号]  
  
- 子区切り記号 = コンマ (,)  
  
- 子の順序 = 接頭辞  
  
- エスケープ文字 = 円記号 (\\)  
  
- タグ = RECORD1  
  
- 2 つのフィールド (Field1 および Field2)  
  
  今度は、このレコードに次のようなフラット ファイル データを適用したとします。  
  
```  
RECORD1,testfield1\,testfield1,testfield2  
                  ^^  
  
```  
  
 このデータは、次のような XML に逆アセンブルされます。  
  
```  
<Record1>  
    <Field1>testfield1,testfield1</Field1>  
    <Field2>testfield2</Field2>  
</Record1>  
  
```  
  
 変換後の XML レコードを見ると、フラット ファイル レコードに続く行で、エスケープ文字の指定された部分 (`\,`) が単一のコンマ文字に変換され、エスケープ文字は Field1 のデータに現れない点に注目してください。 また、他の 2 つのコンマとは異なり、コンマ文字はフィールド区切り記号としては解釈されません。  
  
 フラット ファイル アセンブラーが逆の操作を実行 (つまり、XML 形式のレコードを対応するフラット ファイル レコードに変換) した後の Field1 には、コンマの前に、そのデータがフィールド区切り記号ではないことを示すエスケープ文字が挿入されます。  
  
 BizTalk エディターを使用してフラット ファイル スキーマを作成するときに使用して、スキーマ全体の既定のエスケープ文字を定義することができます、**既定のエスケープ文字**と**既定のエスケープ文字の種類**プロパティ**スキーマ**ノード。 次に、この既定のエスケープ文字またはを使用して、カスタム レコードに固有のエスケープ文字を使用するか、スキーマで個々 のレコードを構成、**エスケープ文字]** と**エスケープ文字の種類**のプロパティ、**レコード**ノード。  
  
## <a name="see-also"></a>参照  
- [特殊文字をフィールド値の一部として解釈させる方法](../core/ways-to-interpret-special-characters-as-part-of-a-field-value.md)  
- エスケープ文字プロパティ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]:  
    - 既定のエスケープ文字 (フラット ファイル スキーマのノード プロパティ)
    - 既定のエスケープ文字の種類 (フラット ファイル スキーマのノード プロパティ)
    - エスケープ文字 (フラット ファイル スキーマのノード プロパティ)  
    - エスケープ文字の種類 (フラット ファイル スキーマのノード プロパティ)