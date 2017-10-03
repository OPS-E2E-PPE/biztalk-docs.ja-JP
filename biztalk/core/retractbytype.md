---
title: "RetractByType |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- RetractByType function [Business Rules Engine], TypedXMLDocument
- RetractByType function [Business Rules Engine]
- RetractByType function [Business Rules Engine], .NET objects
- RetractByType function [Business Rules Engine], TypedData table
- RetractByType function [Business Rules Engine], DataConnection
- .NET objects
ms.assetid: e8867553-ee3c-46be-84cd-d5373eaf3337
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: da8cd4581007ad2bd93ed66ebce4f5de6378280c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="retractbytype"></a>[種類別の取り消し]
**RetractByType**関数によって、作業メモリに指定した型のすべてのインスタンスが取り消された、 **Retract**関数には、特定の種類の特定の項目だけが取り消されます。 以下に述べる方法、 **RetractByType**関数は、さまざまな種類のエンティティで機能します。  
  
## <a name="net-objects"></a>.NET オブジェクト  
 特定のクラスの種類のすべてのオブジェクトが作業メモリから取り消されます。 クラスを .NET クラス ファクト ペインからドラッグするだけ、 **RetractByType**関数。  
  
## <a name="typedxmldocument"></a>TypedXmlDocument  
 すべてのインスタンスが取り消されます。 つまり、すべて**TypedXmlDocument**同じ s **DocumentType.Selector**が取り消されます。 XML スキーマ ファクト ペインから、適切なノードをドラッグする必要があります、 **RetractByType**関数。 一貫性のある、 **Retract**関数を実行する場合、 **RetractByType**ドキュメント ルート ノード上だけでなく、すべて**TypedXmlDocuments**そのアサート**DocumentType**で取り消される場合、すべての子が**TypedXmlDocuments** (**XmlNode**ツリー階層内の s) その親に関連付けられている**TypedXmlDocuments**も取り消されます。  
  
## <a name="typeddatatable-and-dataconnection"></a>TypedDataTable と DataConnection  
 **取り消し**と**RetractByType**は両方の同等**TypedDataTable**と**DataConnection**です。 **DataSetName.DataTableName**一意の識別子は、両方の種類の 1 つだけインスタンスが、エンジンで任意の時点にします。 同様に**Retract**、テーブルをドラッグする、 **RetractByType**関数。  
  
## <a name="see-also"></a>参照  
 [エンジン制御関数](../core/engine-control-functions.md)