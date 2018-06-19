---
title: XML 情報は、XML 逆アセンブラー パイプライン コンポーネントで要素を設定 |Microsoft ドキュメント
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
ms.openlocfilehash: 90b3140cbe23637160aafabdccb37104efd1d318
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22289298"
---
# <a name="xml-information-set-elements-in-the-xml-disassembler-pipeline-component"></a>XML 情報は、XML 逆アセンブラー パイプライン コンポーネントで要素を設定
XML 逆アセンブラーでは、各種の XML 要素が次のように扱われます。  
  
|要素|Description|  
|-------------|-----------------|  
|comment|コメントはドキュメント内に保存されますが、XML エンべロープ内のコメントは保存されません。|  
|CDATA|CDATA はドキュメント内に保存されます。 ドキュメント外部 (エンベロープ内など) に現れる CDATA 要素は保存されません。|  
|処理命令|XML 逆アセンブラーは、XML ドキュメント内または XML ドキュメントの前にある処理命令を保存します。 XML ドキュメントの後、あるいはエンベロープの前または後にある処理命令は、保存されません。|  
|XML 宣言|受信 XML メッセージの XML 宣言要素はすべて削除されます。|  
  
## <a name="see-also"></a>参照  
 [XML 逆アセンブラー パイプライン コンポーネント](../core/xml-disassembler-pipeline-component.md)   
 [XML 逆アセンブラー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-xml-disassembler-pipeline-component.md)