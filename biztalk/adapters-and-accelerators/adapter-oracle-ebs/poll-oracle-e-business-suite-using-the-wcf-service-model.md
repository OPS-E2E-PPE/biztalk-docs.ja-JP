---
title: WCF を使用してポーリング Oracle E-business Suite のサービス モデル |Microsoft Docs
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
ms.openlocfilehash: b2f8c9f16ed93e2866da0cbd55021edfdb2bd863
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36995347"
---
# <a name="poll-oracle-e-business-suite-using-the-wcf-service-model"></a>WCF サービス モデルを使用してポーリング Oracle E-business Suite
構成することができます、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle データベースからのポーリング ベースのメッセージを受信します。 アダプターは、Oracle データベースをポーリングの 2 つの方法を提供します。  
  
- **SELECT ステートメントを使用して**します。 Oracle データベースをポーリングする単純な SELECT ステートメントを指定することができます。 アダプターは、指定した間隔で SELECT ステートメントを実行し、アダプターのクライアントに結果を返します。  
  
- **ストアド プロシージャを使用して**します。 Oracle データベースをポーリングするストアド プロシージャを指定することができます。 アダプターは、指定した間隔でストアド プロシージャを実行し、アダプターのクライアントに結果を返します。  
  
  2 つのアプローチの主な違いは、方法アダプターのクライアントは、アダプターを使用して Oracle データベースをポーリングするポーリング ステートメントを指定します。 最初の方法のポーリング ステートメントには、単純な SELECT ステートメントが、ストアド プロシージャのアプローチのポーリング ステートメント、ストアド プロシージャを実行する要求メッセージです。 アダプター クライアントのポーリング ステートメント、どちらの方法を指定して、 **PollingInput**プロパティをバインドします。 バインド プロパティの詳細については、次を参照してください。 [Oracle E-business Suite バインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)します。  
  
  このセクションのトピックでは、SELECT ステートメントおよびストアド プロシージャを使用してポーリングする方法について説明します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [SELECT ステートメントを使用して WCF サービス モデルとポーリング Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/poll-oracle-e-business-suite-using-select-statement-with-the-wcf-service-model.md)  
  
-   [ストアド プロシージャを使用して WCF サービス モデルとポーリング Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/poll-oracle-e-business-suite-using-stored-procedures-with-the-wcf-service-model.md)  
  
## <a name="see-also"></a>参照  
 [WCF サービス モデルを使用して Oracle E-business Suite のアプリケーションを開発します。](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-service-model.md)