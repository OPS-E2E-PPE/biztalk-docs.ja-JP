---
title: XML 逆アセンブラー パイプライン コンポーネントでの検証のドキュメント |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Validate Document Structure property
- pipeline components, XML Disassembler
- XML Disassembler [pipeline component], document validation
- XML Disassembler [pipeline component], warnings
ms.assetid: feb25033-46d3-48ed-8e1f-0cd123e94149
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8015fdae6bce4b9ac163770d3909206f0325e7c7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65350938"
---
# <a name="document-validation-in-the-xml-disassembler-pipeline-component"></a>XML 逆アセンブラー パイプライン コンポーネントにおけるドキュメントの検証
既定では、XML 逆アセンブラーは、スキーマに対して XML ドキュメントを検証しません。 ただし、設定して XML ドキュメントを検証する XML 逆アセンブラーを構成することができます、**ドキュメント構造の検証**プロパティ。  
  
> [!CAUTION]
>  プロモーションのフィールドを単純なデータ型が宣言されて複雑なデータが含まれる場合は、プロパティの昇格に予期しない結果が発生します。 このシナリオを避けるためには、構成設定によってドキュメントの検証を実行する、XML 逆アセンブラー、**ドキュメント構造の検証**プロパティを**True**します。  
  
## <a name="see-also"></a>参照  
 [XML 逆アセンブラー パイプライン コンポーネント](../core/xml-disassembler-pipeline-component.md)   
 [XML 逆アセンブラー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-xml-disassembler-pipeline-component.md)