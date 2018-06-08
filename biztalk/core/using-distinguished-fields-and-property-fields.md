---
title: 識別フィールドおよびプロパティ フィールドの使用 |Microsoft ドキュメント
description: 識別フィールド、プロパティ フィールドとプロパティ セットの違いについて確認します。 識別フィールドが、メッセージ フィールドのパスを使用して、プロパティ フィールドを使用してが正しくありません名前とスキーマの名前空間、およびプロパティ セットは、メッセージ (プロパティ セット) のコンテキスト プロパティを BizTalk Server の別のメッセージのコンテキスト プロパティに割り当てる
ms.custom: ''
ms.date: 05/02/2018
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 264ee15e-be9a-4ba2-9c61-a1570b20378e
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2dc6233f71bb56fe831fded343e6557292cdb315
ms.sourcegitcommit: 3371ffd8ceca02e2b3715d53a1e0c0a59045912e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/07/2018
ms.locfileid: "34848906"
---
# <a name="using-distinguished-fields-and-property-fields"></a>識別フィールドおよびプロパティ フィールドの使用
識別フィールドは、主に判断を下したり、オーケストレーションでデータを操作するために使用する、特別なメッセージ データです。  
  
 メッセージ プロパティはデータも — メッセージ自体の内容: または"metadata"— タイムスタンプやルーティング情報などのメッセージに関するコンテキスト情報。 システムで定義されているメッセージ コンテキスト プロパティまたはトランスポート コンテキスト プロパティを使用することも、プロパティ スキーマ内からスキーマ フィールドを参照することで独自のプロパティを定義することもできます。 プロパティは、サブスクリプションおよび関連付けで使用されます。  
  
-   使用して、識別フィールドまたはプロパティ フィールドとしてスキーマ内のフィールドを指定することができます、**プロパティの昇格**エディター内からダイアログ ボックス。 詳細については、次を参照してください[プロパティの昇格。](../core/promoting-properties.md)  
  
-   .NET 型のフィールドを、DistinguishedField 属性で修飾することにより識別フィールドとして、または Property 属性で修飾することによりプロパティ フィールドとして、指定できます。  
  
## <a name="using-distinguished-fields"></a>識別フィールドの使用  
 識別フィールドは、メッセージ内でフィールドへのパスにより参照されます。次の例に示すように、ピリオドを使用して、メッセージ名、フィールドを囲むすべてのレコードの名前、およびフィールド自体の名前を区切ります。  
  
```  
MyMessage.MyRecord.MySubrecord.MyDistinguishedField  
```  
  
## <a name="using-property-fields"></a>プロパティ フィールドの使用  
 プロパティ スキーマにフィールドを追加すると、コードを使用してオーケストレーションで、およびフィルター式で、フィールドの値にアクセスできます。 プロパティ スキーマの詳細については、次を参照してください。[プロパティ スキーマ](../core/property-schemas.md)です。  
  
> [!NOTE]
>  メッセージ コンテンツまたはデータのプロパティは、基本的に、基になっているデータへのショートカットです。プロパティを変更するとデータが変更され、データを変更するとプロパティが変更されます。  
  
 次の例に示すように、メッセージのプロパティを参照するには、メッセージの名前の後に、名前空間 (スキーマ) とプロパティ名をかっこで囲んで指定します。  
  
```  
MyMessage(Invoice.PropertySchema.InvoiceID)  
```  
  
> [!NOTE]
>  フィールドのプロパティ名が _ _ に変更は、スキーマ内のフィールドの名前として予約済みキーワードを使用すると、クイック昇格 を選択して、フィールドを昇格する、\<予約済みキーワード\>です。 (二重のアンダー スコアはプロパティ名の前に追加されます。)ただし、オーケストレーションの式でこのプロパティ名を使用する場合、オーケストレーションを構築するときにコンパイラ エラーが表示されます。  このエラーを回避するのには、手動で追加する必要があります\@二重のアンダー スコアの前にします。 例を次に示します。  
>   
>  `MyMessage(Invoice.PropertySchema.@__Name) = "Product Name";`  
  
## <a name="property-sets"></a>プロパティ セット  
 あるメッセージのすべてのコンテキスト プロパティ (プロパティ セット) を、別のメッセージのコンテキスト プロパティに割り当てることもできます。 プロパティ セットを割り当てるには、プロパティをかっこで囲むのと同じように、単に両方のメッセージ名の後にかっこで囲んだアスタリスクを付加します。  
  
```  
MyMessage2(*)=MyMessage1(*);  
```  
  
 この例で、プロパティ セットを MyMessage2 に割り当てた後、MyMessage2 のすべてのプロパティには、MyMessage1 のプロパティと同じ値が含まれます。  
  
## <a name="see-also"></a>参照  
 [プロパティの昇格](../core/promoting-properties.md)   
 [受信メッセージ図形にフィルターを使用します。](../core/using-filters-with-the-receive-message-shape.md)   
 [オーケストレーションでメッセージの使用](../core/using-messages-in-orchestrations.md)   
 [BizTalk メッセージ コンテキストのプロパティについて](../core/about-biztalk-message-context-properties.md)
