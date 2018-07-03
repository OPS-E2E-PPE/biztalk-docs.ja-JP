---
title: SAP からプログラムでメタデータの取得 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IMetadataRetrievalContract endpoint
- metadata, retrieving programmatically
- WS-Metadata Exchange (MEX) endpoint
ms.assetid: 8d75332e-c103-4bd5-a9a2-56d21747a04e
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c0bf41b8213afd1c1af00c113e4a5406e6289dac
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013851"
---
# <a name="get-metadata-programmatically-from-sap"></a>SAP からプログラムでメタデータを取得します。
[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] WCF サービスとしての SAP システムを公開するカスタム WCF バインドします。 アダプターは、自己記述型のサービスとしての SAP システムを公開しますサポートされる操作についてのメタデータを公開できるサービスは、します。 メタデータが、WCF サービスに論理インターフェイスについて説明しますつまり、サービス コントラクト、メッセージ、およびメッセージ スキーマ、サービスと対話するために使用する必要があります。  
  
 このメタデータがなどのツールによって使用されます。  
  
- [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]サービス コントラクトのマネージ コードの表現で生成して  
  
- [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]メッセージ スキーマを生成します。  
  
  ただしもメタデータを取得できますプログラムで、アダプターから。 たとえば、既存のアプリケーションで使用するカスタム メタデータの取得ツールを作成することする可能性があります。  
  
  アダプターは、2 つのエンドポイントからメタデータを発行します。  
  
- Ws-metadata Exchange (MEX) エンドポイント。 WCF では、すべての WCF バインドの MEX エンドポイントを自動的に提供します。 メタデータ交換を使用すると、基になる SAP システムのアダプターでサポートされる操作のメタデータを取得します。  
  
- **IMetadataRetrievalContract**エンドポイント。 **IMetadataRetrievalContract**インターフェイスによって実装されます、[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]します。 複数の論理レベルでの SAP システムの成果物を分類し、それらをメタデータのノードのツリーとして表示します。 によって公開されるメソッドを使用することができます、 **IMetadataRetrievalContract**インターフェイスを参照し、このツリーのノードの検索と操作している対象のメタデータを返します。  
  
  このセクションのトピックでは、MEX を使用する方法を説明し、 **IMetadataRetrievalContract**アダプターからプログラムでメタデータを取得するエンドポイント。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [SAP で Ws-metadata Exchange を使用してメタデータを取得します。](../../adapters-and-accelerators/adapter-sap/get-metadata-using-ws-metadata-exchange-in-sap.md)  
  
-   [IMetadataRetrievalContract を使用して sap メタデータの取得](../../adapters-and-accelerators/adapter-sap/get-metadata-in-sap-using-imetadataretrievalcontract.md)  
  
## <a name="see-also"></a>参照  
[SAP アプリケーションを開発する](../../adapters-and-accelerators/adapter-sap/develop-your-sap-applications.md)