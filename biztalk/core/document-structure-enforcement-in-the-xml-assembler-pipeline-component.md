---
title: "XML アセンブラー パイプライン コンポーネントにおける構造の強化を文書化 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Add XML declaration property
- pipeline components, XML Assembler
ms.assetid: c121ec4b-c02b-4626-a5be-2937500dbefa
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e46dbc613439b24403c66c345b9023151b409213
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="document-structure-enforcement-in-the-xml-assembler-pipeline-component"></a>XML アセンブラー パイプライン コンポーネントにおけるドキュメント構造の強化
XML アセンブラーでドキュメントまたはエンベロープ スキーマが明示的に参照されている場合、参照されたスキーマに対応するメッセージ タイプのドキュメントだけが処理されます。 その他すべてのドキュメントは、該当するスキーマが配置されていたとしても、処理から除外されます。  
  
> [!NOTE]
>  エンベロープ スキーマは最初のメッセージからのみ取得されます。 エンベロープのプロパティは常に最初のメッセージから取得されます。  
  
## <a name="see-also"></a>参照  
 [XML アセンブラー パイプライン コンポーネント](../core/xml-assembler-pipeline-component.md)   
 [XML アセンブラー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-xml-assembler-pipeline-component.md)   
 [パイプライン AssemblerDisassembler (BizTalk Server Samples フォルダ)](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)