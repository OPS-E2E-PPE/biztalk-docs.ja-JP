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
ms.openlocfilehash: 21bc0c175303f7ccfd64a896dd713bf4651b6dcb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65346205"
---
# <a name="escape-characters"></a>エスケープ文字

## <a name="overview"></a>概要
エスケープ文字とは、特殊な意味を持つ文字の前に置くことによって、その意味を無効化させることのできる単一の文字のことです。 たとえば、次のように、次の特性を持つものとして、フラット ファイル レコードを定義する場合。  
  
- Name = Record1  
  
- [区切り記号]  
  
- 子区切り記号 = コンマ (,)  
  
- 子の順序 = 接頭辞  
  
- エスケープ文字 = 円記号 (\\)  
  
- タグ = RECORD1  
  
- Field1 および Field2 という名前の 2 つのフィールド  
  
  次のレコードの次のフラット ファイル データが適用されます。  
  
```  
RECORD1,testfield1\,testfield1,testfield2  
                  ^^  
  
```  
  
 データは、次の XML のフラグメントに逆アセンブルされます。  
  
```  
<Record1>  
    <Field1>testfield1,testfield1</Field1>  
    <Field2>testfield2</Field2>  
</Record1>  
  
```  
  
 エスケープ文字のシーケンスに注意してください`\,`フラット ファイル レコードを次の行に示される、同等の XML レコードの 1 つのコンマ文字データにエスケープ文字を使用せずに Field1 の変換されています。 さらに、コンマ文字が、他の 2 つのコンマのようなフィールドの区切り記号としては解釈されません。  
  
 エスケープ文字を解釈するかを示す field1 では、コンマの前に挿入するフラット ファイル アセンブラーでは、レコードの XML バージョンを同等のフラット ファイル レコードに変換する逆の操作を実行するときフィールド区切り記号ではなくデータとして。  
  
 BizTalk エディターを使用してフラット ファイル スキーマを作成するときに使用して、スキーマ全体の既定のエスケープ文字を定義することができます、**既定のエスケープ文字**と**既定のエスケープ文字の種類**プロパティ**スキーマ**ノード。 次に、この既定のエスケープ文字またはを使用して、カスタム レコードに固有のエスケープ文字を使用するか、スキーマで個々 のレコードを構成、**エスケープ文字]** と**エスケープ文字の種類**のプロパティ、**レコード**ノード。  
  
## <a name="see-also"></a>参照  
- [特殊文字をフィールド値の一部として解釈させる方法](../core/ways-to-interpret-special-characters-as-part-of-a-field-value.md)  
- エスケープ文字プロパティ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]:  
    - 既定のエスケープ文字 (フラット ファイル スキーマのノード プロパティ)
    - 既定のエスケープ文字の種類 (フラット ファイル スキーマのノード プロパティ)
    - エスケープ文字 (フラット ファイル スキーマのノード プロパティ)  
    - エスケープ文字の種類 (フラット ファイル スキーマのノード プロパティ)