---
title: 設定の出力に XSLT を指定する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4c541432-fd4e-41cc-8bcc-f570ce5df439
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1d55a8ddccb996f11315c8856797147083da9123
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998035"
---
# <a name="set-map-compilation-and-output-settings"></a>マップのコンパイルの設定し、出力の設定
BizTalk マッパーでマップのプロパティを設定します。 

マップを使用してこれらのプロパティ、マップのコンパイル方法を設定、含めるまたは XML 宣言を除外およびエンコーディングを設定します。 

このトピックでは、マップ上でこれらのプロパティを設定する方法を示します。

## <a name="set-the-map-level-compilation"></a>マップ レベルのコンパイルを設定します。

**以降で[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]** 、選択した、`XslTransform`または`XslCompiledTransform`マップをコンパイルするクラス。 

1. グリッド ビューでは、マップを開きます。
2. マッパー グリッドで任意の場所を右クリックし、選択**プロパティ**します。  
3. 設定、 **XSL 変換を使用して**プロパティ。 

    | オプション | 説明 |
    | --- | --- |
    | 未定義。 | XslTransform 設定のレジストリ フラグが使用されます。 <ul><li>64 ビット ホスト インスタンス: `HKLM\SOFTWARE\Microsoft\BizTalk Server\3.0\Configuration`</li><li>32 ビットのホスト インスタンス、および Visual Studio のマップのテスト機能: `HKLM\SOFTWARE\Wow6432Node\Microsoft\BizTalk Server\3.0\Configuration`</li></ul> | 
    | True | マップのコンパイルのレベル プロパティに設定されて`XslTransform`(従来の動作) | 
    | False | マップのコンパイルのレベル プロパティに設定します。 `XslCompiledTransform` | 

> [!NOTE]
> BizTalk Server 2013 以降では、コンパイルのマッパーの動作がから変更されました`XslTransform`に`XslCompiledTransform`します。 [、マッパーの更新プログラムにとって何を意味する](http://www.quicklearn.com/blog/2013/05/24/what-the-biztalk-server-2013-mapper-updates-mean-for-you/)ブログの投稿の動作とその潜在的な影響の優れた説明を提供します。 
> 
> 以降で[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]マップをコンパイルするには、どのクラスを選択できます。 
  
## <a name="include-or-exclude-an-xml-declaration"></a>含めるか、XML 宣言を除外  
XML 宣言があるか出力かどうかを選択できます。 

1. グリッド ビューでは、マップを開きます。
2. マッパー グリッドで任意の場所を右クリックし、選択**プロパティ**します。  
3. ドロップダウン リストで、 **XML 宣言の省略**プロパティで、**はい**XML 宣言を省略する場合。 選択**いいえ**XML 宣言を省略するされません。  

XML 宣言が表示されます (選択した場合**いいえ**)、次のようにします。  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
```  
  
## <a name="set-encoding-for-output-instance-data"></a>出力インスタンス データのエンコーディングを設定します。  
"エンコード" プロパティによって、マップの出力結果の作成で必要となる文字セットに関する情報が、ランタイム エンジンに提供されます。  
   
1. グリッド ビューでは、マップを開きます。
2. マッパー グリッドで任意の場所を右クリックし、選択**プロパティ**します。    
3.  ドロップダウン リストで、 **XSLT エンコード**プロパティ、文字セットを選択は、出力インスタンス データに使用します。  
  
## <a name="see-also"></a>参照  
 [コンパイルして、マップのテスト](../core/compiling-and-testing-maps.md)   
 [BizTalk マッパーの使用](../core/using-biztalk-mapper.md)   
 [BizTalk マッパーでの有効な XSLT エンコードの種類](../core/valid-biztalk-mapper-xslt-encoding-types.md)