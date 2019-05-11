---
title: Siebel の SELECT ステートメントの構文 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Data Provider for Siebel, searching and sorting data using
- Data Provider for Siebel, SELECT statement
- SELECT statement, syntax for
ms.assetid: 8528b115-d6f3-420d-8617-0e56dc8922bf
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3e25e8af2bd192495108204ded53b682333d64f8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65370495"
---
# <a name="syntax-for-a-select-statement-in-siebel"></a>Siebel の SELECT ステートメントの構文
使用して、 [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]、ADO.NET クライアントは Siebel 検索の有効な定義を表す WHERE 句を指定することで Siebel ビジネス コンポーネントに対する SELECT クエリを実行することができます。 SELECT ステートメントの構文です。  
  
```  
SELECT  
<column name 1> AS <column alias 1>,  
<column name 2> AS <column alias 2>,  
…  
FROM  
<Business object name>.<Business component name> AS <table alias>  
WHERE  
<filter condition>  
OPTION  
'ViewMode <value>'  
```  
  
 上記の構文で ViewMode オプションに対応 Siebel システムの表示モード、クエリに一致するレコードのセットを制限するフィルター メカニズムです。 値の許可されたセットは、Siebel のドキュメントを参照してください。  
  
> [!NOTE]
>  WHERE 句内のフィールド名には、特殊文字または空白が含まれている場合、常に角かっこ内のフィールド名を囲むことを確認します。  
> 
> [!NOTE]
>  特殊文字を含むエイリアス名を含む SELECT クエリで角かっこ内のエイリアス名を含めることを確認します。  
> 
> [!NOTE]
>  [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] WHERE 句ではなく、SELECT 句で、テーブル名でサポート エイリアス。  
  
## <a name="searching-and-sorting-data-using-the-data-provider-for-siebel"></a>Siebel 用データ プロバイダーを使用してデータの並べ替えと検索  
 [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] Siebel システムでサポートされている検索仕様に基づいて SQL ステートメントでフィルター条件をサポートしています。  
  
 検索条件の規則は次のとおりです。  
  
- 標準的な比較演算子は、定数、フィールドまたは別のフィールドに 1 つのフィールドを比較するために使用する必要があります。 以下の =、! =、>、<>、=、および < =。  
  
  ```  
  Example: [Revenue] > 5000  
  ```  
  
- 文字列定数は二重引用符で囲む必要があり、文字列値は大文字小文字を区別する必要があります。  
  
  ```  
  Example: [Type] != "COST LIST"  
  ```  
  
- 論理演算子 AND、OR、および否定または式を結合するために使用する必要がありません。 これらの演算子では大文字小文字の区別が無視されます。たとえば、"and"と同じでは、"AND"。  
  
  ```  
  Example: [Competitor] IS NOT NULL and [Competitor] != "N"  
  ```  
  
- 検索の定義でフィールド名は、角かっこで囲む必要があります。  
  
  ```  
  Example: [Conflict Id] = 0  
  ```  
  
- LIKE 演算子は、フィールドが、定数と比較して、比較式のテキスト文字列を作成するために使用可能性があります。 または別のフィールドと最初のいくつかの文字のみで一致するフィールドが必要です。 ワイルドカード文字"*「と」?" それぞれの文字、および単一の文字の任意の数を示すために使用する必要があります。  
  
- ADO.NET クライアントには、元の Siebel ビジネス オブジェクト、ビジネス コンポーネント、およびビジネス コンポーネントのフィールド名を指定できます。 特殊文字や空白文字が含まれている場合、これらの名前を角かっこで囲む必要があります。 サポートされているクエリの例は次のとおりです。  
  
  ```  
  SELECT [Name], [Postal Code] FROM Account.Account where [Postal Code] != '11065'  
  SELECT [Name], [Postal Code], Id From Account.Account where [Postal Code] != '60626' Order BY Id ASC, Name DESC  
  SELECT * FROM [Admin Price List].[Price Book Items]  
  ```  
  
  [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] Siebel でサポートされている並べ替え仕様に基づいて SQL ステートメントの仕様の並べ替えがサポートされます。 並べ替え仕様の規則は次のとおりです。  
  
- 並べ替え仕様; でフィールド名を区切るコンマを使用します。たとえば、名前、場所  
  
- リスト内のフィールドを降順に並べ替えることを示す、「開始日 (DESC) です」のように、フィールド名の後 (DESC) を含める 並べ替え順序が指定されていない場合は、昇順が使用されます。 昇順を明示的に指定するには、キーワード (ASC) を使用します。  
  
- 並べ替え仕様の式は 255 文字である必要がありますまたはそれ以下。  
  
## <a name="see-also"></a>参照  
 [.NET Framework Data Provider for Siebel eBusiness Applications を使用する](../../adapters-and-accelerators/adapter-siebel/use-the-net-framework-data-provider-for-siebel-ebusiness-applications.md)