---
title: 出力設定の XSLT を指定する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: e1aa3eea4c3f2f4696d3dc1fdf8109aeddec3ff8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255338"
---
# <a name="set-map-compilation-and-output-settings"></a>マップのコンパイルを設定し、出力設定
BizTalk マッパーでマップのプロパティを設定します。 

これらを使用してマップのプロパティは、マップのコンパイル方法を設定、含めるまたは、XML 宣言を除外するし、エンコードを設定します。 

このトピックでは、マップ上でこれらのプロパティを設定する方法を示します。

## <a name="set-the-map-level-compilation"></a>マップ レベルのコンパイルを設定します。

**以降で[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]** を選択する、`XslTransform`または`XslCompiledTransform`マップをコンパイルするクラス。 

1. グリッド ビューでは、マップを開きます。
2. マッパー グリッドの任意の場所を右クリックし、選択**プロパティ**です。  
3. 設定、**使用 XSL 変換**プロパティ。 

    | オプション | Description |
    | --- | --- |
    | 未定義。 | XslTransform 設定のレジストリ フラグを使用します。 <ul><li>64 ビット ホスト インスタンス:`HKLM\SOFTWARE\Microsoft\BizTalk Server\3.0\Configuration`</li><li>32 ビット ホスト インスタンス、および Visual Studio のマップのテスト機能:`HKLM\SOFTWARE\Wow6432Node\Microsoft\BizTalk Server\3.0\Configuration`</li></ul> | 
    | True | マップのコンパイルのレベル プロパティに設定`XslTransform`(従来の動作) | 
    | False | マップのコンパイルのレベル プロパティに設定します。`XslCompiledTransform` | 

> [!NOTE] 
> BizTalk Server 2013 以降では、マッパー コンパイルの動作が変更されたから`XslTransform`に`XslCompiledTransform`です。 [、マッパーの更新プログラムの意味を](http://www.quicklearn.com/blog/2013/05/24/what-the-biztalk-server-2013-mapper-updates-mean-for-you/)ブログの投稿に説明優れたの動作とその考えられる影響します。 
> 
> 以降で[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]、どのクラスをマップをコンパイルすることができます。 
  
## <a name="include-or-exclude-an-xml-declaration"></a>XML 宣言のエクスクルードまたはインクルード  
XML 宣言があるか出力かどうかを選択できます。 

1. グリッド ビューでは、マップを開きます。
2. マッパー グリッドの任意の場所を右クリックし、選択**プロパティ**です。  
3. ドロップダウン リストで、 **XML 宣言の省略**プロパティで、**はい**XML 宣言を省略する場合。 選択**いいえ**XML 宣言を省略するされません。  

XML 宣言が表示されます (選択した場合は**いいえ**) 次のようにします。  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
```  
  
## <a name="set-encoding-for-output-instance-data"></a>出力インスタンス データのエンコードを設定します。  
"エンコード" プロパティによって、マップの出力結果の作成で必要となる文字セットに関する情報が、ランタイム エンジンに提供されます。  
   
1. グリッド ビューでは、マップを開きます。
2. マッパー グリッドの任意の場所を右クリックし、選択**プロパティ**です。    
3.  ドロップダウン リストで、 **XSLT エンコード**プロパティ、文字セットを選択する出力インスタンス データに使用します。  
  
## <a name="see-also"></a>参照  
 [コンパイルして、マップのテスト](../core/compiling-and-testing-maps.md)   
 [BizTalk マッパーの使用](../core/using-biztalk-mapper.md)   
 [BizTalk マッパーの有効な XSLT エンコードの種類](../core/valid-biztalk-mapper-xslt-encoding-types.md)