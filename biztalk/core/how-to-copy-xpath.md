---
title: XPath をコピーする方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 404599d4-0fb3-4c7c-91e6-1295d9d0965e
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bb282c5c32d8da62a9da6d7a9c900c798e44eee7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248530"
---
# <a name="how-to-copy-xpath"></a>XPath をコピーする方法
XSD (XML Schema Definition) 言語は、BizTalk Server で定義されるメッセージ スキーマの基礎となる構文を提供します。 BizTalk マッパーのツリー ビューでは、それぞれ独自のプロパティのセットを備えた、レコード ノードおよびフィールド ノードの BizTalk 固有のグラフィカルな階層 (他の種類のノード間) を使用します。ただし、このような階層は、XSD として構築および保存されます。  
  
 マップが複雑で複数のグリッド ページが含まれる場合は、スキーマ ノードの親を特定するのが難しいことがあります。 このような場合は XSD パスが役に立ちます。 XSD パスを使用すると、スキーマ ノードの深さについての情報を得ることができます。 また、このパスを別のグリッド ページで再利用して、リレーションシップを識別できます。  
  
## <a name="prerequisites"></a>前提条件  
 これらの手順では、BizTalk マッパーが実行されている必要があります。  
  
### <a name="to-copy-the-xsd-path-xpath"></a>XSD パス (XPath) をコピーするには  
  
1.  XSD パスが必要し、なる をクリックし、スキーマ ノードを右クリックして**コピー XPath**です。  
  
2.  テキスト エディターを開きます。 **[編集]** メニューの **[貼り付け]** をクリックします。 XSD パスを確認できるようになります。  
  
    > [!NOTE]
    >  または、Ctrl + V キーを押してテキスト エディターにパスを貼り付けることもできます。  
  
     次に示すコードは、選択されているスキーマ ノードの XSD パスです。  
  
    ```  
    /*[local-name()='<Schema>']/*[local-name()='Shipment']/*[local-name()='DataCollection']  
    ```  
  
## <a name="see-also"></a>参照  
 [BizTalk マッパーの強化された機能を使用](../core/using-enhanced-features-in-biztalk-mapper.md)   
 [スキーマを置換する方法](../core/how-to-replace-schemas.md)   
 [展開して、スキーマ ツリーを折りたたむ方法](https://msdn.microsoft.com/library/ee253802(v=bts.10).aspx)