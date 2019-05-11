---
title: XSD の役割 |Microsoft Docs
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
ms.openlocfilehash: d6cb9a975f137263265051be0235f33d35bd4a41
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65303531"
---
# <a name="role-of-xsd"></a>XSD の役割
XML スキーマ定義 (XSD) 言語は、BizTalk で定義されるメッセージ スキーマの基礎となる構文を提供します。 BizTalk エディターおよび BizTalk マッパーのツリー ビューは、独自のプロパティのセットとレコードの BizTalk 固有のグラフィカルな階層と [フィールド] ノード (その他の種類のノード間)、各を使用して、このような階層が作成され、XSD として永続化します。 BizTalk エディターは、ノード数が、プロパティの値に関連付けられているさまざまなノードを追加またはツリー ビュー内のスキーマのグラフィック表現から削除し、構築される XSD を表示できる読み取り専用の XSD ビューを提供します。変更されました。 通常はありませんが、ツリー ビューでスキーマの階層構造を変更すると、XSD の変更内容を調査する場合は、単純なスキーマを BizTalk エディターを正常に構築する XSD の詳細を理解するために必要なは、XSD の使用方法について説明します。  
  
 BizTalk Server で定義されている注釈の広範なセットと、XSD 内でのスキーマ注釈機能は、フラット ファイルなどの XML 以外のメッセージを表すため、必要なセマンティクスをサポートするために拡張する XSD を効果的にできます。  
  
## <a name="see-also"></a>参照  
 [Web 上の XSD リソース](../core/xsd-resources-on-the-web.md)   
 [スキーマについて](../core/about-schemas.md)