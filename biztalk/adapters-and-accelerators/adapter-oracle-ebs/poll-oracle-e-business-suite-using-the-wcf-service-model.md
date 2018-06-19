---
title: WCF を使用してポーリング Oracle E-business Suite サービス モデル |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 96670a39-4fec-49bf-85d1-947b1a1bc750
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0122bceddbfd902f31549efe9bc8819f108b6f57
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22215114"
---
# <a name="poll-oracle-e-business-suite-using-the-wcf-service-model"></a>WCF サービス モデルを使用してポーリング Oracle E-business Suite
構成することができます、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle データベースからのポーリングに基づいたメッセージを受信します。 アダプターは、Oracle データベースをポーリングする 2 つの方法を提供します。  
  
-   **SELECT ステートメントを使用して**です。 Oracle データベースをポーリングする単純な SELECT ステートメントを指定することができます。 アダプターは、指定した間隔で SELECT ステートメントを実行し、アダプターのクライアントに結果を返します。  
  
-   **ストアド プロシージャを使用して**です。 Oracle データベースをポーリングするストアド プロシージャを指定することができます。 アダプターは、指定した間隔で、ストアド プロシージャを実行し、アダプターのクライアントに結果を返します。  
  
 2 つのアプローチの主な違いは、方法アダプター クライアントが、アダプターを使用して Oracle データベースをポーリングするポーリング ステートメントを指定します。 最初の方法のポーリング ステートメントには、単純な SELECT ステートメントが、ストアド プロシージャのアプローチのポーリング ステートメント、ストアド プロシージャを実行する要求メッセージです。 アダプターのクライアントのいずれかの方法について、ポーリング ステートメントを指定して、 **PollingInput**プロパティをバインドします。 バインドのプロパティの詳細については、次を参照してください。 [Oracle E-business Suite バインド プロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)です。  
  
 このセクションのトピックでは、SELECT ステートメントおよびストアド プロシージャを使用してをポーリングする方法について説明します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [WCF サービス モデルで SELECT ステートメントを使用してポーリング Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/poll-oracle-e-business-suite-using-select-statement-with-the-wcf-service-model.md)  
  
-   [WCF サービス モデルでストアド プロシージャを使用してポーリング Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/poll-oracle-e-business-suite-using-stored-procedures-with-the-wcf-service-model.md)  
  
## <a name="see-also"></a>参照  
 [WCF サービス モデルを使用して Oracle E-business Suite アプリケーションを開発します。](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-service-model.md)