---
title: RetractByType |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- RetractByType function [Business Rules Engine], TypedXMLDocument
- RetractByType function [Business Rules Engine]
- RetractByType function [Business Rules Engine], .NET objects
- RetractByType function [Business Rules Engine], TypedData table
- RetractByType function [Business Rules Engine], DataConnection
- .NET objects
ms.assetid: e8867553-ee3c-46be-84cd-d5373eaf3337
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 460684c52f00df531eb73f397fdc187829522be2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65309507"
---
# <a name="retractbytype"></a>RetractByType
**RetractByType**関数には、作業メモリ内の指定した型のすべてのインスタンスが取り消されますが、 **Retract**関数は、特定の種類の特定の項目だけを取り消します。 次の段落を記述する方法、 **RetractByType**関数は、さまざまな種類のエンティティを操作します。  
  
## <a name="net-objects"></a>.NET オブジェクト  
 指定されたクラス型のすべてのオブジェクトが作業メモリから取り消されます。 クラスに .NET クラス ファクト ペインからドラッグする、 **RetractByType**関数。  
  
## <a name="typedxmldocument"></a>TypedXmlDocument  
 すべてのインスタンスが取り消されます。 つまり、すべて**TypedXmlDocument**を同じ**DocumentType.Selector**が取り消されます。 XML スキーマ ファクト ペインから、適切なノードをドラッグする必要があります、 **RetractByType**関数。 一貫性のある、 **Retract**関数を実行する場合、 **RetractByType**ドキュメントのルート ノードにするだけでなくすべて**TypedXmlDocuments**そのアサート**DocumentType**すべての子ですが、取り消す**TypedXmlDocuments** (**XmlNode**ツリー階層内の) その親に関連付けられている**TypedXmlDocuments**も取り消されます。  
  
## <a name="typeddatatable-and-dataconnection"></a>TypedDataTable と DataConnection  
 **取り消し**と**RetractByType**の両方に対応が**TypedDataTable**と**DataConnection**します。 **DataSetName.DataTableName**一意の識別子は、両方の種類はインスタンス 1 つだけ、エンジンで任意の時点にある時間。 同様**Retract**、テーブルをドラッグする、 **RetractByType**関数。  
  
## <a name="see-also"></a>参照  
 [エンジン制御関数](../core/engine-control-functions.md)