---
title: パイプライン コンポーネントにおける文字エンコーディングを実装する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components [custom], examples
- pipeline components [custom], code samples
- pipeline components [custom], encoding
ms.assetid: 862b56da-ec14-41f9-b63c-42d81124e167
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8445a69b8de63ad2a0df91d3720436d79d605fdc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382614"
---
# <a name="implementing-character-encoding-in-a-pipeline-component"></a>パイプライン コンポーネントにおける文字エンコーディングを実装します。
カスタムの文字エンコーディングをサポートする Microsoft .NET Framework から派生することによってカスタムのエンコード クラスを実装する必要があります**エンコード**クラス、標準のフラットから継承することによって独自のフラット ファイル パイプライン コンポーネントを作成し、ファイルの逆アセンブラーやフラット ファイル アセンブラー コンポーネントです。 解析エンジンに新しいエンコード インスタンスを指定するには、保護された仮想メソッドをオーバーライドすることで**FFDasmComp.GetDataReader**次の例に示すようにします。  
  
```  
/// <summary>  
/// Gets a data reader instance  
/// </summary>  
/// <param name="dataStream">Data stream</param>  
/// <param name="dataEncoding">Data encoding</param>  
/// <param name="detectEncodingFromByteOrderMarks">Detect encoding from a byte order mark</param>  
/// <returns>IDataReader instance</returns>  
      protected override IDataReader GetDataReader(Stream dataStream, Encoding dataEncoding, bool detectEncodingFromByteOrderMarks)  
      {  
         // Delegate call to the base implementation passing fixed UTF-7 encoding  
         return base.GetDataReader(dataStream, new CustomEncoding(), false);  
      }  
```  
  
## <a name="using-predefined-encoding-classes"></a>定義済みエンコード クラスを使用します。  
 次のエンコードの種類は、Microsoft .NET Framework によって定義済みし、パーサーの構築に使用できます。  
  
-   ASCII  
  
-   UTF7  
  
-   UTF8  
  
-   Unicode (UTF16)  
  
```  
XmlReader xr = docspec.Parse(new DataReader(System.Text.Encoding.UTF8));  
```  
  
## <a name="using-supported-code-pages"></a>サポートされているコード ページを使用します。  
 SHIFT-JIS (コード ページ 932) をサポートするのにには、次のコードを使用します。  
  

```  
XmlReader xr = docspec.Parse(new DataReader(System.Text.Encoding.GetEncoding(932)));  
```  
  
## <a name="using-a-private-encoding-class"></a>プライベート エンコード クラスの使用  
 派生した独自のエンコード クラスを作成することができます、 **System.Text.Encoding**クラスを抽象化し、独自のエンコードとデコードを実行します。  
  
```  
class MyEncoding : System.Text.Encoding  
{  
   // overriding methods omitted  
}  
  
XmlReader xr = docspec.Parser(new DataReader(new MyEncoding()));  
```  
  
## <a name="using-a-private-datareader-class"></a>プライベート DataReader クラスの使用  

 独自に作成することができます[DataReader](https://msdn.microsoft.com/library/microsoft.biztalk.parsingengine.datareader.aspx)を実装するクラス、`IDataReader`インターフェイスし、クラスのどのエンコーディングを作成することがなく読み取り操作を実行します。  
  
```  
class MyDataReader : IDataReader  
{  
   // Implement data reader functions  
   // ...  
}  
  
XmlReader xr = docspec.Parse(new MyDataReader());  
```  
  
## <a name="see-also"></a>参照  
 [解析エンジンおよびシリアル化エンジンの使用](../core/using-the-parsing-and-serializing-engines.md)