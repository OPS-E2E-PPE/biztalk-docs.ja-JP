---
title: エスケープ文字 |Microsoft ドキュメント
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
ms.openlocfilehash: 7e961a205b77a9944a497d6e6cbed0df71f63e03
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246130"
---
# <a name="escape-characters"></a>エスケープ文字

## <a name="overview"></a>概要
エスケープ文字とは、特殊な意味を持つ文字の前に置くことによって、その意味を無効化させることのできる単一の文字のことです。 たとえば、次のような特性を持つフラット ファイル レコードを定義したとします。  
  
-   名前 = Record1  
  
-   [区切り記号]  
  
-   子区切り記号 = コンマ (,)  
  
-   子の順序 = 接頭辞  
  
-   エスケープ文字 = 円記号 (\\)  
  
-   タグ = RECORD1  
  
-   2 つのフィールド (Field1 および Field2)  
  
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
  
 BizTalk エディターを使用してフラット ファイル スキーマを作成するときにを使用して、スキーマ全体に対する既定のエスケープ文字を定義することができます、**既定のエスケープ文字**と**既定のエスケープ文字の種類**プロパティ**スキーマ**ノード。 次に、この既定のエスケープ文字またはカスタムのレコードに固有のエスケープ文字を使用して、使用するスキーマで個々 のレコードを構成できる、**エスケープ文字]** と**エスケープ文字の種類**のプロパティ、**レコード**ノード。  
  
## <a name="see-also"></a>参照  
- [フィールドの値の一部として特殊文字を解釈する方法](../core/ways-to-interpret-special-characters-as-part-of-a-field-value.md)  
- エスケープ文字プロパティ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]:  
    - 既定のエスケープ文字 (フラット ファイル スキーマのノード プロパティ)
    - 既定のエスケープ文字の種類 (フラット ファイル スキーマのノード プロパティ)
    - エスケープ文字 (フラット ファイル スキーマのノード プロパティ)  
    - エスケープ文字の種類 (フラット ファイル スキーマのノード プロパティ)