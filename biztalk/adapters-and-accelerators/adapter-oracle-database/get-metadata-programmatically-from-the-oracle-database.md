---
title: Oracle データベースからプログラムでメタデータの取得 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- metadata, retrieving programmatically from the Oracle database
ms.assetid: 28a55935-6078-41d0-abfa-ac86e9ca8471
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f8f3d6341e0f5d26d589f03dc0b93a3e5b0afa0
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529188"
---
# <a name="get-metadata-programmatically-from-the-oracle-database"></a>Oracle データベースからメタデータをプログラムで取得します。
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] WCF サービスとしての Oracle データベースを公開するカスタム WCF バインドします。 アダプターは、サービスを自己記述型として、Oracle データベースを公開しますサポートされる操作についてのメタデータを公開できるサービスは、します。 メタデータが、WCF サービスに論理インターフェイスについて説明しますつまり、サービス コントラクト、メッセージ、およびメッセージ スキーマ、サービスと対話するために使用する必要があります。  
  
 このメタデータがなどのツールによって使用されます。  
  
- [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]サービス コントラクトのマネージ コードの表現で生成して  
  
- [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]メッセージ スキーマを生成します。  
  
  ただしもメタデータを取得できますプログラムで、アダプターから。 たとえば、既存のアプリケーションで使用するカスタム メタデータの取得ツールを作成することする可能性があります。  
  
  アダプターは、2 つのエンドポイントからメタデータを発行します。  
  
- Ws-metadata Exchange (MEX) エンドポイント。 WCF では、すべての WCF バインドの MEX エンドポイントを自動的に提供します。 メタデータ交換を使用すると、基になる Oracle データベース アダプターによってサポートされる操作のメタデータを取得します。  
  
- **IMetadataRetrievalContract**エンドポイント。 **IMetadataRetrievalContract**インターフェイスによって実装されます、[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]します。 複数の論理レベルでの Oracle データベース成果物を分類し、それらをメタデータのノードのツリーとして表示します。 によって公開されるメソッドを使用することができます、 **IMetadataRetrievalContract**インターフェイスを参照し、このツリーのノードの検索と操作している対象のメタデータを返します。  
  
  このセクションのトピックでは、MEX を使用する方法を説明し、 **IMetadataRetrievalContract**アダプターからプログラムでメタデータを取得するエンドポイント。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [Ws-metadata Exchange を使用して Oracle データベースでメタデータを取得します。](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-using-ws-metadata-exchange-in-oracle-database.md)  
  
-   [IMetadataRetrievalContract を使用して Oracle データベースでメタデータを取得します。](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-in-oracle-database-using-imetadataretrievalcontract.md)  
  
## <a name="see-also"></a>参照  
[Oracle データベース アプリケーションの開発](../../adapters-and-accelerators/adapter-oracle-database/develop-your-oracle-database-applications.md)