---
title: SAP からメタデータをプログラムで取得 |Microsoft ドキュメント
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
ms.openlocfilehash: 4c856b3629d7d7dcd3f9aa5431c0406f6c822e54
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22216834"
---
# <a name="get-metadata-programmatically-from-sap"></a>SAP からメタデータをプログラムで取得します。
[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]は、WCF サービスとして SAP システムを公開するカスタムの WCF バインディング。 アダプターは、自己記述型のサービスとして SAP システムを公開します。サポートされる操作に関するメタデータを公開できるサービスは、します。 メタデータは、WCF サービス; を論理インターフェイスを説明します。つまり、サービス コントラクト、メッセージ、およびメッセージ スキーマ、サービスと対話するために使用する必要があります。  
  
 このメタデータがなどのツールによって使用されます。  
  
-   [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]マネージ コードを表す、サービス コントラクトの生成と  
  
-   [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]メッセージ スキーマを生成します。  
  
 ただし、ことができますもメタデータを取得するプログラムで、アダプターからです。 たとえば、既存のアプリケーションで使用するカスタム メタデータ取得ツールを作成することができます。  
  
 アダプターは、2 つのエンドポイントを介してメタデータを公開します。  
  
-   Ws-metadata Exchange (MEX) エンドポイント。 WCF では、すべての WCF バインドの MEX エンドポイントが自動的に用意されています。 メタデータ交換を使用すると、基になる SAP システム上のアダプターによってサポートされる操作のメタデータを取得します。  
  
-   **IMetadataRetrievalContract**エンドポイント。 **IMetadataRetrievalContract**インターフェイスは、[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]です。 複数の論理レベルでの SAP システムの成果物を分類し、それらがメタデータのノードのツリーとして表示します。 によって公開されるメソッドを使用することができます、 **IMetadataRetrievalContract**インターフェイスを参照して、このツリーのノードを検索しの関心がある操作のメタデータを返します。  
  
 このセクションのトピックでは、MEX を使用する方法を説明し、 **IMetadataRetrievalContract**アダプターからメタデータをプログラムから取得するエンドポイント。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [SAP で Ws-metadata Exchange を使用してメタデータを取得します。](../../adapters-and-accelerators/adapter-sap/get-metadata-using-ws-metadata-exchange-in-sap.md)  
  
-   [IMetadataRetrievalContract を使用して SAP のメタデータを取得します。](../../adapters-and-accelerators/adapter-sap/get-metadata-in-sap-using-imetadataretrievalcontract.md)  
  
## <a name="see-also"></a>参照  
[SAP アプリケーションを開発します。](../../adapters-and-accelerators/adapter-sap/develop-your-sap-applications.md)