---
title: XSD の役割 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1fe08f6b-563f-4bae-a5be-551e487b2a6d
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1ad2f99b60de5ebb2a3cd7e102a2f3f7b787d1ad
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268578"
---
# <a name="role-of-xsd"></a>XSD の役割
XSD (XML Schema Definition) 言語は、BizTalk で定義されるメッセージ スキーマの基礎となる構文を提供します。 BizTalk エディターと BizTalk マッパーのツリー ビューでは、それぞれ独自のプロパティのセットを備えた、レコード ノードおよびフィールド ノードの BizTalk 固有のグラフィカルな階層 (他の種類のノード間) を使用します。ただし、このような階層は、XSD として構築および保存されます。 BizTalk エディターでは、読み取り専用の XSD ビューを使用できます。このビューでは、グラフィカルに表示されているツリー ビューのスキーマにさまざまなノードを追加する場合、スキーマからさまざまなノードを削除する場合、およびこれらのノードに関連付けられているプロパティの値が変更される場合に構築される XSD を表示できます。 通常、BizTalk エディターで単純なスキーマを構築する場合に XSD の詳細を把握する必要はありません。ただし、ツリー ビューのスキーマ階層に対して変更を行う場合に XSD の変更内容を調査すると、XSD の使用方法を学習できます。  
  
 XSD のスキーマ注釈機能と、BizTalk Server によって定義される幅広い注釈のセットを使用すると、XSD を効果的に拡張して、フラット ファイルなどの XML 以外のメッセージを表すためのセマンティクスをサポートすることができます。  
  
## <a name="see-also"></a>参照  
 [Web 上の XSD リソース](../core/xsd-resources-on-the-web.md)   
 [スキーマについて](../core/about-schemas.md)