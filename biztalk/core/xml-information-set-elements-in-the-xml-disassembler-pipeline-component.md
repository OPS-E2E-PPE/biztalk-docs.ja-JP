---
title: XML 情報は、XML 逆アセンブラー パイプライン コンポーネントで要素を設定 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- XML Disassembler [pipeline component], information set
- XML Disassembler [pipeline component], processing instructions
- pipeline components, XML Disassembler
ms.assetid: cc82344c-6c4b-4154-a662-0b7ae5caad30
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2b9d2b581a327f8d7009794338d431a2358db748
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65298484"
---
# <a name="xml-information-set-elements-in-the-xml-disassembler-pipeline-component"></a>XML 情報は、XML 逆アセンブラー パイプライン コンポーネントで要素を設定
XML 逆アセンブラーは、次のように XML 情報セットの要素を処理します。  
  
|要素|説明|  
|-------------|-----------------|  
|comment|コメントはドキュメントに保存されます。ただし、XML エンベロープ内のコメントは保持されません。|  
|CDATA|CDATA はドキュメントに保持されます。 (たとえば、エンベロープ) 内のドキュメントの外部に現れる CDATA 要素は保持されません。|  
|処理命令|XML 逆アセンブラーでは、XML ドキュメントの以前のある処理命令が保持されます。 XML ドキュメントの後または前に、またはエンベロープの後にある処理命令は保持されません。|  
|XML 宣言|受信 XML メッセージの XML 宣言の要素が削除されます。|  
  
## <a name="see-also"></a>参照  
 [XML 逆アセンブラー パイプライン コンポーネント](../core/xml-disassembler-pipeline-component.md)   
 [XML 逆アセンブラー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-xml-disassembler-pipeline-component.md)