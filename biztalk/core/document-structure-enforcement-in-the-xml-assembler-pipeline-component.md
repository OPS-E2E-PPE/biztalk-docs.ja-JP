---
title: 構造の強化、XML アセンブラー パイプライン コンポーネントでのドキュメント |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Add XML declaration property
- pipeline components, XML Assembler
ms.assetid: c121ec4b-c02b-4626-a5be-2937500dbefa
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9ef167df5aaef827e11d33fc73191d46b68afb2c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389524"
---
# <a name="document-structure-enforcement-in-the-xml-assembler-pipeline-component"></a>XML アセンブラー パイプライン コンポーネントにおけるドキュメント構造の強化
XML アセンブラーでドキュメントまたはエンベロープ スキーマが明示的に参照を場合、XML アセンブラーは、参照されたスキーマに対応するメッセージの種類のドキュメントだけを処理することを確認します。 その他すべてのドキュメントは、該当するスキーマが配置されていたとしても、処理から除外されます。  
  
> [!NOTE]
>  エンベロープ スキーマは最初のメッセージからのみ取得されます。 エンベロープのプロパティは常に最初のメッセージから取得されます。  
  
## <a name="see-also"></a>参照  
 [XML アセンブラー パイプライン コンポーネント](../core/xml-assembler-pipeline-component.md)   
 [XML アセンブラー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-xml-assembler-pipeline-component.md)   
 [Pipelines-AssemblerDisassembler (BizTalk Server サンプル フォルダー)](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)