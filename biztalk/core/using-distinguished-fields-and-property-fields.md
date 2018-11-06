---
title: 識別フィールドとプロパティ フィールドを使用して |Microsoft Docs
description: 識別フィールド、プロパティ フィールドとプロパティ セットの違いについて説明します。 識別フィールドは、メッセージ フィールドにパスを使用して、プロパティ フィールドは、メッセージの名前とスキーマ名前空間を使用して、プロパティ セットは、BizTalk Server の他のメッセージのコンテキスト プロパティをメッセージ (プロパティ セット) のコンテキスト プロパティを割り当てる
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
ms.openlocfilehash: dd58f8b9e72f955bc02c5b7116469390468937d9
ms.sourcegitcommit: 53b16fe6c1b1707ecf233dbd05f780653eb19419
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2018
ms.locfileid: "50752305"
---
# <a name="using-distinguished-fields-and-property-fields"></a>識別フィールドとプロパティ フィールドの使用
識別フィールドは、主に判断を下したり、オーケストレーションでデータを操作するために使用する、特別なメッセージ データです。  
  
 メッセージ プロパティは、いずれかのデータ、メッセージ自体の内容: または"metadata"— タイムスタンプやルーティング情報などのメッセージに関するコンテキスト情報。 システムで定義されているメッセージ コンテキスト プロパティまたはトランスポート コンテキスト プロパティを使用することも、プロパティ スキーマ内からスキーマ フィールドを参照することで独自のプロパティを定義することもできます。 プロパティは、サブスクリプションおよび関連付けで使用されます。  
  
-   使用して、スキーマ内のフィールドを識別フィールドまたはプロパティ フィールドとして指定できます、**プロパティの昇格** ダイアログ ボックスから、エディター内で。 詳細については、次を参照してください[プロパティの昇格。](../core/promoting-properties.md)  
  
-   .NET 型のフィールドを、DistinguishedField 属性で修飾することにより識別フィールドとして、または Property 属性で修飾することによりプロパティ フィールドとして、指定できます。  
  
## <a name="using-distinguished-fields"></a>識別フィールドの使用  
 識別フィールドは、メッセージ内でフィールドへのパスにより参照されます。次の例に示すように、ピリオドを使用して、メッセージ名、フィールドを囲むすべてのレコードの名前、およびフィールド自体の名前を区切ります。  
  
```  
MyMessage.MyRecord.MySubrecord.MyDistinguishedField  
```  
  
## <a name="using-property-fields"></a>プロパティ フィールドの使用  
 プロパティ スキーマにフィールドを追加すると、コードを使用してオーケストレーションで、およびフィルター式で、フィールドの値にアクセスできます。 プロパティ スキーマの詳細については、次を参照してください。[プロパティ スキーマ](../core/property-schemas.md)します。  
  
> [!NOTE]
>  メッセージ コンテンツまたはデータのプロパティは、基本的に、基になっているデータへのショートカットです。プロパティを変更するとデータが変更され、データを変更するとプロパティが変更されます。  
  
 次の例に示すように、メッセージのプロパティを参照するには、メッセージの名前の後に、名前空間 (スキーマ) とプロパティ名をかっこで囲んで指定します。  
  
```  
MyMessage(Invoice.PropertySchema.InvoiceID)  
```  
  
> [!NOTE]
>  _ _ に、フィールドのプロパティの名前が変更されたスキーマ内のフィールドの名前として予約済みキーワードを使用すると、クイック昇格を選択して、フィールドを昇格する、\<予約済みキーワード\>します。 (二重のアンダー スコアは、プロパティ名の前に追加されます)。ただし、オーケストレーションの式でこのプロパティ名を使用する場合、オーケストレーションを構築するときに、コンパイラ エラーが受信されます。  このエラーを回避するのには、手動で追加する必要があります\@二重のアンダー スコアの前にします。 例えば以下のようにします。  
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
