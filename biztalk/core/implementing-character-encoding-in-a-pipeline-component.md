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
# <a name="implementing-character-encoding-in-a-pipeline-component"></a><span data-ttu-id="f81f0-102">パイプライン コンポーネントにおける文字エンコーディングを実装します。</span><span class="sxs-lookup"><span data-stu-id="f81f0-102">Implementing Character Encoding in a Pipeline Component</span></span>
<span data-ttu-id="f81f0-103">カスタムの文字エンコーディングをサポートする Microsoft .NET Framework から派生することによってカスタムのエンコード クラスを実装する必要があります**エンコード**クラス、標準のフラットから継承することによって独自のフラット ファイル パイプライン コンポーネントを作成し、ファイルの逆アセンブラーやフラット ファイル アセンブラー コンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="f81f0-103">To support custom character encoding, you must implement a custom encoding class by deriving from the Microsoft .NET Framework **Encoding** class, then create a custom flat file pipeline component by inheriting from the standard Flat File Disassembler or Flat File Assembler component.</span></span> <span data-ttu-id="f81f0-104">解析エンジンに新しいエンコード インスタンスを指定するには、保護された仮想メソッドをオーバーライドすることで**FFDasmComp.GetDataReader**次の例に示すようにします。</span><span class="sxs-lookup"><span data-stu-id="f81f0-104">You can supply a new encoding instance to the parsing engine by overriding the protected virtual method **FFDasmComp.GetDataReader** as shown in the following example.</span></span>  
  
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
  
## <a name="using-predefined-encoding-classes"></a><span data-ttu-id="f81f0-105">定義済みエンコード クラスを使用します。</span><span class="sxs-lookup"><span data-stu-id="f81f0-105">Using predefined encoding classes</span></span>  
 <span data-ttu-id="f81f0-106">次のエンコードの種類は、Microsoft .NET Framework によって定義済みし、パーサーの構築に使用できます。</span><span class="sxs-lookup"><span data-stu-id="f81f0-106">The following encoding types are predefined by the Microsoft .NET Framework and can be used to construct the parser:</span></span>  
  
-   <span data-ttu-id="f81f0-107">ASCII</span><span class="sxs-lookup"><span data-stu-id="f81f0-107">ASCII</span></span>  
  
-   <span data-ttu-id="f81f0-108">UTF7</span><span class="sxs-lookup"><span data-stu-id="f81f0-108">UTF7</span></span>  
  
-   <span data-ttu-id="f81f0-109">UTF8</span><span class="sxs-lookup"><span data-stu-id="f81f0-109">UTF8</span></span>  
  
-   <span data-ttu-id="f81f0-110">Unicode (UTF16)</span><span class="sxs-lookup"><span data-stu-id="f81f0-110">Unicode (UTF16)</span></span>  
  
```  
XmlReader xr = docspec.Parse(new DataReader(System.Text.Encoding.UTF8));  
```  
  
## <a name="using-supported-code-pages"></a><span data-ttu-id="f81f0-111">サポートされているコード ページを使用します。</span><span class="sxs-lookup"><span data-stu-id="f81f0-111">Using supported code pages</span></span>  
 <span data-ttu-id="f81f0-112">SHIFT-JIS (コード ページ 932) をサポートするのにには、次のコードを使用します。</span><span class="sxs-lookup"><span data-stu-id="f81f0-112">Use the following code to support Shift-JIS (codepage 932).</span></span>  
  

```  
XmlReader xr = docspec.Parse(new DataReader(System.Text.Encoding.GetEncoding(932)));  
```  
  
## <a name="using-a-private-encoding-class"></a><span data-ttu-id="f81f0-113">プライベート エンコード クラスの使用</span><span class="sxs-lookup"><span data-stu-id="f81f0-113">Using a private encoding class</span></span>  
 <span data-ttu-id="f81f0-114">派生した独自のエンコード クラスを作成することができます、 **System.Text.Encoding**クラスを抽象化し、独自のエンコードとデコードを実行します。</span><span class="sxs-lookup"><span data-stu-id="f81f0-114">You can create your own encoding class that derives from the **System.Text.Encoding** abstract class and perform your own encoding and decoding.</span></span>  
  
```  
class MyEncoding : System.Text.Encoding  
{  
   // overriding methods omitted  
}  
  
XmlReader xr = docspec.Parser(new DataReader(new MyEncoding()));  
```  
  
## <a name="using-a-private-datareader-class"></a><span data-ttu-id="f81f0-115">プライベート DataReader クラスの使用</span><span class="sxs-lookup"><span data-stu-id="f81f0-115">Using a private DataReader class</span></span>  

 <span data-ttu-id="f81f0-116">独自に作成することができます[DataReader](https://msdn.microsoft.com/library/microsoft.biztalk.parsingengine.datareader.aspx)を実装するクラス、`IDataReader`インターフェイスし、クラスのどのエンコーディングを作成することがなく読み取り操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="f81f0-116">You can create your own [DataReader](https://msdn.microsoft.com/library/microsoft.biztalk.parsingengine.datareader.aspx) class that implements the `IDataReader` interface and performs reading without creating any encoding classes.</span></span>  
  
```  
class MyDataReader : IDataReader  
{  
   // Implement data reader functions  
   // ...  
}  
  
XmlReader xr = docspec.Parse(new MyDataReader());  
```  
  
## <a name="see-also"></a><span data-ttu-id="f81f0-117">参照</span><span class="sxs-lookup"><span data-stu-id="f81f0-117">See Also</span></span>  
 [<span data-ttu-id="f81f0-118">解析エンジンおよびシリアル化エンジンの使用</span><span class="sxs-lookup"><span data-stu-id="f81f0-118">Using the Parsing and Serializing Engines</span></span>](../core/using-the-parsing-and-serializing-engines.md)