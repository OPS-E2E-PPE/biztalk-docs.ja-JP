---
title: Oracle データベースからメタデータをプログラムで取得 |Microsoft ドキュメント
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
ms.openlocfilehash: c36fcd6a791f1d960a4dd4dfd78ca199d2e49cb5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214274"
---
# <a name="get-metadata-programmatically-from-the-oracle-database"></a>Oracle データベースからメタデータをプログラムで取得します。
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]は、WCF サービスとして Oracle データベースを公開するカスタムの WCF バインディング。 アダプターは、自己記述型のサービスとして、Oracle データベースを公開します。サポートされる操作に関するメタデータを公開できるサービスは、します。 メタデータは、WCF サービス; を論理インターフェイスを説明します。つまり、サービス コントラクト、メッセージ、およびメッセージ スキーマ、サービスと対話するために使用する必要があります。  
  
 このメタデータがなどのツールによって使用されます。  
  
-   [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]マネージ コードを表す、サービス コントラクトの生成と  
  
-   [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]メッセージ スキーマを生成します。  
  
 ただし、ことができますもメタデータを取得するプログラムで、アダプターからです。 たとえば、既存のアプリケーションで使用するカスタム メタデータ取得ツールを作成することができます。  
  
 アダプターは、2 つのエンドポイントを介してメタデータを公開します。  
  
-   Ws-metadata Exchange (MEX) エンドポイント。 WCF では、すべての WCF バインドの MEX エンドポイントが自動的に用意されています。 メタデータ交換を使用すると、基になる Oracle データベースで、アダプターでサポートされる操作のメタデータを取得します。  
  
-   **IMetadataRetrievalContract**エンドポイント。 **IMetadataRetrievalContract**インターフェイスは、[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]です。 複数の論理レベルでの Oracle データベースの成果物を分類し、それらがメタデータのノードのツリーとして表示します。 によって公開されるメソッドを使用することができます、 **IMetadataRetrievalContract**インターフェイスを参照して、このツリーのノードを検索しの関心がある操作のメタデータを返します。  
  
 このセクションのトピックでは、MEX を使用する方法を説明し、 **IMetadataRetrievalContract**アダプターからメタデータをプログラムから取得するエンドポイント。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [Ws-metadata Exchange を使用して Oracle データベースでメタデータを取得します。](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-using-ws-metadata-exchange-in-oracle-database.md)  
  
-   [IMetadataRetrievalContract を使用して Oracle データベース内のメタデータを取得します。](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-in-oracle-database-using-imetadataretrievalcontract.md)  
  
## <a name="see-also"></a>参照  
[Oracle データベース アプリケーションを開発します。](../../adapters-and-accelerators/adapter-oracle-database/develop-your-oracle-database-applications.md)