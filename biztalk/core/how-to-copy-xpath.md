---
title: XPath をコピーする方法 |Microsoft Docs
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
ms.openlocfilehash: 5bf9a8da90f264abb0953592abf16dc0e157fcb5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385600"
---
# <a name="how-to-copy-xpath"></a>XPath をコピーする方法
XML スキーマ定義 (XSD) 言語は、BizTalk Server 内で定義されるメッセージ スキーマの基礎となる構文を提供します。 BizTalk マッパーのツリー ビューは、独自のプロパティのセットとレコードの BizTalk 固有のグラフィカルな階層と [フィールド] ノード (その他の種類のノード間)、各を使用して、このような階層が作成され、XSD として永続化します。  
  
 マップが複雑になり、span をグリッド ページ間ではここでは、スキーマのノードの親を検索するは難しいです。 XSD パスは、ここで使用されます。 XSD パスを使用すると、スキーマ ノードの深さについての情報を取得します。 また、リレーションシップを識別するために別のグリッド ページ内にこのパスを再利用できます。  
  
## <a name="prerequisites"></a>前提条件  
 これらの手順では、BizTalk マッパーが実行されている必要があります。  
  
### <a name="to-copy-the-xsd-path-xpath"></a>XSD パス (XPath) をコピーするには  
  
1.  スキーマのノードを XSD パスが必要し、し、をクリックを右クリックして**XPath のコピー**します。  
  
2.  テキスト エディターを開きます。 **[編集]** メニューの **[貼り付け]** をクリックします。 XSD パスが確認できます。  
  
    > [!NOTE]
    >  またをテキスト エディターで、パスを貼り付けるには、CTRL + V を押すことができます。  
  
     次のコードでは、選択したスキーマ ノードの XSD パスが表示されます。  
  
    ```  
    /*[local-name()='<Schema>']/*[local-name()='Shipment']/*[local-name()='DataCollection']  
    ```  
  
## <a name="see-also"></a>参照  
 [BizTalk マッパーの強化された機能を使用](../core/using-enhanced-features-in-biztalk-mapper.md)   
 [スキーマを置換する方法](../core/how-to-replace-schemas.md)   
 [展開し、スキーマ ツリーを折りたたむ方法](https://msdn.microsoft.com/library/ee253802(v=bts.10).aspx)