---
title: "BizTalk Server を使用してポーリング Oracle E-business Suite |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a22b99a5-1715-4351-b0e0-6b8dcfacd9eb
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f9b5d0743d39dfcf6cbab7e1da20a8a3fb1382fe
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="poll-oracle-e-business-suite-using-biztalk-server"></a>BizTalk Server を使用してポーリング Oracle E-business Suite
構成することができます、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle データベースからのポーリングに基づいたメッセージを受信します。 アダプターは、Oracle データベースをポーリングする 2 つの方法を提供します。  
  
-   **SELECT ステートメントを使用して**です。 Oracle データベースをポーリングする単純な SELECT ステートメントを指定することができます。 アダプターは、指定した間隔で SELECT ステートメントを実行し、アダプターのクライアントに結果を返します。  
  
-   **ストアド プロシージャを使用して**です。 Oracle データベースをポーリングするストアド プロシージャを指定することができます。 アダプターは、指定した間隔で、ストアド プロシージャを実行し、アダプターのクライアントに結果を返します。  
  
 2 つのアプローチの主な違いは、方法アダプター クライアントが、アダプターを使用して Oracle データベースをポーリングするポーリング ステートメントを指定します。 最初の方法のポーリング ステートメントには、単純な SELECT ステートメントが、ストアド プロシージャのアプローチのポーリング ステートメント、ストアド プロシージャを実行する要求メッセージです。 アダプターのクライアントのいずれかの方法について、ポーリング ステートメントを指定して、 **PollingInput**プロパティをバインドします。 バインドのプロパティの詳細については、次を参照してください。 [BizTalk Adapter for Oracle E-business Suite バインド プロパティ読む](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)です。  
  
 このセクションのトピックでは、SELECT ステートメントおよびストアド プロシージャを使用してをポーリングする方法について説明します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [SELECT ステートメントを使用してポーリング Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/poll-oracle-e-business-suite-using-select-statement.md)  
  
-   [ストアド プロシージャを使用してポーリング Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/poll-oracle-e-business-suite-using-stored-procedures.md)  
  
## <a name="see-also"></a>参照  
[Oracle E-business Suite アダプターを使用して BizTalk アプリケーションを開発します。](../../adapters-and-accelerators/adapter-oracle-ebs/develop-biztalk-applications-using-the-oracle-e-business-suite-adapter.md)