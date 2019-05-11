---
title: BizTalk Server を使用してポーリング Oracle データベース |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9c3aef30-956d-4585-b2de-7eebb919fab5
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 31a4a7d7afe372c6334219ec8cdf84a3e43aef65
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65376269"
---
# <a name="poll-oracle-database-using-biztalk-server"></a>BizTalk Server を使用してポーリング Oracle データベース
構成することができます、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Oracle データベースからのポーリング ベースのメッセージを受信します。 アダプターは、Oracle データベースをポーリングの 2 つの方法を提供します。  
  
- **SELECT ステートメントを使用して**します。 テーブルと Oracle データベースでビューをポーリングする単純な SELECT ステートメントを指定することができます。 アダプターは、指定した間隔で SELECT ステートメントを実行し、アダプターのクライアントに結果を返します。  
  
- **ストアド プロシージャ、関数、またはプロシージャまたはパッケージ内の関数を使用して**します。 ストアド プロシージャ、関数、またはプロシージャまたは Oracle データベースをポーリングするパッケージ内の関数を指定することができます。 アダプターは、指定した間隔で要求メッセージを実行し、アダプターのクライアントに結果を返します。  
  
  2 つのアプローチの主な違いは、方法アダプターのクライアントは、アダプターを使用して Oracle データベースをポーリングするポーリング ステートメントを指定します。 最初の方法のポーリング ステートメントには、単純な SELECT ステートメントが、その他のアプローチのポーリング ステートメント、ストアド プロシージャ、関数、またはプロシージャまたはパッケージ内の関数を実行する要求メッセージです。 アダプター クライアントのいずれの方法でも、ポーリング ステートメントを指定する、 **PollingStatement**プロパティをバインドします。 バインド プロパティの詳細については、次を参照してください。 [Oracle データベース アダプターのバインドのプロパティについて](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md)します。  
  
  このセクションのトピックでは、SELECT ステートメントとストアド プロシージャ、関数、またはプロシージャを使用してポーリングする方法について説明またはパッケージ内で機能します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [SELECT ステートメントを使用してポーリング Oracle データベース](../../adapters-and-accelerators/adapter-oracle-database/poll-oracle-database-using-the-select-statement.md)  
  
-   [ストアド プロシージャ、関数、またはパッケージ化されたプロシージャおよび関数を使用してポーリング Oracle データベース](../../adapters-and-accelerators/adapter-oracle-database/poll-oracle-db-using-stored-procedures-functions-or-packaged-procedures.md)  
  
## <a name="see-also"></a>参照  
[Oracle データベース アダプターを使用して BizTalk アプリケーションを開発します。](../../adapters-and-accelerators/adapter-oracle-database/develop-biztalk-applications-using-the-oracle-database-adapter.md)