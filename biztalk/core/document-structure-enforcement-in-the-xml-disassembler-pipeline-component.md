---
title: "XML 逆アセンブラー パイプライン コンポーネントにおける構造の強化を文書化 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XML Disassembler [pipeline component], document structure
- pipeline components, XML Disassembler
ms.assetid: ac405bf2-f92b-4b45-8256-dd188ec9510a
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9e14b20292b23a0f50362940e3b873fa37a3f5bd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="document-structure-enforcement-in-the-xml-disassembler-pipeline-component"></a>XML 逆アセンブラー パイプライン コンポーネントにおけるドキュメント構造の強化
XML 逆アセンブラーでドキュメント スキーマまたはエンベロープ スキーマが明示的に参照されている場合、XML 逆アセンブラーは、そのスキーマに準拠したメッセージ タイプのドキュメントだけを処理します。 その他のドキュメントは、配置されたスキーマが参照されているかどうかに関係なく、処理から除外されます。  
  
 XML 逆アセンブラーでは、エンベロープ スキーマの順序は強制されますがドキュメント スキーマの順序は強制されません。  
  
## <a name="see-also"></a>参照  
 [XML 逆アセンブラー パイプライン コンポーネント](../core/xml-disassembler-pipeline-component.md)   
 [XML 逆アセンブラー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-xml-disassembler-pipeline-component.md)