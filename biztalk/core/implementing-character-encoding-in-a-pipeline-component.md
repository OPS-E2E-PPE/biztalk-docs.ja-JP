---
title: パイプライン コンポーネントの文字エンコーディングを実装する |Microsoft ドキュメント
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
ms.openlocfilehash: a1bc95dc44fa4a4905affaad969c248aa4b76d89
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257050"
---
# <a name="implementing-character-encoding-in-a-pipeline-component"></a>パイプライン コンポーネントの文字エンコーディングを実装します。
カスタム文字エン コードをサポートする Microsoft .NET Framework から派生することによってカスタムのエンコード クラスを実装する必要があります**エンコード**クラス、し、カスタムのフラット ファイル パイプライン コンポーネントを作成するには、標準のフラットを継承ファイルの逆アセンブラーやフラット ファイル アセンブラー コンポーネントです。 プロテクト仮想メソッドをオーバーライドすることで、解析エンジンに新しいエンコード インスタンスを指定することができます**FFDasmComp.GetDataReader**次の例で示すようにします。  
  
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
  
## <a name="using-predefined-encoding-classes"></a>定義済みエンコード クラスの使用  
 次のエンコードの種類は Microsoft .NET Framework で定義済みであり、パーサーの構築に使用できます。  
  
-   ASCII  
  
-   UTF7  
  
-   UTF8  
  
-   Unicode (UTF16)  
  
```  
XmlReader xr = docspec.Parse(new DataReader(System.Text.Encoding.UTF8));  
```  
  
## <a name="using-supported-code-pages"></a>サポートされているコード ページの使用  
 Shift-JIS (コード ページ 932) をサポートするには、次のコードを使用します。  
  

```  
XmlReader xr = docspec.Parse(new DataReader(System.Text.Encoding.GetEncoding(932)));  
```  
  
## <a name="using-a-private-encoding-class"></a>プライベート エンコード クラスの使用  
 派生した独自のエンコード クラスを作成することができます、 **System.Text.Encoding**クラスを抽象化し、独自のエンコードおよびデコードを実行します。  
  
```  
class MyEncoding : System.Text.Encoding  
{  
   // overriding methods omitted  
}  
  
XmlReader xr = docspec.Parser(new DataReader(new MyEncoding()));  
```  
  
## <a name="using-a-private-datareader-class"></a>プライベート DataReader クラスの使用  

 独自に作成することができます[DataReader](https://msdn.microsoft.com/library/microsoft.biztalk.parsingengine.datareader.aspx)を実装するクラス、`IDataReader`インターフェイスし、クラスのどのエンコーディングを作成せずに読み取り操作を実行します。  
  
```  
class MyDataReader : IDataReader  
{  
   // Implement data reader functions  
   // ...  
}  
  
XmlReader xr = docspec.Parse(new MyDataReader());  
```  
  
## <a name="see-also"></a>参照  
 [解析およびシリアル化エンジンを使用します。](../core/using-the-parsing-and-serializing-engines.md)