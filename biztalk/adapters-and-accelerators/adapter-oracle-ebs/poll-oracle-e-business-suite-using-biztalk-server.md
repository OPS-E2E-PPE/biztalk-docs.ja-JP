---
title: BizTalk Server を使用してポーリング Oracle E-business Suite |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a22b99a5-1715-4351-b0e0-6b8dcfacd9eb
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b8180b3b671c87b5dcd0d41477e20b6d175f1cce
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974219"
---
# <a name="poll-oracle-e-business-suite-using-biztalk-server"></a>BizTalk Server を使用してポーリング Oracle E-business Suite
構成することができます、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle データベースからのポーリング ベースのメッセージを受信します。 アダプターは、Oracle データベースをポーリングの 2 つの方法を提供します。  
  
- **SELECT ステートメントを使用して**します。 Oracle データベースをポーリングする単純な SELECT ステートメントを指定することができます。 アダプターは、指定した間隔で SELECT ステートメントを実行し、アダプターのクライアントに結果を返します。  
  
- **ストアド プロシージャを使用して**します。 Oracle データベースをポーリングするストアド プロシージャを指定することができます。 アダプターは、指定した間隔でストアド プロシージャを実行し、アダプターのクライアントに結果を返します。  
  
  2 つのアプローチの主な違いは、方法アダプターのクライアントは、アダプターを使用して Oracle データベースをポーリングするポーリング ステートメントを指定します。 最初の方法のポーリング ステートメントには、単純な SELECT ステートメントが、ストアド プロシージャのアプローチのポーリング ステートメント、ストアド プロシージャを実行する要求メッセージです。 アダプター クライアントのポーリング ステートメント、どちらの方法を指定して、 **PollingInput**プロパティをバインドします。 バインド プロパティの詳細については、次を参照してください。[については、BizTalk Adapter for Oracle E-business Suite バインド プロパティを読み取る](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)します。  
  
  このセクションのトピックでは、SELECT ステートメントおよびストアド プロシージャを使用してポーリングする方法について説明します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [SELECT ステートメントを使用してポーリング Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/poll-oracle-e-business-suite-using-select-statement.md)  
  
-   [ストアド プロシージャを使用してポーリング Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/poll-oracle-e-business-suite-using-stored-procedures.md)  
  
## <a name="see-also"></a>参照  
[Oracle E-business Suite アダプターを使用して BizTalk アプリケーションを開発します。](../../adapters-and-accelerators/adapter-oracle-ebs/develop-biztalk-applications-using-the-oracle-e-business-suite-adapter.md)